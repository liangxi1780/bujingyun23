简体中文 | [English](./README.EN.md)

 MyPerf4J 

 

一个针对高并发、低延迟应用设计的高性能 Java 性能监控和统计工具。

[![GitHub (pre-)release](https://img.shields.io/github/release/ThinkpadNC5/MyPerf4J/all.svg)](https://github.com/ThinkpadNC5/MyPerf4J) [![Build Status](https://travis-ci.com/ThinkpadNC5/MyPerf4J.svg?branch=develop)](https://travis-ci.com/ThinkpadNC5/MyPerf4J) [![Coverage Status](https://coveralls.io/repos/github/ThinkpadNC5/MyPerf4J/badge.svg?branch=develop)](https://coveralls.io/github/ThinkpadNC5/MyPerf4J?branch=develop) [![GitHub issues](https://img.shields.io/github/issues/ThinkpadNC5/MyPerf4J.svg)](https://github.com/ThinkpadNC5/MyPerf4J/issues) [![GitHub closed issues](https://img.shields.io/github/issues-closed/ThinkpadNC5/MyPerf4J.svg)](https://github.com/ThinkpadNC5/MyPerf4J/issues?q=is%3Aissue+is%3Aclosed) [![GitHub](https://img.shields.io/github/license/ThinkpadNC5/MyPerf4J.svg)](./LICENSE)

 

## 特性
* 高性能: 单线程支持每秒 **1000 万次** 响应时间的记录，每次记录只花费 **73 纳秒**
* 无侵入: 采用 **JavaAgent** 方式，对应用程序完全无侵入，无需修改应用代码
* 低内存: 采用内存复用的方式，整个生命周期只产生极少的临时对象，不影响应用程序的 GC
* 高精度: 采用纳秒来计算响应时间
* 高实时: 支持秒级监控，最低 **1 秒**

## 使用场景
* 在**开发环境**中快速定位 Java 应用程序的性能瓶颈
* 在**生产环境**中长期监控 Java 应用程序的性能指标

## 文档
* [English Doc](http://u.720life.cn/g/54145d0471d91890860f7f8463c030462427425cfa8ac380b7610a3b4941e7126440a1a61713807df694e2cd76c60d1def1b99059cdf52ff510269b35e27d8ec)
* [中文文档](http://u.720life.cn/g/54145d0471d91890860f7f8463c030462427425cfa8ac380b7610a3b4941e712a47b5165ed725653379ca1d4893da77d93b3016371c3a9df041cabf22d3fedc1)    
    
## 监控指标
MyPerf4J 为每个应用收集数十个监控指标，所有的监控指标都是实时采集和展现的。

下面是 MyPerf4J 目前支持的监控指标列表:
- **[Method Metrics](http://u.720life.cn/g/b675da847faf899dd7953a9eae0a65ac790013a76750c5a9edb146dcbdfa23f4144c53484e0dab2e84e31a74805cb74b)** 
RPS，Count，Avg，Min，Max，StdDev，TP50, TP90, TP95, TP99, TP999, TP9999, TP99999, TP100
![Markdown](https://raw.githubusercontent.com/ThinkpadNC5/Pictures/master/MyPerf4J-InfluxDB-Method_Show_Operation.gif)

- **[JVM Metrics](http://u.720life.cn/g/b675da847faf899dd7953a9eae0a65acd593b816d2feecd05a116984132da11c34859e7f54d227cd95841b817621f42c)** 
Thread，Memory，ByteBuff，GC，Class
![Markdown](https://raw.githubusercontent.com/ThinkpadNC5/Objects/master/MyPerf4J_JVM_Compressed.jpeg)

    > 想知道如何实现上述效果？请先按照[快速启动](http://u.720life.cn/g/54145d0471d91890860f7f8463c030462427425cfa8ac380b7610a3b4941e712a88ef3e37f8804a5c0166ce679393ea358aa1f0ba701e2a04593fac3928dec1c81c1c8c135ebcec164b6febc24211925)的描述启动应用，再按照[这里]https://github.com/ThinkpadNC5/MyPerf4J/wiki/InfluxDB_

## 快速启动
MyPerf4J 采用 JavaAgent 配置方式，**透明化**接入应用，对应用代码完全**没有侵入**。

### 打包
* git clone git@github.com:ThinkpadNC5/MyPerf4J.git
* mvn clean package
* 把 MyPerf4J-ASM-${MyPerf4J-version}.jar 重命名为 MyPerf4J-ASM.jar

> 如果你使用的是 JDK 7 或者更高版本可以尝试直接下载 [MyPerf4J-ASM.jar](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046e1920fe5d510a478eb257ba7ad8b1877f54609b9985898327f544558425dd7950c59f3e970037e2d4fdb470ca80b86c4685af089440ea91517f7a461f316cf17ebc23532d7cd119c504ab73bcb2c4b23)

### 配置
在 JVM 启动参数里加上以下两个参数
> -javaagent:/your/path/to/MyPerf4J-ASM.jar

> -DMyPerf4JPropFile=/your/path/to/myPerf4J.properties

其中，`MyPerf4JPropFile`的配置如下:

 ```
#应用名称
AppName=MyPerf4JTest

#MetricsProcessor类型，0:以标准格式化结构输出到stdout.log 1:以标准格式化结构输出到磁盘  2:以InfluxDB LineProtocol格式输出到磁盘
MetricsProcessorType=1

#配置各个Metrics日志的文件路径，可不配置
MethodMetricsFile=/data/logs/MyPerf4J/method_metrics.log
ClassMetricsFile=/data/logs/MyPerf4J/class_metrics.log
GCMetricsFile=/data/logs/MyPerf4J/gc_metrics.log
MemMetricsFile=/data/logs/MyPerf4J/memory_metrics.log
BufPoolMetricsFile=/data/logs/MyPerf4J/buf_pool_metrics
ThreadMetricsFile=/data/logs/MyPerf4J/thread_metrics.log

#配置Record模式，可配置为accurate/rough
RecorderMode=accurate
    
#配置时间片，单位为ms，最小1s，最大600s
MilliTimeSlice=10000
    
#需要监控的package，可配置多个，用英文';'分隔
IncludePackages=cn.perf4j.demo
 ```
        
> 想了解更多的配置？请看[这里](http://u.720life.cn/g/54145d0471d91890860f7f8463c030462427425cfa8ac380b7610a3b4941e71234a13637843a8efadff98414d070ac948a5c377262b8bdd141fe3d3b93a8538f)

### 运行
* 输出结果，输出到 /data/logs/MyPerf4J/method_metrics.log:

    ```
    MyPerf4J Method Metrics [2018-09-06 19:21:40, 2018-09-06 19:21:45]
    Method[4]                           RPS  Avg(ms)  Min(ms)  Max(ms)   StdDev     Count     TP50     TP90     TP95     TP99    TP999   TP9999  TP99999    TP100
    DemoServiceImpl.getId1(long)       1974     0.00        0        0     0.00      9870        0        0        0        0        0        0        0        0
    DemoServiceImpl.getId2(long)       2995     0.50        0        2     0.01     14975        0        1        2        2        2        2        2        2
    DemoServiceImplV2.getId1(long)      787     0.00        0        0     0.00      3938        0        0        0        0        0        0        0        0
    DemoServiceImplV2.getId3(long)     1575     0.50        0        1     0.01      7876        1        1        1        1        1        1        1        1
    ```

### 卸载
在 JVM 启动参数中去掉以下两个参数，重启即可卸载此工具。
> -javaagent:/your/path/to/MyPerf4J-ASM.jar

> -DMyPerf4JPropFile=/your/path/to/myPerf4J.properties

## 问题
如果您有任何问题、疑问或者建议，请您毫不犹豫的 [提交Issue](http://u.720life.cn/g/54145d0471d91890860f7f8463c030462427425cfa8ac380b7610a3b4941e712ed0e7445ddffc4d638d22ce83858edfe119e08e45dfce8d99f064d49e599d45e) 或者 [发送邮件](mailto:feedback.myperf4j@gmail.com) : )

## 参考项目
MyPerf4J 是受以下项目启发而来：
* [Perf4J](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304673758eb6422775f77fd728ecd33d0f04)
* [TProfiler](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046b8f4543a0cb71e6b6856ddec5ce835a22366188bab5e17764a5bff8a4c4d1a07)

## 更多信息
想更深入的了解 MyPerf4J ？请看[https://github.com/ThinkpadNC5/MyPerf4J/wiki/Chinese-Doc](http://u.720life.cn/g/54145d0471d91890860f7f8463c030462427425cfa8ac380b7610a3b4941e712a47b5165ed725653379ca1d4893da77d93b3016371c3a9df041cabf22d3fedc1)。


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ee4c394881c02eac76bbd9731783ffb436ebd74870bd06e4fd7637be096a5dc9b9a32e6a0603e77d1017aa9d06013c41f)