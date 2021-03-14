
# 使用Netty实现服务端和客户端tcp或websockt长连接通信
- 客户端往服务端发送一条消息，服务端收到客户端消息”ping”，处理消息后回复一条消息”pong”；
- 服务端支持多个客户端连接，需实现心跳检测和断线重连。

## com.baron.study.netty
netty服务端和客户端，断线重连以及心跳检测，其中com.baron.study.netty.server.NettyServer是server启动类，com.baron.study.netty.client.NettyClient是client启动类。
# com.baron.study.thread
编写一个类。类里有一个map和一个int compute(int param)方法。Compute方法使用sleep模拟一个非常耗时的计算过程。当执行compute方法时能够判断之前是否计算过该值，如果计算过，则返回结果，否则执行计算过程并缓存结果到map中再返回。要求线程安全，性能尽可能高。

其中com.baron.study.thread.TestMain是测试启动类



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e0b00c355f8e0470814c282fc50b6dcce0118865716c8e0de3ae232e3083a8ef9df1f3b4dd7b545d44f266e95a68517ff)