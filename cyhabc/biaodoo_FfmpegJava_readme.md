# FFmpegjava（FFmpeg命令执行管理器） 
 ## 说明
 java封装的提供ffmpeg命令执行、停止、查询功能、监控ffmpeg是否中断，重新推流的功能的简单管理器 
 ## 版本说明 
 	1、本次更新主要针对配置文件的加载优化，详情见下面的使用说明
	初始化FFmpegManager时会自动查找loadFFmpeg.properties配置文件
	 配置文件的加载方式如下：
	(1)、javaSE项目会自动从项目根目录加载
	(2)、javaEE项目会自动从classes目录下加载（编写web项目的src目录下）
	(3)、如果上述位置都没有找到配置文件，会自动加载默认配置，默认的配置文件在config包下的defaultFFmpegConfig.properties中

 	2、支持自定义的消息输出
	
	上个版本更新说明
 	3、增加一个String start(String id,String commond,boolean hasPath)接口，用于区分是否使用配置文件中的绝对路径，如果为false，请务必保证ffmpeg的路径可以正确加载
 	4、增加一个debug配置，用于判断是否输出关键位置的debug消息
 	5、增加日志输出
 ## 基于
 本项目基于jdk1.8开发，FFmpeg各版本支持的命令请参考[FFmpeg官方文档](http://u.720life.cn/g/08a8721494911cd8408a11af9e278b2329354e345bb6f98fe35cf61e740bb227) 
 ## 使用说明 
```Java 
	 FFmpegManager manager=new FFmpegManagerImpl(10);
	//当然也可以这样：FFmpegManager manager=new FFmpegManagerImpl();//这样会从配置文件中读取size的值作为初始化参数
	//组装命令
	Map map = new HashMap();
	map.put("appName", "test123");
	map.put("input","rtsp://admin:admin@192.168.2.236:37779/cam/realmonitor?channel=1&subtype=0");
	map.put("output", "rtmp://192.168.30.21/live/");
	map.put("codec","h264");
	map.put("fmt", "flv");
	map.put("fps", "25");
	map.put("rs", "640x360");
	map.put("twoPart","2");
	//执行任务，id就是appName，如果执行失败返回为null
	String id=manager.start(map);
	System.out.println(id);
	//通过id查询
	TaskEntity info=manager.query(id);
	System.out.println(info);
	//查询全部
	Collection  infoList=manager.queryAll();
	System.out.println(infoList);

	//停止id对应的任务
	manager.stop(id);
	//执行原生ffmpeg命令（不包含ffmpeg的执行路径，该路径会从配置文件中自动读取）
	manager.start("test1", "ffmpeg -i input_file -vcodec copy -an output_file_video");
	//包含完整ffmpeg执行路径的命令
	manager.start("test2,","d:/ffmpeg/ffmpeg -i input_file -vcodec copy -an output_file_video",true);
	//停止全部任务
	manager.stopAll();
```
关于FFmpegCommandHandler接口调用/使用方式也可以参考readme文件
# FfmpegJava



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e38f1c6e54557ac64df0f8bde1fb1716a41be6d1771320a3b3240296196656550eacda7a842cd20f106ed0e06e8e2a9b6)