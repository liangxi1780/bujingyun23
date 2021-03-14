## iBas4J项目简介

- iBase4J是Java语言的分布式系统架构。 使用Spring整合开源框架。
- 使用Maven对项目进行模块化管理，提高项目的易开发性、扩展性。
- 系统包括三个模块：公共模块、系统管理模块、Web展示模块。
- 公共模块：公共功能(AOP、缓存、基类、调度等等)、公共配置、工具类。
- 系统管理模块：包括用户管理、权限管理、数据字典、系统参数管理等等。
- 每个模块都是独立的系统，可以无限的扩展模块，模块之间使用Dubbo或MQ进行通信。
- 每个模块服务多系统部署，注册到同一个Zookeeper集群服务注册中心，实现集群部署。

## 主要功能
 1. 数据库：Druid数据库连接池，监控数据库访问性能，统计SQL的执行性能。 数据库密码加密，加密方式请查看PropertiesUtil，decryptProperties属性配置需要解密的key。
 2. 持久层：mybatis持久化，使用MyBatis-Plus优化，减少sql开发量；aop切换数据库实现读写分离。Transtraction注解事务。
 3. MVC： 基于spring mvc注解,Rest风格Controller。Exception统一管理。
 4. 调度：Spring+quartz, 可以查询、修改周期、暂停、删除、新增、立即执行，查询执行记录等。
 5. 基于session的国际化提示信息，职责链模式的本地语言拦截器,Shiro登录、URL权限管理。会话管理，强制结束会话。
 6. 缓存和Session：注解redis缓存数据，Spring-session和redis实现分布式session同步，重启服务会话不丢失。
 7. 多系统交互：Dubbo,ActiveMQ多系统交互，ftp/sftp/fastdafs发送文件到独立服务器，使文件服务分离。
 8. 前后端分离：没有权限的文件只用nginx代理即可。
 9. 日志：log4j2打印日志，业务日志和调试日志分开打印。同时基于时间和文件大小分割日志文件。
 10. QQ、微信、新浪微博第三方登录。
 11. 工具类：excel导入导出，汉字转拼音，身份证号码验证，数字转大写人民币，FTP/SFTP/fastDFS上传下载，发送邮件，redis缓存，加密等等。

## 技术选型
    ● 核心框架：Spring Framework 4.3.0 + Dubbo 2.5.3
    ● 安全框架：Apache Shiro 1.2
    ● 任务调度：Spring + Quartz
    ● 持久层框架：MyBatis 3.4 + MyBatis-Plus 2.0
    ● 数据库连接池：Alibaba Druid 1.0
    ● 缓存框架：Redis
    ● 会话管理：Spring-Session 1.2
    ● 日志管理：SLF4J、Log4j2
    ● 前端框架：Angular JS + Bootstrap + Jquary

## 启动说明
    * 项目依赖activemq、Redis和ZooKeeper服务。
    * 启动SYS-Service命令：clean package -P build tomcat7:run-war-only -f pom-sys-server.xml
    * 启动Web命令：clean package -P build tomcat7:run-war-only -f pom-web-server.xml
    * 使用nginx代理UI：修改配置里的UI目录后重启nginx。
    
## 版权声明
iBase4J使用 [Apache License 2.0][] 协议.

## 建议
可以先看一下拆分前的版本，地址：[iBase4J-old][].

## 加入QQ群[538240548](http://u.720life.cn/g/88d3be70c797d2a69a24ab56221f9e0339fd68ed2b2e8afb401b350bf89ee621eb5e4882f94703be3e6a6d61ca9ba22a635c249bee01708f1fdda578f3ebf1c6cbc8984488ecf69e5369655f57b4f68af1bc81efa2109f74af1ada8e5ed49e129b8ebbced8d579e6846acb454872d67d) [498085331](http://u.720life.cn/g/88d3be70c797d2a69a24ab56221f9e0339fd68ed2b2e8afb401b350bf89ee621c0521b943a3b50ab5ec4842b4c9bf57f7a1818a5af9c7ea2e0740cc54e6942caa2698696d80876955f65079438db0e0d69765f0a2b2fdba6517e9ca86e5ac36d06c9d3eb3dae0fbbc30a31f5b9904174)
交流技术问题，下载项目文档和一键启动依赖服务工具。

![QQ群](http://git.oschina.net/iBase4J/iBase4J/raw/master/img/1464169485871.png "QQ群一")
![QQ群](http://git.oschina.net/iBase4J/iBase4J/raw/master/img/1482378175294.png "QQ群二")

## UI地址
[iBase4J-UI](http://u.720life.cn/g/5c954f4cd4204fb6c09a7e58aa70844d577f2653c8430f59054af15b308626d477d2c0dca35b19e85ede6d61141c753e)

## UI效果图

![登录](http://git.oschina.net/iBase4J/iBase4J/raw/master/img/login.png "登录")
![主页](http://git.oschina.net/iBase4J/iBase4J/raw/master/img/index.png "主页")
![接口](http://git.oschina.net/iBase4J/iBase4J/raw/master/img/swagger.png "接口")

![捐赠](http://git.oschina.net/iBase4J/iBase4J/raw/master/img/contribute.png "捐赠")

## License
iBase4J is released under version 2.0 of the [Apache License][].


[Apache License 2.0]: http://www.apache.org/licenses/LICENSE-2.0
[iBase4J-old]: http://git.oschina.net/iBase4J/iBase4J/tree/NoSplit
[Apache License]: http://www.apache.org/licenses/LICENSE-2.0


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e11b90c4741d83e5192020134f3739ba72d2ad3d5e5a391791bcbaba245003f8721170e26207f47ae06b9025510c2f9e6)