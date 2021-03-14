微信支付、公众号&企业号开发Java SDK
---------------------------------
[![Maven Central](https://maven-badges.herokuapp.com/maven-central/com.github.binarywang/weixin-java-parent/badge.svg)](https://maven-badges.herokuapp.com/maven-central/com.github.binarywang/weixin-java-parent)
[![Build Status](https://travis-ci.org/Wechat-Group/weixin-java-tools.svg?branch=develop)](https://travis-ci.org/Wechat-Group/weixin-java-tools)

### 注意事项：
1. 声明： ***本项目Fork自chanjarster/weixin-java-tools，但由于原项目已停止维护，故单独维护和发布，且发布到maven上的groupId也会不同，详细信息见下文。***
1. **新手请注意，本项目仅是一个开发工具包（即SDK），未提供Web实现，建议使用maven或gradle引用本项目即可使用本SDK提供的各种功能，详情可参考下文中提到的Demo项目或本项目中的部分单元测试代码；如果没有贡献代码的意愿，不建议下载项目的源码自行编译，因为如果想看源码使用maven也是可以下载源码的**；
1. 最新更新：**2017-4-13 发布[【2.6.0正式版】](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046201a511e2ba300ebaea50f02340949bcca63bd4327b4be140b9c98ec0254b23e4da9587d592d99c122fe6a997d216c79)**！
1. 开源中国网站的本项目介绍的首页链接地址：https://www.oschina.net/p/weixin-java-tools-new
1. 自2.0.0版本以来，公众号的接口调整比较大，主要是为了解决主接口类过于庞大不方便管理的问题，将接口实现代码按模块进行拆分。
1. 自2.6.0版本开始，微信支付相关功能抽出独立为一个模块，详细使用方式请参考相关demo；
1. SDK详细开发文档请查阅 [【Wiki】](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046baa7244917c0ef77762f29cdc461153cfcc4378b6133c2f20a621f96c118a6badf9a86f38eb01a8cff3ec213f34e8c83)，部分文档可能未能及时更新，如有发现，可以及时上报或者自行修改。***另外微信开发新手请务必阅读wiki首页的常见问题部分，可以少走很多弯路，节省不少时间。***
1. 各个模块的Javadoc可以在线查看（有可能是最新的测试版本的，请注意观察版本号）：[weixin-java-pay](http://u.720life.cn/g/7abee09d62f77ca52d23d1123d4aaea4e6f4a3d0a1c6301521d83f98ef44b1e8906499058ea1c354de48d8d5d3b3aa5ee99730b3e5663e21e6c103b25fd958a3)、[weixin-java-mp]https://binarywang.github.io/weixin-java-mp-javadoc/
1. 本SDK要求的最低JDK版本是7，还在使用JDK6的用户请参考[【此项目】]( https://github.com/binarywang/weixin-java-tools-for-jdk6) ，而其他更早的JDK版本则需要自己改造实现。
1. 如有新功能需求，发现BUG，或者由于微信官方接口调整导致的代码问题，可以直接在[【Issues】](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046201a511e2ba300ebaea50f02340949bcca63bd4327b4be140b9c98ec0254b23e10e4e637fd7bc20059eaf160a3226a48)页提出issue，便于讨论追踪问题；
1. 如果想贡献代码，请阅读[【代码贡献指南】](contribution.md)；
1. 捐助渠道已开通，如有意向请前往托管于码云的项目首页（具体地址见下文）的页面评论区上方，可以找到“捐助”按钮，非常感谢各位捐助的同学！

---------------------------------
## SDK使用交流方式说明：
1. QQ群： [![加入QQ群](https://img.shields.io/badge/QQ群-343954419-blue.svg)](http://shang.qq.com/wpa/qunwpa?idkey=731dc3e7ea31ebe25376cc1a791445468612c63fd0e9e05399b088ec81fd9e15) 或 [![加入QQ群](https://img.shields.io/badge/QQ群-343954419-blue.svg)](http://jq.qq.com/?_wv=1027&k=40lRskK)，推荐点击按钮入群，当然如果无法成功操作，请自行搜索群号343954419进行添加 ）
1. 由于群容量有限，即将爆满，故开启付费入群模式以保证只有真实交流需求的人进入，如果确实因为各种原因无法付费入群的，请联系群主说明原因即可入群；并为保证群的活跃度，本群将不定期清理长时间不活跃的同学；
1. 微信群： 因微信群已达到100人限制，故如有想加入微信群的，请入QQ群后联系管理员，提供微信号以便邀请加入；
1. 新手提问前，请先阅读此文章：http://t.cn/RV93MRB
1. 寻求帮助时需贴代码或大长串异常信息的，请利用http://paste.ubuntu.com

---------------------------------
## 版本说明
1. 本项目定为大约每两个月发布一次正式版，版本号格式为X.X.0（如2.1.0，2.2.0等），遇到重大问题需修复会及时提交新版本，欢迎大家随时提交Pull Request；
1. BUG修复和新特性一般会先发布成小版本作为临时测试版本（如2.4.5.BETA，2.4.6.BETA等，即尾号不为0，并添加BETA字样，以区别于正式版）；
1. 目前最新版本号为 [![Maven Central](https://maven-badges.herokuapp.com/maven-central/com.github.binarywang/weixin-java-parent/badge.svg)](https://maven-badges.herokuapp.com/maven-central/com.github.binarywang/weixin-java-parent) ，也可以通过访问链接 [【微信支付】](http://search.maven.org/#search%7Cgav%7C1%7Cg%3A%22com.github.binarywang%22%20AND%20a%3A%22weixin-java-pay%22) 、[【公众号】](http://search.maven.org/#search%7Cgav%7C1%7Cg%3A%22com.github.binarywang%22%20AND%20a%3A%22weixin-java-mp%22) 、[【企业号】](http://search.maven.org/#search%7Cgav%7C1%7Cg%3A%22com.github.binarywang%22%20AND%20a%3A%22weixin-java-cp%22)
分别查看所有最新的版本。 

---------------------------------
#### 本项目在几个著名的代码托管网站同步更新，地址分别是:
* 码云：http://git.oschina.net/binary/weixin-java-tools
* GitHub: https://github.com/wechat-group/weixin-java-tools
* Bitbucket：https://bitbucket.org/binarywang/weixin-java-tools
* Coding: https://git.coding.net/binarywang/weixin-java-tools.git

---------------------------------
## 可参考的Demo项目
#### 欢迎提供更多的Demo供新手参考:
* https://github.com/wechat-group/weixin-java-mp-demo （公众号Demo，使用Spring MVC实现）
* https://github.com/wechat-group/weixin-java-mp-multi-demo (支持多公众号)
* https://github.com/wechat-group/weixin-java-tools-springmvc （公众号Demo，内含部分微信支付代码）
* https://github.com/wechat-group/weixin-java-mp-demo-springboot （公众号Demo，使用Spring Boot实现）
* https://github.com/wechat-group/weixin-java-pay-demo （微信支付demo） 
* https://github.com/wechat-group/weixin-java-cp-demo （企业号demo，筹备中）

---------------------------------
## Maven & Gradle 最新正式版本

* 微信支付：

maven：
```xml
 
   com.github.binarywang 
   weixin-java-pay 
   2.6.0 
 
```
gradle：
```groovy
compile 'com.github.binarywang:weixin-java-pay:2.6.0'
```

* 公众号（订阅号及服务号）：

maven：
```xml
 
   com.github.binarywang 
   weixin-java-mp 
   2.6.0 
 
```
gradle：
```groovy
compile 'com.github.binarywang:weixin-java-mp:2.6.0'
```

* 企业号：

maven：
```xml
 
   com.github.binarywang 
   weixin-java-cp 
   2.6.0 
 
```
gradle：
```groovy
compile 'com.github.binarywang:weixin-java-cp:2.6.0'
```



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e812e0c28e250eb70fde0b4d55a620a35a29228bb301d7d339aad40afaf9c37dcd08e035a713d98a02a1bf852bec2112dd94f1eb425b437c24332f23ef6982db4)