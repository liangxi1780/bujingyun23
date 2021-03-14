Bolt
====
Bolt - The Realtime Image Compress System
 

介绍
----
&nbsp;&nbsp;&nbsp;&nbsp;Bolt是一个实时裁剪压缩图片服务器，其比nginx的image_filter快2倍以上，主要是因为Bolt对一张图片只做一次处理，就算在处理图片的过程中，其他的客户端也在请求此图片，Bolt也能保证只有一个线程在处理此图片。 

&nbsp;&nbsp;&nbsp;&nbsp;另外Bolt替换缓存机制，处理过的图片不再进行第二次处理，除非内存不足的时候，Bolt才会处理LRU算法来删除缓存中的图片，在启动Bolt的时候可以使用“--max-cache”启动参数来设置最大内存限制。Bolt使用LRU算法来淘汰缓存的图片，也就是说一般只会淘汰较少访问的图片，这就可以很好的限制Bolt的内存使用。

用在哪里
--------
Bolt可以用在内存和CPU都过剩的服务器，另外使用Bolt可以减少磁盘的使用，加快图片的加载速度。

安装
----
* 安装libevent (http://u.720life.cn/g/3cec5b12837d4379818eeaf7b6867e8eb6509009261eee01d2872bfeb6bb19f8)
* 安装ImageMagick (http://u.720life.cn/g/a892a06bc3d42ca4f603e68d59e166e2cc5b098075aa44071e03f9199bf036ee866d18f508583e497a1f1ece1a058716)
* 安装Bolt
```shell
$ git clone https://github.com/liexusong/bolt
$ cd bolt
$ make
```

使用方式
--------
访问URL：http://your-host/filename_(width)x(height)_(quality).jpg

Bolt配置文件
--------------
* host = [str]          # 设置绑定的IP
* port = [int]          # 设置监听的端口
* workers = [int]       # 启动多少个worker线程(用于裁剪图片)
* logfile = [str]       # 日志文件输出的路径
* logmark = [str]       # 日志要显示的级别，可以选择(DEBUG|NOTICE|ALERT|ERROR)
* max-cache = [int]     # 设置Bolt可以使用的最大内存(单位为字节)
* gc-threshold = [int]  # GC要清理的阀值(也就是说GC会清理到max-cache的百分之多少停止，可选值为0 ~ 99)
* path = [str]          # 要进行裁剪的图片源路径
* watermark = [str]     # 水印图片路径
* daemon = [yes|no]     # 是否启动守护进程模式

 
如果各位发现bug，请向本人提出，本人深深感谢。如果希望提供什么样的新功能也可以提出。
 



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e3943df9669ac3b4affa040cc67e835a150ab6ca8d65284c5dee985041518a18bbceed389d16096041299f2b6593f8426)