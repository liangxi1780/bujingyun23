## 引言

[JeeSite Spring Cloud](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e5ba5203134346384205c0d3b577718be81315ecde5aab080cffec290d1c94dc3) 具备 [JeeSite 4.x](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e5ba5203134346384205c0d3b577718be59f2a84669167b33e3e87ffa124f8c40) 的所有功能，是在 JeeSite 4.x 基础之上，完成的 [Spring Cloud](http://u.720life.cn/g/c6d1b26d763f49c99d62f7dd7e1f263d74791681f9785d83f6cd6c957366ad1dd6abd36b3d488c22bff8dcabd4ce747f) 分布式系统套件的整合。它利用 JeeSite 4.x 的开发便利性巧妙地简化了分布式系统开发。

JeeSite Spring Cloud 并没有重复制造轮子，它只是将目前比较成熟的、经得起实际考验的服务框架组合起来，通过 Spring Boot 风格进行再封装屏蔽掉了复杂的配置和实现原理，最终给开发者留出了一套简单易懂、易部署和易维护的分布式系统开发工具包。

**特点：用经典开发模式，开发分布式应用，两个字【简单】，一个字【快】。**

## 技术选型

* 分布式系统套件版本：Spring Cloud Finchley
* 服务治理注册与发现：Spring Cloud Eureka / Consul
* 服务容错保护限流降级：Spring Cloud Hystrix
* 分布式统一配置中心：Spring Cloud Config
* 网关路由代理调用：Spring Cloud Gateway
* 声明式服务调用：Spring Cloud OpenFeign
* 分布式链路追踪：Spring Cloud Zipkin (可选组件)
* 分布式事务框架：Codingapi TX-LCN (可选组件)
* 工作流引擎框架：Flowable (可选组件)

## 子项目介绍

* 服务治理：jeesite-cloud-eureka ：  
* 配置中心：jeesite-cloud-config ：  
* 网关路由：jeesite-cloud-gateway ：  
* 核心模块（**统一授权认证**）：jeesite-cloud-module-core ：  
* 测试模块1（单表增删改查示例）：
    - 模块1主项目：jeesite-cloud-module-test1 ：  
    - 模块1客户端项目（提供其它模块调用）：jeesite-cloud-module-test1-client
* 测试模块2（树表增删改查示例）：
    - 模块2主项目：jeesite-cloud-module-test2 ：  
    - 模块2客户端项目（提供其它模块调用）：jeesite-cloud-module-test2-client
* 链路追踪：jeesite-cloud-zipkin ：  

## 快速运行

* 初始化数据库：[下载最新的mysql脚本](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e5ba5203134346384205c0d3b577718beb514777b8b88c901326dddbd8e1c11cf)
     或者使用 [init-db.bat](https://jeesite.gitee.io/docs/install-deploy/#初始化数据库) 命令
* 修改分布式统一配置文件 `/jeesite-cloud-config/../cloud-config/application.yml` 的 JDBC 和 Redis 信息
* 按顺序运行以下启动类的main方法：（因为服务直接有依赖，请启动完成一个再启下一个）
    - /jeesite-cloud-eureka/../EurekaApplication.java
    - /jeesite-cloud-config/../ConfigApplication.java
    - /jeesite-cloud-gateway/../GatewayApplication.java
    - /jeesite-cloud-module-core/../CoreApplication.java
    - /jeesite-cloud-module-test1/../Test1Application.java
    - /jeesite-cloud-module-test2/../Test2Application.java
* 以上都启动成功后，浏览器访问网关项目地址即可：
    - 访问地址：    system   admin
    - 若访问报错，请再等待一会，可能服务未完全启动完成

![](https://images.gitee.com/uploads/images/2020/0120/235836_b3da5155_6732.png)

## 调用实例演示

### 网关代理模块调用

* 代理 test1 模块（单表）： 
    - 控制器位置：jeesite-cloud-module-test1/../web/TestData1Controller.java
* 代理 test2 模块（树表）： 
    - 控制器位置：jeesite-cloud-module-test2/../web/TestTree2Controller.java

### 模块之间互相调用

* test2 模块调用 test1 模块（单表）： 
    - 服务消费者位置：jeesite-cloud-module-test2/../web/TestData2Controller.java
    - 服务提供者位置：/jeesite-cloud-module-test1/../service/TestDataService.java
* test1 模块调用 test2 模块（树表）： 
    - 服务消费者位置：jeesite-cloud-module-test1/../web/TestTree1Controller.java
    - 服务提供者位置：/jeesite-cloud-module-test2/../service/TestTreeService.java

## 授权协议声明

1. 您可以免费使用、修改和衍生代码，但不允许修改后和衍生的代码做为闭源软件发布。
2. 修改后和衍生的代码必须也按照当前协议进行流通，对修改后和衍生的代码必须向社会公开。
3. 如果您修改了代码，需要在被修改的文件中进行说明，并遵守代码格式规范，帮助他人更好的理解您的用意。
4. 在延伸的代码中（修改和有源代码衍生的代码中）需要带有原来代码中的协议、版权声明和其他原作者规定
    需要包含的说明（请尊重原作者的著作权，不要删除或修改文件中的`@author`信息）。
5. 本项目仅用于学习和交流，未得到官方授权不得用于商业用途。

### 获得技术服务支持： 

* 我们深知，没有资金的支撑就很难得到发展，特别是一个好的产品，如果 JeeSite 帮助了您，请为我们点赞。支持我们，您可以得到一些回报，有了这些我们会把开源事业做的更好，回报社区和社会，请给我们一些动力吧，在此非常感谢已支持我们的朋友！

# 技术交流方式

* QQ 群号：`127515876`、`209330483`、`223507718`、`709534275`、`730390092`、`183903863(外包)`
* 问题反馈：  　[【新手必读】](http://u.720life.cn/g/01cc770b0fbe39d52007d1419abd1f382c5557d435756e68fe8bf8e26e1118c45da70c79b0b2434d5990844a830192c964ef71eff3451fa2d96eda6e3bfaadb2)
* 码云Gitee： 
* GitHub： 
* 作者博客： 
* 官方网站： 
* 官方论坛： 
* 微信公众号：

![JeeSite4微信公众号](https://images.gitee.com/uploads/images/2020/0120/235836_3018847b_6732.jpeg "JeeSite4微信公众号")

# Git 全局设置技巧

```
1、提交检出均不转换换行符

git config --global core.autocrlf false

2、拒绝提交包含混合换行符的文件

git config --global core.safecrlf true
```


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e3b06d8276b14013283e8a46a9f587c29bcf0862388fb1938477af74e8e2f2f45856a01ea732fdb18282fc35017cc73880a098dbef8073df3d041cb54fcc7c421)