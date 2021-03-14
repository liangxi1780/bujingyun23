Swoole
======
[![Build Status](https://api.travis-ci.org/swoole/swoole-src.svg)](https://travis-ci.org/swoole/swoole-src)
[![License](https://img.shields.io/badge/license-apache2-blue.svg)](LICENSE)
[![Join the chat at https://gitter.im/swoole/swoole-src](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/swoole/swoole-src?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)
[![Coverity Scan Build Status](https://scan.coverity.com/projects/11654/badge.svg)](https://scan.coverity.com/projects/swoole-swoole-src)

Swoole is an event-driven asynchronous & concurrent networking communication framework with high performance written only in C for PHP.

* __Document__: https://github.com/swoole/swoole-docs
* __API__:  
* __IDE Helper__:  
* __中文文档__:  
* __IRC__:   

* __Twitter__:  
* __Slack Group__:  

Event-based
------

The network layer in Swoole is event-based and takes full advantage of the underlaying epoll/kqueue implementation, making it really easy to serve thousands of connections.

Coroutine
----------------
[Swoole 2.0](Version2.md) supports the built-in coroutine, and you can use fully synchronized code to implement asynchronous programs. PHP code without any additional keywords, the underlying automatic coroutine-scheduling.

```php
 connect('127.0.0.1', 6379);
        $ret = $redis->incr('coroutine');
        $redis->close();
        if ($i == 50) {
            Swoole\Coroutine::create(function() use ($i) {
                $redis = new Swoole\Coroutine\Redis();
                $res = $redis->connect('127.0.0.1', 6379);
                $ret = $redis->set('coroutine_i', 50);
                $redis->close();
            });
        }
    });
}
```

```php
 on('Request', function($request, $response) {

    $tcp_cli = new Swoole\Coroutine\Client(SWOOLE_SOCK_TCP);
    $ret = $tcp_cli->connect('127.0.0.1', 9906);
    $tcp_cli ->send('test for the coroutine');
    $ret = $tcp_cli->recv(5);
    $tcp_cli->close();

    if ($ret) {
        $response->end(' swoole response is ok');
    }
    else{
        $response->end(" recv failed error : {$client->errCode}");
    }
});

$server->start();
```

Concurrent
------

On the request processing part, Swoole uses a multi-process model. Every process works as a worker. All business logic is executed in workers, synchronously.

With the synchronous logic execution, you can easily write large and robust applications and take advantage of almost all libraries available to the PHP community.

In-memory
------

Unlike traditional apache/php-fpm stuff, the memory allocated in Swoole will not be freed after a request, which can improve performance a lot.


## Why Swoole?

Traditional PHP applications almost always run behind Apache/Nginx, without much control of the request. This brings several limitations:

1. All memory will be freed after the request. All PHP code needs be re-compiled on every request. Even with opcache enabled, all opcode still needs to be re-executed.
2. It is almost impossible to implement long connections and connection pooling techniques.
3. Implementing asynchronous tasks requires third-party queue servers, such as rabbitmq and beanstalkd.
4. Implementing realtime applications such as chatting servers requires third-party languages, such as nodejs, for example.

This is why Swoole appeared. Swoole extends the use cases of PHP, and brings all these possibilities to the PHP world.
By using Swoole, you can build enhanced web applications with more control, real-time chatting servers, etc, more easily.

## Requirements

* Version-1: PHP 5.3.10 or later
* Version-2: PHP 5.5.0 or later
* Linux, OS X and basic Windows support (thanks to cygwin)
* GCC 4.4 or later

## Installation

1. Install via pecl

    ```
    pecl install swoole
    ```

2. Install from source

    ```
    sudo apt-get install php5-dev
    git clone https://github.com/swoole/swoole-src.git
    cd swoole-src
    phpize
    ./configure
    make && make install
    ```

## Introduction

Swoole includes components for different purposes: Server, Task Worker, Timer, Event and Async IO. With these components, Swoole allows you to build many features.

### Server

This is the most important part in Swoole. It provides the necessary infrastructure to build server applications.
With Swoole server, you can build web servers, chat messaging servers, game servers and almost anything you want.

The following example shows a simple echo server.

```php
// Create a server instance
$serv = new swoole_server('127.0.0.1', 9501);

// Attach handler for connect event. Once the client has connected to the server, the registered handler will be
// executed.
$serv->on('connect', function ($serv, $fd) {
    echo "Client:Connect.\n";
});

// Attach handler for receive event. Every piece of data will be received by server and the registered handler will be
// executed. All custom protocol implementation should be located there.
$serv->on('receive', function ($serv, $fd, $from_id, $data) {
    $serv->send($fd, $data);
});

$serv->on('close', function ($serv, $fd) {
    echo "Client: Close.\n";
});

// Start our server, listen on the port and be ready to accept connections.
$serv->start();
```

Try to extend your server and implement what you want!

### HTTP Server

```php
$http = new swoole_http_server('0.0.0.0', 9501);

$http->on('request', function ($request, $response) {
    $response->header('Content-Type', 'text/html; charset=utf-8');
    $response->end(' Hello Swoole. #' . rand(1000, 9999) . ' ');
});

$http->start();
```

### WebSocket Server

```php
$ws = new swoole_websocket_server('0.0.0.0', 9502);

$ws->on('open', function ($ws, $request) {
    var_dump($request->fd, $request->get, $request->server);
    $ws->push($request->fd, "hello, welcome\n");
});

$ws->on('message', function ($ws, $frame) {
    echo "Message: {$frame->data}\n";
    $ws->push($frame->fd, "server: {$frame->data}");
});

$ws->on('close', function ($ws, $fd) {
    echo "client-{$fd} is closed\n";
});

$ws->start();
```

### Real async-mysql client
```php
$db = new swoole_mysql('127.0.0.1', 'root', 'root', 'test');

$db->on('close', function($o) {
    echo "mysql connection is closed\n";
});

$db->query('select now() as now_t', function($db, $result_rows) {
    var_dump($result_rows);
    $db->close();
});
```

### Real async-redis client
```php
$client = new swoole_redis;
$client->connect('127.0.0.1', 6379, function (swoole_redis $client, $result) {
    echo "connect\n";
    var_dump($result);
    $client->set('key', 'swoole', function (swoole_redis $client, $result) {
        var_dump($result);
        $client->get('key', function (swoole_redis $client, $result) {
            var_dump($result);
            $client->close();
        });
    });
});
```


### Async http Client

```php
$cli = new swoole_http_client('127.0.0.1', 80);

$cli->setHeaders(['User-Agent' => 'swoole']);
$cli->post('/dump.php', array('test' => '9999999'), function (swoole_http_client $cli) {
    echo "#{$cli->sock}\tPOST response Length: " . strlen($cli->body) . "\n";
    $cli->get('/index.php', function (swoole_http_client $cli) {
        echo "#{$cli->sock}\tGET response Length: " . strlen($cli->body) . "\n";
    });
});
```

### Async WebSocket Client

```php
$cli = new swoole_http_client('127.0.0.1', 9501);

$cli->on('message', function ($_cli, $frame) {
    var_dump($frame);
});

$cli->upgrade('/', function ($cli) {
    echo $cli->body;
    $cli->push('Hello world');
});
```


### Multi-port and mixed protocol

```php
$serv = new swoole_http_server('127.0.0.1', 9501, SWOOLE_BASE);

$port2 = $serv->listen('0.0.0.0', 9502, SWOOLE_SOCK_TCP);
$port2->on('receive', function (swoole_server $serv, $fd, $from_id, $data) {
    var_dump($data);
    $serv->send($fd, $data);
});

$serv->on('request', function($req, $resp) {
    $resp->end(' Hello world ');
});


$serv->start();
```

### Task Worker

Swoole brings you two types of workers: server workers and task workers. Server workers are for request
handling, as demonstrated above. Task workers are for task execution. With task workers, we can execute our
task asynchronously without blocking the server workers.

Task workers are mainly used for time-consuming tasks, such as sending password recovery emails, and ensure
the main request returns as soon as possible.

The following example shows a simple server with task support.

```php
$serv = new swoole_server("127.0.0.1", 9502);

// Sets server configuration, we set task_worker_num config greater than 0 to enable task workers support
$serv->set(array('task_worker_num' => 4));

// Attach handler for receive event, which has been explained above.
$serv->on('receive', function($serv, $fd, $from_id, $data) {
    // We dispath a task to task workers by invoke the task() method of $serv
    // This method returns a task id as the identity of ths task
    $task_id = $serv->task($data);
    echo "Dispath AsyncTask: id=$task_id\n";
});

// Attach handler for task event. The handler will be executed in task workers.
$serv->on('task', function ($serv, $task_id, $from_id, $data) {
    // Handle the task and do what you want with $data
    echo "New AsyncTask[id=$task_id]" . PHP_EOL;

    // After the task is handled, we return the results to the caller worker.
    $serv->finish("$data -> OK");
});

// Attach handler for finish event. The handler will be executed in server workers. The same worker dispatched this task before.
$serv->on('finish', function ($serv, $task_id, $data) {
    echo "AsyncTask[$task_id] Finish: $data" . PHP_EOL;
});

$serv->start();
```

Swoole also supports synchronous tasks. To use synchronous tasks, just simply replace
`$serv->task($data)` with `$serv->taskwait($data)`. Unlike `task()`, `taskwait()` will wait for a task to
complete before it returns its response.

### Timer

Swoole has built-in millisecond timer support. By using the timer, it is easy to get a block of code
executed periodically (really useful for managing interval tasks).

To demonstrate how the timer works, here is a small example:

```php
//interval 2000ms
$serv->tick(2000, function ($timer_id) {
    echo "tick-2000ms\n";
});

//after 3000ms
$serv->after(3000, function () {
    echo "after 3000ms.\n"
});
```

In the example above, we first set the `timer` event handler to `swoole_server` to enable timer support.
Then, we add two timers by calling `bool swoole_server::addtimer($interval)` once the server started.
To handle multiple timers, we switch the `$interval` in registered handler and do what we want to do.

### Event

Swoole's I/O layer is event-based, which is very convenient to add your own file descriptor to Swoole's main eventloop.
With event support, you can also build fully asynchronous applications with Swoole.

To use events in Swoole, we can use `swoole_event_set()` to register event handler to sepecified file descriptor,
once registered descriptors become readable or writeable, our registered handler will be invoked. Also, we can
using `bool swoole_event_del(int $fd);` to remove registered file descriptor from eventloop.

The following are prototypes for the related functions:

```php
bool swoole_event_add($fd, mixed $read_callback, mixed $write_callback, int $flag);
bool swoole_event_set($fd, mixed $read_callback, mixed $write_callback, int $flag);
bool swoole_event_del($fd);
```

The `$fd` parameter can be one of the following types:

* unix file descriptor
* stream resource created by `stream_socket_client()/fsockopen()`
* sockets resources created by `socket_create()` in sockets extension (require compile swoole with --enable-sockets support)

The `$read_callback` and `$write_callback` are callbacks for corresponding read/write event.

The `$flag` is a mask to indicate what type of events we should get notified, can be `SWOOLE_EVENT_READ`,
`SWOOLE_EVENT_WRITE` or `SWOOLE_EVENT_READ | SWOOLE_EVENT_WRITE`

### Async IO

Swoole's Async IO provides the ability to read/write files and lookup dns records asynchronously. The following
are signatures for these functions:


```php
bool swoole_async_readfile(string $filename, mixed $callback);
bool swoole_async_writefile('test.log', $file_content, mixed $callback);
bool swoole_async_read(string $filename, mixed $callback, int $trunk_size = 8192);
bool swoole_async_write(string $filename, string $content, int $offset = -1, mixed $callback = NULL);
void swoole_async_dns_lookup(string $domain, function($host, $ip){});
bool swoole_timer_after($after_n_ms, mixed $callback);
bool swoole_timer_tick($n_ms, mixed $callback);
bool swoole_timer_clear($n_ms, mixed $callback);
```

Refer to [API Reference](http://u.720life.cn/g/277253dc8bbf9e7678a39b9da116d01c057e639b7bea032dcc58f15413630c481355fade1ffb7ab78b91f829a724ac7d) for more detailed information about these functions.


### Client

Swoole also provides a client component to build tcp/udp clients in both asynchronous and synchronous ways.
Swoole uses the `swoole_client` class to expose all its functionalities.

synchronous blocking:
```php
$client = new swoole_client(SWOOLE_SOCK_TCP);
if (!$client->connect('127.0.0.1', 9501, 0.5)) {
    die('connect failed.');
}

if (!$client->send('Hello world')) {
    die('send failed.');
}

$data = $client->recv();
if (!$data) {
    die('recv failed.');
}

$client->close();

```

Asynchronous non-blocking:

```php
$client = new swoole_client(SWOOLE_SOCK_TCP, SWOOLE_SOCK_ASYNC);

$client->on('connect', function($cli) {
    $cli->send("Hello world\n");
});
$client->on('receive', function($cli, $data) {
    echo "Received: ".$data."\n";
});
$client->on('error', function($cli) {
    echo "Connect failed\n";
});
$client->on('close', function($cli) {
    echo "Connection close\n";
});

$client->connect('127.0.0.1', 9501, 0.5);
```

The following methods are available in swoole_client:

```php
swoole_client::__construct(int $sock_type, int $is_sync = SWOOLE_SOCK_SYNC, string $key);
int swoole_client::on(string $event, mixed $callback);
bool swoole_client::connect(string $host, int $port, float $timeout = 0.1, int $flag = 0)
bool swoole_client::isConnected();
int swoole_client::send(string $data);
bool swoole_client::sendfile(string $filename)
string swoole_client::recv(int $size = 65535, bool $waitall = 0);
bool swoole_client::close();
```

Refer to [API Reference](http://u.720life.cn/g/277253dc8bbf9e7678a39b9da116d01c057e639b7bea032dcc58f15413630c48b0f41a59a1618f0713ad3170ae18d4c9) for more detailed information about these functions.

## API Reference

* [中文](http://u.720life.cn/g/277253dc8bbf9e7678a39b9da116d01c8c88ae33ced63ffad0a2c91fe5b0ccee)
* [English](http://u.720life.cn/g/954acd2a13e84fa86d1adc7b55a3d3afa3a255ac1c79ccb9b52c757e71a89e78e1b9d4516d37f8bb05389523ba6c1894b5c29bf265e3e8663289c5ee0ca7fe599cfe48261c5b02d856efab89ab691b3b)

## Related Projects

* [SwooleFramework](http://u.720life.cn/g/54145d0471d91890860f7f8463c030464ebbed3a87ace3cf55fb4a3bd5a213ef8013ada5ca2e00b1c1026c30d006a0a9) Web framework powered by Swoole

## Contribution

Your contribution to Swoole development is very welcome!

You may contribute in the following ways:

* [Repost issues and feedback](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046b8f1e94ae6b0683db830a7d4a6b0f3b2cbad0689eb9cdb594f0ba26c35cb7cef)
* Submit fixes, features via Pull Request
* Write/polish documentation

## License

Apache License Version 2.0 see http://www.apache.org/licenses/LICENSE-2.0.html



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ecba01206125068c59d421914d9099c42efa7a143e5ea9858aab742c2d8597cab10850b04fc13fd87dd79681e606ad1bf)