### dubbo-ops
[![Build Status](https://travis-ci.org/apache/incubator-dubbo-ops.svg?branch=master)](https://travis-ci.org/apache/incubator-dubbo-ops) 
[![Gitter](https://badges.gitter.im/alibaba/dubbo.svg)](https://gitter.im/alibaba/dubbo?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge)

The following modules in [Apache Dubbo(incubating)](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046c0001bca31ae58bae1a9ea2d5840c8aaac402427671c802ff5aa67866bf73ef2) have been moved here:

* dubbo-admin
* dubbo-monitor-simple
* dubbo-registry-simple


### How to use it
You can get a release of dubbo monitor in two steps:

#### dubbo admin
dubbo admin is a spring boot application, you can start it with fat jar or in IDE directly

#### dubbo monitor and dubbo registry
- Step 1:
```
git clone https://github.com/apache/incubator-dubbo-ops
```

- Step 2:
```
cd incubator-dubbo-ops && mvn package
```

Then you will find:

  * dubbo-monitor-simple-2.0.0-assembly.tar.gz in incubator-dubbo-ops\dubbo-monitor-simple\target directory. Unzip it you will find the shell scripts for starting or stopping monitor.
  * dubbo-registry-simple-2.0.0-assembly.tar.gz in incubator-dubbo-ops\dubbo-registry-simple\target directory. Unzip it you will find the shell scripts for starting or stopping registry.






 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e17ae728a864f53e0cbec2a825992626f47bc3f7a2f205b3b3d91485da5d9a0231a2cc10680df66782f1d937ce1a112214f68d79b90e9ac7fa04277a4e7d6be48)