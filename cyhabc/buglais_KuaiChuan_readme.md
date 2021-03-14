# KuaiChuan(仿茄子快传)
[English](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304639503bcf5df9ddc32ab5299bb5106d8d0bf3a693902dbfaa74977d9094de307b1d3fa2abc59c357ae46412d2863c00a8)

仿茄子快传的一款文件传输应用， 涉及到Socket通信，包括TCP，UDP通信。（喜欢的给一个star, 有帮助的给一个fork， 欢迎Star和Fork ^_^）

[下载](http://u.720life.cn/g/7998f3692f38a7fae6eac6142cbe5b48faa67371267a10bed952d99192449d03) 点击下载去下载应用。

[https://github.com/mayubao/KuaiChuan](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304639503bcf5df9ddc32ab5299bb5106d8d7475b2006369b0ca3fc345cf68ef0fc2)

## 效果预览

### 主页 ###
![Alt text](http://img.blog.csdn.net/20161215211058219?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQveXViYW9tYTIwMTQ=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

### 文件发送端 ###
![Alt text](http://img.blog.csdn.net/20161215211350691?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQveXViYW9tYTIwMTQ=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)
![Alt text](http://img.blog.csdn.net/20161215211444724?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQveXViYW9tYTIwMTQ=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)
![Alt text](http://img.blog.csdn.net/20161215211554850?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQveXViYW9tYTIwMTQ=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

### 文件接收端 ###
![Alt text](http://img.blog.csdn.net/20161215211700461?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQveXViYW9tYTIwMTQ=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)
![Alt text](http://img.blog.csdn.net/20161215211731440?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQveXViYW9tYTIwMTQ=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

### 网页传(20161218新增) ###
![Alt text](http://img.blog.csdn.net/20161219181840389?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQveXViYW9tYTIwMTQ=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

![Alt text](http://img.blog.csdn.net/20161219181853340?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQveXViYW9tYTIwMTQ=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)
![Alt text](http://img.blog.csdn.net/20161219181906670?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQveXViYW9tYTIwMTQ=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

## 原理


快传有两种方式可以传输文件：

1. Android应用端发送到Android应用端（必须安装应用）
2. 通过Web浏览器来实现文件的传送 （不必安装应用）

第一种方式主要是是通过设备间发送文件。 文件传输在文件发送端或者是文件接收端通过自定义协议的Socket通信来实现。由于文件接收方和文件发送方都要有文件的缩略图，这里采用了header + body的自定义协议, header部分包括了文件的信息（长度，大小，缩略图）， body部分就是文件。

第二种方式主要是在android应用端架设微型Http服务器来实现文件的传输。这里可以用ftp来实现，为什么不用ftp呢？因为没有缩略图，这是重点！


## 测试

（必须在真机下测试）
在Android测试机 分别是 魅蓝2 与  华为 SCL-TL00， Vivo xs1 运行正常

## 感谢

google:  

stackoverflow   


## 版本

### v1.0 ###
完成了Android端到Android端的文件传输

### v1.1 ###
完成了网页传模块的功能


## issue
QQ:345269374

Email:345269374@qq.com


## License
    Copyright 2016 mayubao

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e5f22bdb705699c9b1e13850916adcc4fa4a3efd82a342badbf718cbb3aff087f0fe007218c2bba1c2f8b1f94a494f91d)