# Workerman
[![Gitter](https://badges.gitter.im/walkor/Workerman.svg)](https://gitter.im/walkor/Workerman?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=body_badge)

## What is it
Workerman is a library for event-driven programming in PHP. It has a huge number of features. Each worker is able to handle thousands of connections.

## Requires

PHP 5.3 or Higher  
A POSIX compatible operating system (Linux, OSX, BSD)  
POSIX and PCNTL extensions for PHP  

## Installation

```
composer require workerman/workerman
```

## Basic Usage

### A websocket server 
test.php
```php
 count = 4;

// Emitted when new connection come
$ws_worker->onConnect = function($connection)
{
    echo "New connection\n";
 };

// Emitted when data received
$ws_worker->onMessage = function($connection, $data)
{
    // Send hello $data
    $connection->send('hello ' . $data);
};

// Emitted when connection closed
$ws_worker->onClose = function($connection)
{
    echo "Connection closed\n";
};

// Run worker
Worker::runAll();
```

### An http server
test.php
```php
require_once './Workerman/Autoloader.php';
use Workerman\Worker;

// #### http worker ####
$http_worker = new Worker("http://0.0.0.0:2345");

// 4 processes
$http_worker->count = 4;

// Emitted when data received
$http_worker->onMessage = function($connection, $data)
{
    // $_GET, $_POST, $_COOKIE, $_SESSION, $_SERVER, $_FILES are available
    var_dump($_GET, $_POST, $_COOKIE, $_SESSION, $_SERVER, $_FILES);
    // send data to client
    $connection->send("hello world \n");
};

// run all workers
Worker::runAll();
```

### A WebServer
test.php
```php
require_once './Workerman/Autoloader.php';
use Workerman\WebServer;

// WebServer
$web = new WebServer("http://0.0.0.0:80");

// 4 processes
$web->count = 4;

// Set the root of domains
$web->addRoot('www.your_domain.com', '/your/path/Web');
$web->addRoot('www.another_domain.com', '/another/path/Web');
// run all workers
Worker::runAll();
```

### A tcp server
test.php
```php
require_once './Workerman/Autoloader.php';
use Workerman\Worker;

// #### create socket and listen 1234 port ####
$tcp_worker = new Worker("tcp://0.0.0.0:1234");

// 4 processes
$tcp_worker->count = 4;

// Emitted when new connection come
$tcp_worker->onConnect = function($connection)
{
    echo "New Connection\n";
};

// Emitted when data received
$tcp_worker->onMessage = function($connection, $data)
{
    // send data to client
    $connection->send("hello $data \n");
};

// Emitted when new connection come
$tcp_worker->onClose = function($connection)
{
    echo "Connection closed\n";
};

Worker::runAll();
```

### Custom protocol
Protocols/MyTextProtocol.php
```php
namespace Protocols;
/**
 * User defined protocol
 * Format Text+"\n"
 */
class MyTextProtocol
{
    public static function input($recv_buffer)
    {
        // Find the position of the first occurrence of "\n"
        $pos = strpos($recv_buffer, "\n");
        // Not a complete package. Return 0 because the length of package can not be calculated
        if($pos === false)
        {
            return 0;
        }
        // Return length of the package
        return $pos+1;
    }

    public static function decode($recv_buffer)
    {
        return trim($recv_buffer);
    }

    public static function encode($data)
    {
        return $data."\n";
    }
}
```

test.php
```php
require_once './Workerman/Autoloader.php';
use Workerman\Worker;

// #### MyTextProtocol worker ####
$text_worker = new Worker("MyTextProtocol://0.0.0.0:5678");

$text_worker->onConnect = function($connection)
{
    echo "New connection\n";
};

$text_worker->onMessage =  function($connection, $data)
{
    // send data to client
    $connection->send("hello world \n");
};

$text_worker->onClose = function($connection)
{
    echo "Connection closed\n";
};

// run all workers
Worker::runAll();
```

### Timer
test.php
```php
require_once './Workerman/Autoloader.php';
use Workerman\Worker;
use Workerman\Lib\Timer;

$task = new Worker();
$task->onWorkerStart = function($task)
{
    // 2.5 seconds
    $time_interval = 2.5; 
    $timer_id = Timer::add($time_interval, 
        function()
        {
            echo "Timer run\n";
        }
    );
};

// run all workers
Worker::runAll();
```

run with:

```php test.php start```

## Available commands
```php test.php start  ```  
```php test.php start -d  ```  
![workerman start](http://www.workerman.net/img/workerman-start.png)  
```php test.php status  ```  
![workerman satus](http://www.workerman.net/img/workerman-status.png?a=123)
```php test.php stop  ```  
```php test.php restart  ```  
```php test.php reload  ```  

## Documentation

中文主页:[http://www.workerman.net](http://u.720life.cn/g/ada3e9e82fa778691969d36f55ae5c11f15cac51801f9494b6ece67e3e4fe424)

中文文档: [http://doc3.workerman.net](http://u.720life.cn/g/73543cf1d0ebc1fe82ab0b39e1d72dd0115063b27bc84778e5271357eede8821)

Documentation:[https://github.com/walkor/workerman-manual](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304688057b8f59fd3e02f3e24b2982fb6d7fda94d5719f1ee9f4559f3da1c424fabbbb191548571abba0f7d8fc1f6468d57f78c9717d55974039730fde064ccbb9fe)

# Benchmarks
```
CPU:      Intel(R) Core(TM) i3-3220 CPU @ 3.30GHz and 4 processors totally
Memory:   8G
OS:       Ubuntu 14.04 LTS
Software: ab
PHP:      5.5.9
```

**Codes**
```php
 count=3;
$worker->onMessage = function($connection, $data)
{
    $connection->send("HTTP/1.1 200 OK\r\nConnection: keep-alive\r\nServer: workerman\r\nContent-Length: 5\r\n\r\nhello");
};
Worker::runAll();
```
**Result**

```shell
ab -n1000000 -c100 -k http://127.0.0.1:1234/
This is ApacheBench, Version 2.3  
Copyright 1996 Adam Twiss, Zeus Technology Ltd, http://www.zeustech.net/
Licensed to The Apache Software Foundation, http://www.apache.org/

Benchmarking 127.0.0.1 (be patient)
Completed 100000 requests
Completed 200000 requests
Completed 300000 requests
Completed 400000 requests
Completed 500000 requests
Completed 600000 requests
Completed 700000 requests
Completed 800000 requests
Completed 900000 requests
Completed 1000000 requests
Finished 1000000 requests


Server Software:        workerman/3.1.4
Server Hostname:        127.0.0.1
Server Port:            1234

Document Path:          /
Document Length:        5 bytes

Concurrency Level:      100
Time taken for tests:   7.240 seconds
Complete requests:      1000000
Failed requests:        0
Keep-Alive requests:    1000000
Total transferred:      73000000 bytes
HTML transferred:       5000000 bytes
Requests per second:    138124.14 [#/sec] (mean)
Time per request:       0.724 [ms] (mean)
Time per request:       0.007 [ms] (mean, across all concurrent requests)
Transfer rate:          9846.74 [Kbytes/sec] received

Connection Times (ms)
              min  mean[+/-sd] median   max
Connect:        0    0   0.0      0       5
Processing:     0    1   0.2      1       9
Waiting:        0    1   0.2      1       9
Total:          0    1   0.2      1       9

Percentage of the requests served within a certain time (ms)
  50%      1
  66%      1
  75%      1
  80%      1
  90%      1
  95%      1
  98%      1
  99%      1
 100%      9 (longest request)

```


# Demos

## [tadpole](http://u.720life.cn/g/f0a574b6da1262627ffc6020df85368abc0f60177162bb135613b2403c6a6f4e)  
[Live demo](http://u.720life.cn/g/f0a574b6da1262627ffc6020df85368abc0f60177162bb135613b2403c6a6f4e)  
[Source code](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304688057b8f59fd3e02f3e24b2982fb6d7f4f648349f6efe8c3e76e145bb08a338e)  
![workerman todpole](http://www.workerman.net/img/workerman-todpole.png)  

## [BrowserQuest](http://u.720life.cn/g/ada3e9e82fa778691969d36f55ae5c11c6574396f7229428d0fd9b80d724998e1121156ac1e7112eeec652e68dd5fabf)   
[Live demo](http://u.720life.cn/g/ada3e9e82fa778691969d36f55ae5c11c6574396f7229428d0fd9b80d724998e1121156ac1e7112eeec652e68dd5fabf)  
[Source code](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046246fd98bae108aa1c94b99d45966c1ff45b8a62ded61a66f0f61b1ce8cfffd2d)  
![BrowserQuest width workerman](http://www.workerman.net/img/browserquest.jpg) 

## [web vmstat](http://u.720life.cn/g/ada3e9e82fa778691969d36f55ae5c11ac062d7ac159bf82b48a1d1e9c73145092e318204196ece315db053b81d5599b)   
[Live demo](http://u.720life.cn/g/ada3e9e82fa778691969d36f55ae5c11ac062d7ac159bf82b48a1d1e9c73145092e318204196ece315db053b81d5599b)  
[Source code](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304688057b8f59fd3e02f3e24b2982fb6d7f78535e58eccc507d100a118a9498377f)  
![web vmstat](http://www.workerman.net/img/workerman-vmstat.png)   

## [live-ascii-camera](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046802098d083184f356b473cb2e9a465c3d30e8d455db54c18e68777ebc389a41a)   
[Live demo camera page](http://u.720life.cn/g/ada3e9e82fa778691969d36f55ae5c11521898cfcc1ae69ed7d296c5bf977062372319aebc974a830fb4739d8a96d7a86213fd41f6aa088f3ec54cee2abdf167)  
[Live demo receive page](http://u.720life.cn/g/ada3e9e82fa778691969d36f55ae5c11521898cfcc1ae69ed7d296c5bf977062372319aebc974a830fb4739d8a96d7a8af099f4144c00ed7cf5f39810ca5f138)  
[Source code](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046802098d083184f356b473cb2e9a465c3d30e8d455db54c18e68777ebc389a41a)  
![live-ascii-camera](http://www.workerman.net/img/live-ascii-camera.png)   

## [live-camera](http://u.720life.cn/g/54145d0471d91890860f7f8463c030467852ec141d5c47333b4c23a5730eb2de3be9f96ac1b952d9de9d39144a159500)   
[Live demo camera page](http://u.720life.cn/g/ada3e9e82fa778691969d36f55ae5c11521898cfcc1ae69ed7d296c5bf97706282d254df93526f5d7443ecfc0ca6d90c9a96f68128c79fef7d94d61f3d495ed6)  
[Live demo receive page](http://u.720life.cn/g/ada3e9e82fa778691969d36f55ae5c11521898cfcc1ae69ed7d296c5bf977062848740c2dcac8b2e7719778af3b25a20)  
[Source code](http://u.720life.cn/g/54145d0471d91890860f7f8463c030467852ec141d5c47333b4c23a5730eb2de3be9f96ac1b952d9de9d39144a159500)  
![live-camera](http://www.workerman.net/img/live-camera.jpg)  

## [chat room](http://u.720life.cn/g/21b47f3db1811b46e6fd484a9a2c749e4256e205fc10b9971d9570bc7af5491f)  
[Live demo](http://u.720life.cn/g/21b47f3db1811b46e6fd484a9a2c749e4256e205fc10b9971d9570bc7af5491f)  
[Source code](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304688057b8f59fd3e02f3e24b2982fb6d7fa0c2aed5fdd8c746071e819e28401ce3)  
![workerman-chat](http://www.workerman.net/img/workerman-chat.png)  

## [PHPSocket.IO](http://u.720life.cn/g/54145d0471d91890860f7f8463c030468c831ced5a91d00b3bd29a29da43a4f57268698cafe1ff7b25e50b7eedf1d059)  
[Live demo](http://u.720life.cn/g/ada3e9e82fa778691969d36f55ae5c11e9c11e78fc9fd9479612297917f72aa20e3b2038db403c8b78ab241073de466a)  
[Source code](http://u.720life.cn/g/54145d0471d91890860f7f8463c030468c831ced5a91d00b3bd29a29da43a4f57268698cafe1ff7b25e50b7eedf1d059)  
![phpsocket.io](http://www.workerman.net/img/socket.io.png)  

## [statistics](http://u.720life.cn/g/ada3e9e82fa778691969d36f55ae5c112dfb0276d38b514c01758635ec34cb27)  
[Live demo](http://u.720life.cn/g/ada3e9e82fa778691969d36f55ae5c112dfb0276d38b514c01758635ec34cb27)  
[Source code](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304688057b8f59fd3e02f3e24b2982fb6d7f24e331d66c59200199b12d98f01b8add)  
![workerman-statistics](http://www.workerman.net/img/workerman-statistics.png)  

## [flappybird](http://u.720life.cn/g/905fa6e071b0372124ee7032dbaf56567108db211a5b9ff17a11c76fb5e3c2da75360cec4860e27a48a631226f2a6ae3)  
[Live demo](http://u.720life.cn/g/905fa6e071b0372124ee7032dbaf56567108db211a5b9ff17a11c76fb5e3c2da75360cec4860e27a48a631226f2a6ae3)  
[Source code](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304688057b8f59fd3e02f3e24b2982fb6d7f9908cd31876a6bfa90b0cd4c8b8b5a52)  
![workerman-statistics](http://www.workerman.net/img/workerman-flappy-bird.png)  

## [jsonRpc](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304688057b8f59fd3e02f3e24b2982fb6d7f8d4d3a5a00ab43e7e78b35eddd2129a6)  
[Source code](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304688057b8f59fd3e02f3e24b2982fb6d7f8d4d3a5a00ab43e7e78b35eddd2129a6)  
![workerman-jsonRpc](http://www.workerman.net/img/workerman-json-rpc.png)  

## [thriftRpc](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304688057b8f59fd3e02f3e24b2982fb6d7fd5e8a0364fc696d45cdc946494f82ed9)  
[Source code](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304688057b8f59fd3e02f3e24b2982fb6d7fd5e8a0364fc696d45cdc946494f82ed9)  
![workerman-thriftRpc](http://www.workerman.net/img/workerman-thrift.png)  

## [web-msg-sender](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046b257c5d986770439613cc9972687c321b382f787ed78b4bf756a69e3d3276cbe)  
[Live demo send page](http://u.720life.cn/g/905fa6e071b0372124ee7032dbaf5656a4d579fad42536b9dc8cd288cfbcd9e3)  
[Live demo receive page](http://u.720life.cn/g/905fa6e071b0372124ee7032dbaf5656e4faab5a0098b0a615376dc289ced8ef6e37917cf185622f6d3bd0895d296715)  
[Source code](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046b257c5d986770439613cc9972687c321b382f787ed78b4bf756a69e3d3276cbe)  
![web-msg-sender](http://www.workerman.net/img/web-msg-sender.png)  

## [shadowsocks-php](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304691fbcd54d27c435ca288ff69a794b44827a2f10ad3b53c06420b94847518da1d)
[Source code](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304691fbcd54d27c435ca288ff69a794b44827a2f10ad3b53c06420b94847518da1d)  
![shadowsocks-php](http://www.workerman.net/img/shadowsocks-php.png)  

## [queue](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304688057b8f59fd3e02f3e24b2982fb6d7f7f24b630c16262e84138374543e2def2)
[Source code](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304688057b8f59fd3e02f3e24b2982fb6d7f7f24b630c16262e84138374543e2def2)  

## LICENSE

Workerman is released under the [MIT license](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304688057b8f59fd3e02f3e24b2982fb6d7f7cc5b1f577dd00152960b8dd1436681449c3ee4476cf08a5f134c3ae979a2854).



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e1ae5155a38f181ea2e89da52c4f289067ef3c2a92d23a829143898cdb6435ad8a014a958f308a5e21aeccf843bb388b1)