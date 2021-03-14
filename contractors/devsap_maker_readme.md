# 代码生成器
## 发展规划：
    1，支持手机端的代码生成，技术采用flutter. 已经完成初版
    2，microServer增加加密通信，能够支持移动端使用
    3，vertx进一步优化：集群，分布式等。一切突出性能
    4，对生成的代码增加测试代码
    5，nodejs进一步优化，增加更多的组件
    6，增加生成mobile web代码
    7，增加监控功能
    8，优化权限控制
    9，基础功能会进一步优化

# 感谢大家的支持，尤其是以下两位朋友：
  1， 诺亚之舟  2，eastion
  他们发现软件中的问题，并积极参与其中，改进代码。
  大家的支持，是我后续优化的最大动力。


采用javafx制作UI界面，通过操作界面，直接生产可以运行的代码，
 对表生成了增，删，改，查等功能，还生成了相应的界面页面。

## 生成代码说明：
    根据数据库结构，按照用户的要求，动态生成可执行代码。
    生成的maven结构。spring mvc + spring + mybatis传统接口
    前端多技术： easyui, bootstrap + jsp, bootstrap + freemarker, javafx ui, flutter(android + ios)

子项目说明：
## main
    项目的启动项目。启动类： MainLauncher
## core 项目
    所有子项目的基础，包含了对数据库结构的描述。
## server 项目
    基础项目
## web项目
    生成不同框架的具体实现
## desktop
    1，可以生成javafx客户端桌面应用
    2，可以生成javafx+spring+mybatis桌面应用
## mobile web
    可以生成nodejs + vuejs + bootstrap 前端界面
## android
    flutter支持android 和ios手机端

# 功能列表
    1, spring boot + spring + mybatis + mysql + 各种前端
    2, 支持mybatis一对一，一对多，多对多关系查询，并支持动态选择是否生成
    3, 支持mybatis分页查询，唯一索引删除，查询，更新等
    4, 支持表中字段枚举生成
    5, 支持表中字段重注释，并且同步到POJO的注释上
    6, 支持对表筛选，筛选中的表可以不生成对应的pojo + mybatis mapper + dao + service + controller;
    7, 表对应的前端可以动态控制，控制只显示需要的字段
    8, 支持Swagger2
    9, 支持vertx + sync + quasar + freemarker
    10, web端支持shiro权限控制
    11，支持metrics.对系统增加了监控
    12，支持flutter版的android + ios
    13，支持spring oauth2的中心登录和权限控制，使用方法：
          请将lib/oauth-common-1.0.jar单独copy出来，添加进本地仓库中。运行：
          mvn install:install-file -DgroupId=ldh.auth -DartifactId=oauth-common -Dversion=1.0 -Dpackaging=jar -Dfile=oauth-common-1.0.jar
    14, 支持spring oauth2资源服务器端代码的自动生成, 支持swagger已经权限控制  
    
    
# 操作图
![Alt text](https://gitee.com/ldh123/maker/raw/master/doc/images/0.png)
![Alt text](https://gitee.com/ldh123/maker/raw/master/doc/images/1.png)
![Alt text](https://gitee.com/ldh123/maker/raw/master/doc/images/2.png)
![Alt text](https://gitee.com/ldh123/maker/raw/master/doc/images/3.png)
![Alt text](https://gitee.com/ldh123/maker/raw/master/doc/images/4.png)
![Alt text](https://gitee.com/ldh123/maker/raw/master/doc/images/5.png)
![Alt text](https://gitee.com/ldh123/maker/raw/master/doc/images/6.png)
![Alt text](https://gitee.com/ldh123/maker/raw/master/doc/images/7.png)
![Alt text](https://gitee.com/ldh123/maker/raw/master/doc/images/8.png)
![Alt text](https://gitee.com/ldh123/maker/raw/master/doc/images/9.png)
![Alt text](https://gitee.com/ldh123/maker/raw/master/doc/images/10.png)
![Alt text](https://gitee.com/ldh123/maker/raw/master/doc/images/10-1.png)
![Alt text](https://gitee.com/ldh123/maker/raw/master/doc/images/10-2.png)
![Alt text](https://gitee.com/ldh123/maker/raw/master/doc/images/11.png)
![Alt text](https://gitee.com/ldh123/maker/raw/master/doc/images/12.png)
![Alt text](https://gitee.com/ldh123/maker/raw/master/doc/images/13.png)
![Alt text](https://gitee.com/ldh123/maker/raw/master/doc/images/14.png)
![Alt text](https://gitee.com/ldh123/maker/raw/master/doc/images/15.png)
![Alt text](https://gitee.com/ldh123/maker/raw/master/doc/images/16.png)
![Alt text](https://gitee.com/ldh123/maker/raw/master/doc/images/17.png)
![Alt text](https://gitee.com/ldh123/maker/raw/master/doc/images/18.png)
![Alt text](https://gitee.com/ldh123/maker/raw/master/doc/images/19.png)
![Alt text](https://gitee.com/ldh123/maker/raw/master/doc/images/mobile1.jpg)
![Alt text](https://gitee.com/ldh123/maker/raw/master/doc/images/mobile2.jpg)
![Alt text](https://gitee.com/ldh123/maker/raw/master/doc/images/mobile3.png)
![Alt text](https://gitee.com/ldh123/maker/raw/master/doc/images/mobile4.png)
![Alt text](https://gitee.com/ldh123/maker/raw/master/doc/images/mobile5.png)
![Alt text](https://gitee.com/ldh123/maker/raw/master/doc/images/mobile6.png)
![Alt text](https://gitee.com/ldh123/maker/raw/master/doc/images/mobile7.png)


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ed710229ac039556a8b68c3368f31451b78af3e0839f3866382d04d9b24431ef7769466a6e203f5e3f8a5f8c20ea6c530)