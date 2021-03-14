### My Fixes

1. In order to understand the code easily, I added many Debug/Trace log in source files.
2. Author used too many *this* pointer, which i don't think it's an appropriate coding habit.
3. I change folder fmt to submodule, which i think it's more suitable. By the way, library fmt wasn't often used in the code, perhaps we could remove it.

---

A Redis cluster proxy.

Build
===

Requirements:

* `make` and `cmake`
* UNIX-like system with `SO_REUSEPORT | SO_REUSEADDR` support
* `epoll` support
* pthread
* C++ compiler & lib with C++11 features, like g++ 4.8 or clang++ 3.2 (NOTE: install clang++ 3.2 on CentOS 6.5 won't compile because clang uses header files from gcc, which is version 4.4 without C++11 support)
* Google Test (for test)

To build, just

    make

turn on all debug logs

    make MODE=debug

or compile with g艹

    make COMPILER=g++

To link libstdc++ statically, use

    make STATIC_LINK=1

to run test (just cover message parsing parts)

    make runtest

run test with valgrind checking

    make runtest CHECK_MEM=1

Run
===

    cerberus CONFIG_FILE [ARGS]

The first argument is path of a configuration file, then optional arguments. Those specifies

* bind / `-b` : (integer) local port to listen; could also specified
* node / `-n` : (address, optional) one of active node in a cluster; format should be *host:port*; could also set after cerberus launched, via the `SETREMOTES` command, see it below
* thread / `-t` : (integer) number of threads
* read-slave / `-r` : (optional, default off) set to "yes" to turn on read slave mode. A proxy in read-slave mode won't support writing commands like `SET`, `INCR`, `PUBLISH`, and it would select slave nodes for reading commands if possible. For more information please read [here (CN)](http://u.720life.cn/g/54145d0471d91890860f7f8463c030460b002764c890a7c7d35b90d1889009ff51ff6b9c53e8d25fe44bf168363d4394614d28ba502128b5e22887f2f9d06f2fd48383877154d9525ae885d694eaf13cd758b56853a0092512f8d73cd4274222).
* read-slave-filter / `-R` : (optional, need read-slave set to "yes") if multiple slaves replicating one master, use the one whose host starts with this option value; for example, you have `10.0.0.1:7000` as a master, with 2 slave `10.0.1.1:8000` and `10.0.2.1:9000`, and read-slave-filter set to `10.0.1`, then `10.0.1.1:8000` is preferred. Note this option is no more than a string matching, so `10.0.1.1` and `10.0.10.1` won't be different on option value `10.0.1`
* cluster-require-full-coverage : (optional, default on) set to "no" to turn off full coverage mode, so proxy would keep serving when not all slots covered in a cluster.

The option set via ARGS would override it in the configuration file. For example

    cerberus example.conf -t 8

set the program to 8 threads.

Commands in Particular
===

Restricted Commands Bypass
---

* `MGET` : execute multiple `GET`s
* `MSET` : execute multiple `SET`s
* `DEL` : execute multiple `DEL`s
* `RENAME` : if source and destination are not in the same slot, execute a `GET`-`SET`-`DEL` sequence without atomicity
* `BLPOP` / `BRPOP` : one list limited; might return nil value before timeout [See detail (CN)](http://u.720life.cn/g/54145d0471d91890860f7f8463c030460b002764c890a7c7d35b90d1889009ffc16d47bdb2b378b5ac6cca0179f1b16769143ef0fc57b0647bb99063cfb51ffe)
* `EVAL` : one key limited; if any key which is not in the same slot with the argument key is in the lua script, a cross slot error would return

Extra Commands
---

* `PROXY` / `INFO`: show proxy information, including threads count, clients counts, commands statistics, and remote redis servers
* `KEYSINSLOT slot count`: list keys in a specified slot, same as `CLUSTER GETKEYSINSLOT slot count`
* `UPDATESLOTMAP`: notify each thread to update slot map after the next operation
* `SETREMOTES host port host port ...`: reset redis server addresses to arguments, and update slot map after that

Not Implemented
---

* keys: `KEYS`, `MIGRATE`, `MOVE`, `OBJECT`, `RANDOMKEY`, `RENAMENX`, `SCAN`, `BITOP`,
* list: `BRPOPLPUSH`, `RPOPLPUSH`,
* set: `SINTERSTORE`, `SDIFFSTORE`, `SINTER`, `SMOVE`, `SUNIONSTORE`,
* sorted set: `ZINTERSTORE`, `ZUNIONSTORE`,
* pub/sub: `PUBSUB`, `PUNSUBSCRIBE`, `UNSUBSCRIBE`,

others: `PFADD`, `PFCOUNT`, `PFMERGE`,
`EVALSHA`, `SCRIPT`,
`WATCH`, `UNWATCH`, `EXEC`, `DISCARD`, `MULTI`,
`SELECT`, `QUIT`, `ECHO`, `AUTH`,
`CLUSTER`, `BGREWRITEAOF`, `BGSAVE`, `CLIENT`, `COMMAND`, `CONFIG`,
`DBSIZE`, `DEBUG`, `FLUSHALL`, `FLUSHDB`, `LASTSAVE`, `MONITOR`,
`ROLE`, `SAVE`, `SHUTDOWN`, `SLAVEOF`, `SLOWLOG`, `SYNC`, `TIME`,

For more information please read [here (CN)](http://u.720life.cn/g/54145d0471d91890860f7f8463c030460b002764c890a7c7d35b90d1889009ff6fe83c10114fe8b978e6d8f39d6b487e21ac650e0185f5d0662596ec672761ac506e56345d43befe451a61539e64850bd46813e54d678764977087e71fd1249e95b3d600cb65e771913b29bdb0a5f68f10663203d50c3fbb1e73e77eed3b96345e1c6dae3751c63e5e3796c0fef00c6b74a6341f8b53e039b6626250fcf3a07c).



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e1244121d020b6dcf16951772afdd1fbcfc474eeb5c57b8948d46550c89fa44ac7692510a12a71d916538d791917e2153)