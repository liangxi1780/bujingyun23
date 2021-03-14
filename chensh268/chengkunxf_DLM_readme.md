 基于redis,zookeeper实现分布式锁 

 1.铺垫 
countDownLatch的使用[CountDownLatchTest.java] 
zookeeper客户端操作zk节点及watcher事件机制[SimpleOperationDemo.java] 
curator对客户端的封装demo演示[CuratorCRUD.java] 
 2.zk原生客户端实现分布式锁 
代码[OriginZKlock.java] 
分布式锁测试[ZKTest.java] 
 3.使用curator完成可重入分布式互斥锁(InterProcessMutex) 
代码[CuratorLock.java] 
 4.redis的java客户端实现分布式锁 
核心redis方法 setnx(key,val) 
代码[DLock.java] 
测试[DLockTest.java] 
 5.Redisson框架实现分布式可重入互斥锁 
代码[Redission.java]、[RedissionLock.java] 
测试[RedissionLockTest]


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ec65afc788d63b125a65c27e452839a5bef8382ec251e408891f000beeb30ef7ee992d50357106aea0f2eb09e348f5ea5)