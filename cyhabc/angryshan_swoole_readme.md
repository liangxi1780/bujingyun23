English | [中文](./README-CN.md)

Swoole
======
[![Latest Version](https://img.shields.io/github/release/swoole/swoole-src.svg?style=flat-square)](https://github.com/swoole/swoole-src/releases)
[![Build Status](https://api.travis-ci.org/swoole/swoole-src.svg)](https://travis-ci.org/swoole/swoole-src)
[![License](https://img.shields.io/badge/license-apache2-blue.svg)](LICENSE)
[![Join the chat at https://gitter.im/swoole/swoole-src](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/swoole/swoole-src?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)
[![Coverity Scan Build Status](https://scan.coverity.com/projects/11654/badge.svg)](https://scan.coverity.com/projects/swoole-swoole-src)
[![Backers on Open Collective](https://opencollective.com/swoole-src/backers/badge.svg)](#backers) 
[![Sponsors on Open Collective](https://opencollective.com/swoole-src/sponsors/badge.svg)](#sponsors) 

![](./mascot.png)

**Swoole is an event-driven asynchronous & coroutine-based concurrency networking communication engine with high performance written in C and C++ for PHP.**

## ✨Event-based

The network layer in Swoole is event-based and takes full advantage of the underlying epoll/kqueue implementation, making it really easy to serve millions of requests.


Swoole 4.x use a brand new engine kernel and now it has a full-time developer team, so we are entering an unprecedented period in PHP history which offers a unique possibility for rapid evolution in performance.

## ⚡️Coroutine

Swoole 4.x or later supports the built-in coroutine with high availability, and you can use fully synchronized code to implement asynchronous performance. PHP code without any additional keywords, the underlying automatic coroutine-scheduling.

Developers can understand coroutines as ultra-lightweight threads, and you can easily create thousands of coroutines in a single process.

### MySQL

Concurrency 10K requests to read data from MySQL takes only 0.2s!

```php
$s = microtime(true);
for ($c = 100; $c--;) {
    go(function () {
        $mysql = new Swoole\Coroutine\MySQL;
        $mysql->connect([
            'host' => '127.0.0.1',
            'user' => 'root',
            'password' => 'root',
            'database' => 'test'
        ]);
        $statement = $mysql->prepare('SELECT * FROM `user`');
        for ($n = 100; $n--;) {
            $result = $statement->execute();
            assert(count($result) > 0);
        }
    });
}
Swoole\Event::wait();
echo 'use ' . (microtime(true) - $s) . ' s';
```

### Mixed server

You can create multiple services on the single event loop: TCP, HTTP, Websocket and HTTP2, and easily handle thousands of requests.

```php
function tcp_pack(string $data): string
{
    return pack('n', strlen($data)) . $data;
}
function tcp_unpack(string $data): string
{
    return substr($data, 2, unpack('n', substr($data, 0, 2))[1]);
}
$tcp_options = [
    'open_length_check' => true,
    'package_length_type' => 'n',
    'package_length_offset' => 0,
    'package_body_offset' => 2
];
```

```php
$server = new Swoole\WebSocket\Server('127.0.0.1', 9501, SWOOLE_BASE);
$server->set(['open_http2_protocol' => true]);
// http && http2
$server->on('request', function (Swoole\Http\Request $request, Swoole\Http\Response $response) {
    $response->end('Hello ' . $request->rawcontent());
});
// websocket
$server->on('message', function (Swoole\WebSocket\Server $server, Swoole\WebSocket\Frame $frame) {
    $server->push($frame->fd, 'Hello ' . $frame->data);
});
// tcp
$tcp_server = $server->listen('127.0.0.1', 9502, SWOOLE_TCP);
$tcp_server->set($tcp_options);
$tcp_server->on('receive', function (Swoole\Server $server, int $fd, int $reactor_id, string $data) {
    $server->send($fd, tcp_pack('Hello ' . tcp_unpack($data)));
});
$server->start();
```

### Coroutine clients

Whether you DNS query or send requests or receive responses, all of these are scheduled by coroutine automatically.

```php
go(function () {
    // http
    $http_client = new Swoole\Coroutine\Http\Client('127.0.0.1', 9501);
    assert($http_client->post('/', 'Swoole Http'));
    var_dump($http_client->body);
    // websocket
    $http_client->upgrade('/');
    $http_client->push('Swoole Websocket');
    var_dump($http_client->recv()->data);
});
go(function () {
    // http2
    $http2_client = new Swoole\Coroutine\Http2\Client('localhost', 9501);
    $http2_client->connect();
    $http2_request = new Swoole\Http2\Request;
    $http2_request->method = 'POST';
    $http2_request->data = 'Swoole Http2';
    $http2_client->send($http2_request);
    $http2_response = $http2_client->recv();
    var_dump($http2_response->data);
});
go(function () use ($tcp_options) {
    // tcp
    $tcp_client = new Swoole\Coroutine\Client(SWOOLE_TCP);
    $tcp_client->set($tcp_options);
    $tcp_client->connect('127.0.0.1', 9502);
    $tcp_client->send(tcp_pack('Swoole Tcp'));
    var_dump(tcp_unpack($tcp_client->recv()));
});
```

### Channel

Channel is the only way for exchanging data between coroutines, the development combination of the `Coroutine + Channel` is the famous CSP programming model.

In Swoole development, Channel is usually used for implementing connection pool or scheduling coroutine concurrent.

#### The simplest example of a connection pool

In the following example, we have a thousand concurrently requests to redis. Normally, this has exceeded the maximum number of Redis connections setting and will throw a connection exception, but the connection pool based on Channel can perfectly schedule requests. We don't have to worry about connection overload.

```php
class RedisPool
{
    /**@var \Swoole\Coroutine\Channel */
    protected $pool;

    /**
     * RedisPool constructor.
     * @param int $size max connections
     */
    public function __construct(int $size = 100)
    {
        $this->pool = new \Swoole\Coroutine\Channel($size);
        for ($i = 0; $i  connect('127.0.0.1', 6379);
            if ($res == false) {
                throw new \RuntimeException("failed to connect redis server.");
            } else {
                $this->put($redis);
            }
        }
    }

    public function get(): \Swoole\Coroutine\Redis
    {
        return $this->pool->pop();
    }

    public function put(\Swoole\Coroutine\Redis $redis)
    {
        $this->pool->push($redis);
    }

    public function close(): void
    {
        $this->pool->close();
        $this->pool = null;
    }
}

go(function () {
    $pool = new RedisPool();
    // max concurrency num is more than max connections
    // but it's no problem, channel will help you with scheduling
    for ($c = 0; $c  get();
                assert($redis->set("awesome-{$c}-{$n}", 'swoole'));
                assert($redis->get("awesome-{$c}-{$n}") === 'swoole');
                assert($redis->delete("awesome-{$c}-{$n}"));
                $pool->put($redis);
            }
        });
    }
});
```

#### Producer and consumers

Some Swoole's clients implement the defer mode for concurrency, but you can still implement it flexible with a combination of coroutines and channels.

```php
go(function () {
    // User: I need you to bring me some information back.
    // Channel: OK! I will be responsible for scheduling.
    $channel = new Swoole\Coroutine\Channel;
    go(function () use ($channel) {
        // Coroutine A: Ok! I will show you the github addr info
        $addr_info = Co::getaddrinfo('github.com');
        $channel->push(['A', json_encode($addr_info, JSON_PRETTY_PRINT)]);
    });
    go(function () use ($channel) {
        // Coroutine B: Ok! I will show you what your code look like
        $mirror = Co::readFile(__FILE__);
        $channel->push(['B', $mirror]);
    });
    go(function () use ($channel) {
        // Coroutine C: Ok! I will show you the date
        $channel->push(['C', date(DATE_W3C)]);
    });
    for ($i = 3; $i--;) {
        list($id, $data) = $channel->pop();
        echo "From {$id}:\n {$data}\n";
    }
    // User: Amazing, I got every information at earliest time!
});
```

### Timer

```php
$id = Swoole\Timer::tick(100, function () {
    echo "⚙️ Do something...\n";
});
Swoole\Timer::after(500, function () use ($id) {
    Swoole\Timer::clear($id);
    echo "⏰ Done\n";
});
Swoole\Timer::after(1000, function () use ($id) {
    if (!Swoole\Timer::exists($id)) {
        echo "✅ All right!\n";
    }
});
```
#### The way of coroutine

```php
go(function () {
    $i = 0;
    while (true) {
        Co::sleep(0.1);
        echo "📝 Do something...\n";
        if (++$i === 5) {
            echo "🛎 Done\n";
            break;
        }
    }
    echo "🎉 All right!\n";
});
```

## 🔥 Amazing runtime hooks

**In the latest version of Swoole, we have added a new feature to make sync PHP network libraires to be coroutine libraires with only one line of code.**

Just call `Swoole\Runtime::enableCoroutine()` method on the top of the script and use php-redis, 10K concurrent requests reading data from Redis takes only 0.1s!

```php
Swoole\Runtime::enableCoroutine();
$s = microtime(true);
for ($c = 100; $c--;) {
    go(function () {
        ($redis = new Redis)->connect('127.0.0.1', 6379);
        for ($n = 100; $n--;) {
            assert($redis->get('awesome') === 'swoole');
        }
    });
}
Swoole\Event::wait();
echo 'use ' . (microtime(true) - $s) . ' s';
```

After you call it, the Swoole kernel will replace the function pointers of streams in ZendVM, if you use `php_stream` based extensions, all socket operations can be dynamically converted to be asynchronous IO scheduled by coroutine at runtime.

### How many things you can do in 1s?

Sleep 10K times, read, write, check and delete files 10K times, use PDO and MySQLi to communicate with the database 10K times, create a TCP server and multiple clients to communicate with each other 10K times, create a UDP server and multiple clients to communicate with each other 10K times... Everything works well in one process!

Just see what the Swoole brings, just imagine...

```php
Swoole\Runtime::enableCoroutine();
$s = microtime(true);

// i just want to sleep...
for ($c = 100; $c--;) {
    go(function () {
        for ($n = 100; $n--;) {
            usleep(1000);
        }
    });
}

// 10K file read and write
for ($c = 100; $c--;) {
    go(function () use ($c) {
        $tmp_filename = "/tmp/test-{$c}.php";
        for ($n = 100; $n--;) {
            $self = file_get_contents(__FILE__);
            file_put_contents($tmp_filename, $self);
            assert(file_get_contents($tmp_filename) === $self);
        }
        unlink($tmp_filename);
    });
}

// 10K pdo and mysqli read
for ($c = 50; $c--;) {
    go(function () {
        $pdo = new PDO('mysql:host=127.0.0.1;dbname=test;charset=utf8', 'root', 'root');
        $statement = $pdo->prepare('SELECT * FROM `user`');
        for ($n = 100; $n--;) {
            $statement->execute();
            assert(count($statement->fetchAll()) > 0);
        }
    });
}
for ($c = 50; $c--;) {
    go(function () {
        $mysqli = new Mysqli('127.0.0.1', 'root', 'root', 'test');
        $statement = $mysqli->prepare('SELECT `id` FROM `user`');
        for ($n = 100; $n--;) {
            $statement->bind_result($id);
            $statement->execute();
            $statement->fetch();
            assert($id > 0);
        }
    });
}

// php_stream tcp server & client with 12.8K requests in single process
function tcp_pack(string $data): string
{
    return pack('n', strlen($data)) . $data;
}

function tcp_length(string $head): int
{
    return unpack('n', $head)[1];
}

go(function () {
    $ctx = stream_context_create(['socket' => ['so_reuseaddr' => true, 'backlog' => 128]]);
    $socket = stream_socket_server(
        'tcp://0.0.0.0:9502',
        $errno, $errstr, STREAM_SERVER_BIND | STREAM_SERVER_LISTEN, $ctx
    );
    if (!$socket) {
        echo "$errstr ($errno)\n";
    } else {
        $i = 0;
        while ($conn = stream_socket_accept($socket, 1)) {
            stream_set_timeout($conn, 5);
            for ($n = 100; $n--;) {
                $data = fread($conn, tcp_length(fread($conn, 2)));
                assert($data === "Hello Swoole Server #{$n}!");
                fwrite($conn, tcp_pack("Hello Swoole Client #{$n}!"));
            }
            if (++$i === 128) {
                fclose($socket);
                break;
            }
        }
    }
});
for ($c = 128; $c--;) {
    go(function () {
        $fp = stream_socket_client("tcp://127.0.0.1:9502", $errno, $errstr, 1);
        if (!$fp) {
            echo "$errstr ($errno)\n";
        } else {
            stream_set_timeout($fp, 5);
            for ($n = 100; $n--;) {
                fwrite($fp, tcp_pack("Hello Swoole Server #{$n}!"));
                $data = fread($fp, tcp_length(fread($fp, 2)));
                assert($data === "Hello Swoole Client #{$n}!");
            }
            fclose($fp);
        }
    });
}

// udp server & client with 12.8K requests in single process
go(function () {
    $socket = new Swoole\Coroutine\Socket(AF_INET, SOCK_DGRAM, 0);
    $socket->bind('127.0.0.1', 9503);
    $client_map = [];
    for ($c = 128; $c--;) {
        for ($n = 0; $n  recvfrom($peer);
            $client_uid = "{$peer['address']}:{$peer['port']}";
            $id = $client_map[$client_uid] = ($client_map[$client_uid] ?? -1) + 1;
            assert($recv === "Client: Hello #{$id}!");
            $socket->sendto($peer['address'], $peer['port'], "Server: Hello #{$id}!");
        }
    }
    $socket->close();
});
for ($c = 128; $c--;) {
    go(function () {
        $fp = stream_socket_client("udp://127.0.0.1:9503", $errno, $errstr, 1);
        if (!$fp) {
            echo "$errstr ($errno)\n";
        } else {
            for ($n = 0; $n   As with any open source project, Swoole always provides the most reliable stability and the most powerful features in **the latest released version**. Please ensure as much as possible that you are using the latest version.

### 1. From binary package (beginners + dev-env)

See our [download page](http://u.720life.cn/g/ea77b905e9f2cc0fcf482fd7805be67befe95350591539b595cca641d40974207efcb24d3cf8bc9edaef0ef928108eb5)

### Compiling requirements

- Linux, OS X or Cygwin, WSL
- PHP 7.0.0 or later (The higher the version, the better the performance.)
- GCC 4.8 or later

### 2. Install via PECL (beginners)

```shell
pecl install swoole
```

### 3. Install from source (recommended)

Please download the source packages from [Releases](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046b8f1e94ae6b0683db830a7d4a6b0f3b23a4c1d28f39938046eba51d1c6c6f79b) or:

```shell
git clone https://github.com/swoole/swoole-src.git && \
cd swoole-src && \
git checkout v4.x.x
```

Compile and install at the source folder:

```shell
phpize && \
./configure && \
make && make install
```

#### Enable extension in PHP

After compiling and installing to the system successfully, you have to add a new line `extension=swoole.so` to `php.ini` to enable Swoole extension.

#### Extra compiler configurations

> for example: `./configure --enable-openssl --enable-sockets`

- `--enable-openssl` or `--with-openssl-dir=DIR`
- `--enable-sockets`
- `--enable-http2`
- `--enable-mysqlnd` (need mysqlnd, it just for supporting `$mysql->escape` method)

### Upgrade

>  ⚠️ If you upgrade from source, don't forget to `make clean` before you upgrade your swoole

1. `pecl upgrade swoole`
2. `git pull && cd swoole-src && make clean && make && sudo make install`
3. if you change your PHP version, please re-run `phpize clean && phpize` then try to compile


### Major change since version 4.3.0

Async clients and API are moved to a separate PHP extension `swoole_async` since version 4.3.0, install `swoole_async`:

```shell
git clone https://github.com/swoole/async-ext.git
cd async-src
phpize
./configure
make -j 4
sudo make install
```

Enable it by adding a new line `extension=swoole_async.so` to `php.ini`.

## 💎 Frameworks & Components

- [**Swoft**](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046abc4198f224edb32c0d76dcdf98f52e7) is a modern, high-performance AOP and coroutine PHP framework.
- [**Easyswoole**](http://u.720life.cn/g/7d86ea14028eb786983796b83d5904655f58091e219deaf1b242b4337e1da0e9) EasySwoole is a distributed, persistent memory PHP framework based on the Swoole extension. It was created specifically for APIs to get rid of the performance penalties associated with process calls and file loading. EasySwoole highly encapsulates the Swoole Server and still maintains the original features of the Swoole server, supports simultaneous monitoring of HTTP, custom TCP, and UDP protocols, allowing developers to write multi-process, asynchronous, and highly available applications with minimal learning cost and effort.
    - Base on Swoole extension
    - Built-in HTTP, TCP, WebSocket,Udp Coroutine Server
    - Global dependency injection container
    - PSR-7 based HTTP message implementation
    - HTTP,TCP, WebSocket, Udp middleware support
    - Scalable high performance RPC
    - Database ORM
    - Mysql, Redis, RPC, HTTP Coroutine Clients
    - Coroutine and asynchronous task delivery
    - Custom user processes
    - RESTful supported
    - High performance router
    - Fast and flexible parameter validator
    - Powerful log component
    - Universal connection pools
    - Remote Console support
    - Crontab Rule Timer support
- [**Saber**](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304649f709fb68e6c2917df4ae3f142b208a) Is a human-friendly, high-performance HTTP client component that has almost everything you can imagine.

## 🛠 Develop & Discussion

* __中文文档__:  
* __Documentation__:  
* __IDE Helper & API__:  
* __中文社区__:  
* __Twitter__:  
* __Slack Group__:  

## 🍭 Benchmark

+ On the open source [Techempower Web Framework benchmarks](http://u.720life.cn/g/587984922c2f36564b2cfde7aef7be58c9f8d9d505fad061d9f4529d1ab040f2215a2e4b2c4950e1409e8c576581599805e6fc259e0739c3c00a9925369ebae7) Swoole used MySQL database benchmark to rank first, and all performance tests ranked in the first echelon.
+ You can just run [Benchmark Script](./benchmark/benchmark.php) to quickly test the maximum QPS of Swoole-HTTP-Server on your machine.

## 🖊️ Security issues

Security issues should be reported privately, via email, to the Swoole develop team team@swoole.com. You should receive a response within 24 hours. If for some reason you do not, please follow up via email to ensure we received your original message.

## 🖊️ Contribution

Your contribution to Swoole development is very welcome!

You may contribute in the following ways:

* [Report issues and feedback](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046b8f1e94ae6b0683db830a7d4a6b0f3b2cbad0689eb9cdb594f0ba26c35cb7cef)
* Submit fixes, features via Pull Request
* Write/polish documentation

## ❤️ Contributors

This project exists thanks to all the people who contribute. [[Contributors](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046b8f1e94ae6b0683db830a7d4a6b0f3b292509db2d32e933a64ca09ae249084d5b741ad7f8e2ea356f15c3f75f8e552a4)].
   

## 🎙️ Official Evangelist

[Demin](http://u.720life.cn/g/a4d71ff257b2ed284e26eb7dc8b3a5941c80d84dd41616043dea0bfdc0c07c52) has been playing with PHP since 2000, focusing on building high-performance, secure web services. He is an occasional conference speaker on PHP and Swoole, and has been working for companies in the states like eBay, Visa and Glu Mobile for years. You may find Demin on [Twitter](http://u.720life.cn/g/5ea88169c4a0fbd169233d52478d54fe64b18dd946d093958226cee82efc82c8) or [GitHub](http://u.720life.cn/g/54145d0471d91890860f7f8463c030466621b3e8eea2da1c5e70bf3d32370ec9).

## 📃 License

Apache License Version 2.0 see http://www.apache.org/licenses/LICENSE-2.0.html



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e56be0ed9e1a1840a4239755bdef65890deb0cc3dd9e941b7e7ae27c8d0748af216adf6b3c2247f74cc665ab8c7f1a307)