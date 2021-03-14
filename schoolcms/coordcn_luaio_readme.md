# [LuaIO](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046b52929497f60ec97f909fd31e82915c5)
http server base on lua + libuv

项目灵感来自[fibjs](http://u.720life.cn/g/3e67e6abb5e341dc20d8e6226451e0464c19745d2e5822d2c944161398a550d3)和[openresty]http://openresty.org/

参考：
+  [nginx](http://u.720life.cn/g/8e5d45d2feb3582a8a09a3bac21cb32b9f0f4bc92470f7cc858ee4a1dafaf5ef)
+  [io.js](http://u.720life.cn/g/5281e776604544bdc4b27e692d4f3b53b38de2cf366f6e10d039f8447d02a554)
+  [openresty](http://u.720life.cn/g/847a7658f2aaf9f3bf6ef90149776062311ace00ef6a0e2691c4dea8c2670f47)
+  [luvit](http://u.720life.cn/g/56df4e9cb59d39a85dbe874e9a5b6f8711e90c4b211466706c275af0c08a208b)
+  [aLiLua](http://u.720life.cn/g/cfb191c0d1d4754b8e2e4d69190a7bdf67178b7511be24d686ae421d5a600139)
+  [luajit.io](http://u.720life.cn/g/50eee8f6f72d76f44626c5e9f19cbbb79e50c41e8d8a20aab7b74c2c35ede9e8)

实现目标：通过对coroutine包装实现同步代码编写异步程序，lua代码实现[形式同步]，c代码实现[实质异步]。

开发模式：需求驱动

##第一阶段工作：http1.1 预计三个月完成

## TODO
- bin2hex
- hex2bin
- base64.encode
- base64.decode
- base64.encodeURL
- base64.decodeURL
- crypto.hash
- crypto.hmac
- JSON.parse
- JSON.stringfy
- querystring
- escape
- unescape
- encodeURI
- decodeURI
- encodeURIComponent
- decodeURIComponent

###模块
####system

system.cpuinfo()
* @overview returns an array of all cpus informations. 
* @return {table[array(object)]}
```lua
  ret = {
    {
      model = '{string} Intel(R) Core(TM) i7 CPU860 @2.80GHz',
      speed = '{integer} [MHz]',
      times = {
        user = '{integer}',
	      nice = '{integer}',
        sys = '{integer}',
        idle = '{integer}',
        irq = '{integer}'
      } 
    },
    {
      model = '{string}',
      speed = '{integer}',
      times = {
        user = '{integer}',
	      nice = '{integer}',
        sys = '{integer}',
        idle = '{integer}',
        irq = '{integer}'
      } 
    }
  }
```

system.meminfo()
* @overview returns the total and free system memory in bytes.
* @return {table}
```lua
  ret = {
    total = '{integer} [bytes]',
    free = '{integer} [bytes]'
  }
```

system.loadavg()
* @overview returns an array containing the 1, 5, 15 minute load averages.
* @return {table[array(number)]}

system.hrtime()
* @overview returns the current high-resolution real time in nanoseconds.
* @return {integer} [nanoseconds]

system.uptime()
* @overview returns the system running time in seconds
* @return {number} [seconds]

####process

process.fork(options)
* @overview create a process and return the pid. 
* @param options {table}
```lua
  local options = {
    file = '{string} the file to run in the process',
    args = '{table[array(string)]} string arguments',
    uid = '{integer} the user identity of the process',
    gid = '{integer} the group identity of the process',
    forever = '{boolean} if true, the process will restart when it dies',
    cpu = '{integer} set the affinity of CPU and process',
    detached = '{boolean} if true, the child process will be made the leader of a new process group. This makes it possible for the child to continue running after the parent exits'
  }
```
* @return pid {integer}

process.exec(command)
* @overview create a new process and executive the command
* @param command {string}
* @return pid {integer}

process.cwd()
* @overview return the current working directory of the process
* @return cwd {string}

process.exit([signal])
* @overview end the process with the specified signal
* @param signal {integer|default:SIGTERM}

process.abort()
* @overview abort the process and generate a core file(if core file is open)

process.kill(pid[, signal])
* @overview send a signal to a process
* @param pid {integer}
* @param signal {integer|default:SIGTERM}

process.uptime()
* @overview return the process running time in seconds 
* @return {integer} [seconds]

####dns
dns.resolve4(hostname)
* @overvie resolve hostname(e.g. 'baidu.com') into an array of IPv4 address
* @param hostname {string}
* @return {table[array(string)]} ips array

dns.resolve6(hostname)
* @overvie resolve hostname(e.g. 'baidu.com') into an array of IPv6 address
* @param hostname {string}
* @return {table[array(string)]} ips array

####tcp
tcp.createServer(port, onconnect[, options])
* @overview create a new tcp server
* @param port {integer|required}
* @param onconnect {function|required}
```lua
  local function onconnect(socket, server)
  end
```
* @param options {table}
```lua
  local options = {
    family = '{integer|default: 4}',
    host = '{string|default: 0.0.0.0(::)}',
    timeout = '{integer|default: 0}',
    tcp_nodelay = '{boolean|default: true}',
    tcp_keepalive = '{boolean|default: true}',
    tcp_keepidle = '{integer|default: 0}',
    tcp_backlog = 'integer|default: 511}',
    tcp_reuseport = '{boolean|default: false}',
    read_buffer_size = '{integer|default: 16}',
    maxconnections = '{integer|default: 65535}'
  }
```

tcp.connect(port[, host, options])
* @overview connect to a host:port and return a new socket
* @param port {integer|required}
* @param host {string}
* @param options {table}
```lua
  local options = {
    family = '{integer|default: 4}',
    timeout = '{integer|default: 0}',
    tcp_nodelay = '{boolean|default: true}',
    tcp_keepalive = '{boolean|default: true}',
    tcp_keepidle = '{integer|default: 0}',
    read_buffer_size = '{integer|default: 16}'
  }
```
* @return {2}
  socket {table[object]}
  error {table}
```lua
  error = {
    code = '[integer] error code',
    name = '[string] error name',
    message = '[string] error message'
  }
```

tcp.isIP(address)
* @overview test if address is an IPv4 or IPv6 address
* @param address {string}
* @return {integer} IPv4: 4, IPv6: 6, not an address: 0

server:address()
* @overview return the local address of the server
* @return address {table}
```lua
  address = {
    family = '{integer}',
    port = '{integer}',
    address = '{string}'
  }
```

server:connections()
* @overview return the current connections of the server
* @return {integer}

server:close()
* @overview close the server

socket:read(n)
* @overview read n bytes data from read buffer
* @param n {integer} bytes
* @return {2}
  data {string}
  error {table}

socket:readline()
* @overview read a line data from read buffer
* @return {2}
  data {string}
  error {table}

socket:write(data)
* @overview send data to the socket
* @param data {string|table[array(string)]}
* @return {table}

socket:localAddress()
* @overview return the local address of the socket
* @return address {table}

socket:remoteAddress()
* @overview return the remote address of the socket
* @return address {table}

socket:setTimeout(timeout)
* @overview set timeout milliseconds of inactivity(no read and write) on the socket, when the socket timeout, socket:read(n), socket:readline(), socket:writ(data) will return an error
* @param timeout {integer} [milliseconds]

socket:setNodelay([enable])
* @overview enable/disable the nagle algorithm 
* @param enable {boolean|default: true}
* @return error {table}

socket:setKeepalive([enable][, idle])
* @overview enable/disable keep-alive functionality 
* @param enable {boolean|default: true}
* @parm idle {integer|default : 0} 
* @return error {table}

socket:end()
* @overview half close the socket, the socket write channel is shutdown
* @return error {table}

####http 进行中

####websocket

以下模块采用迭代开发模式，逐步完善

####log

####https

####redis

####mysql

####mongodb

####sequoiadb

##第二阶段工作：测试 预计两个月完成

####单元测试

####性能测试

##第三阶段工作：实例 结合实际情况开展项目，通过项目开发过程中出现的问题，形成需求，驱动links开发

####社区

####聊天

####游戏

##第四阶段工作：http2.0

####spdy3.0 看http2.0发展情况，如果http2.0推广的迅速就跳过这个阶段

####http2.0








 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ed6ec8019a502c58c1f99761aff1137fbd1279b7b0aa16ab9fcebbd5e418393ff148351e831a6c2963eb585dda90d44a6)