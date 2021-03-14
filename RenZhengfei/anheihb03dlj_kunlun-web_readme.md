# 昆仑管理系统

  
     
     
     
 

#### 系统介绍
昆仑管理系统是一套基于前后端分离架构的后台管理系统。kunlun-web 基于React + Umi(乌米) + Ant Design (蚂蚁金服) 构建开发，提供前端解决方案；kunlun-service 基于 SpringBoot 与 Spring Cloud 构建开发，提供后端基于微服务架构的解决方案。系统通过Apache Shiro与Jwt组件，用token进行数据交互认证，可快速开发并独立进行Docker容器化部署。

系统模块主要功能（kunlun-web包括kunlun-home-web和kunlun-system-web，kunlun-service包括：kunlun-common-api、kunlun-register-service、kunlun-gateway-service、kunlun-basedata-service和kunlun-system-service）：
 
     
         kunlun-common-api 
         公共模块 
         提供公共基础模型、工具、自动配置、统一异常处理、统一Swagger配置及操作日志AOP等等 
     
     
         kunlun-register-service 
         服务治理 
         服务注册、服务发现、服务心跳检测、高级消息队列(RabbitMQ)及分布式配置中心等 
     
     
         kunlun-gateway-service 
         网关服务 
         服务路由、登录用户校验、鉴权及生成Token、Hystrix的turbine模式配置及Swagger路由配置等 
     
     
         kunlun-basedata-service 
         基础数据 
         提供基础数据支持，如菜单、角色、权限等，并提供基于Redis的分布式缓存功能、基于ElasticSearch + RabbitMQ的服务调用追踪、资源爬取等 
     
     
         kunlun-system-service 
         业务服务 
         业务功能支持服务，提供业务数据、动态数据源、脚本自动执行及基于RabbitMQ的异步操作日志生成功能 
     
     
         kunlun-home-web 
         前端框架 
         提供登录页面、业务菜单、消息待办、主题皮肤、登录人信息及项目布局等 
     
     
         kunlun-system-web 
         前端业务 
         展示系统业务数据及功能页面，如首页信息、人员管理、用户地图、流程管理、操作日志、事项日程、服务资源管理、菜单管理等 
     
 


#### 软件架构
 
     
           
           
     
 


#### 使用说明

1.  npm安装前端依赖库，并启动kunlun-home-web与kunlun-system-web服务；
2.  启动PostgreSQL，执行kunlun-basedata-service与kunlun-system-service服务resources下的sql文件；
3.  启动RabbitMQ和Redis；
4.  启动注册中心kunlun-register-service；
5.  依次启动kunlun-gateway-service、kunlun-basedata-service与kunlun-system-service服务；
6.  访问URL：http://localhost:8000；
7.  输入账号：admin，密码：admin及验证码。


#### 功能说明

1.  统一安全认证中心，支持用户名、密码加图形验证码登录
2.  微服务架构基础支撑，支持服务注册发现、路由与负载均衡，服务熔断与限流，统一配置中心
3.  系统服务监控中心，支持服务调用链监控，微服务监控
4.  系统业务支撑，支持统一跨域处理，统一异常处理，统一处理操作日志，服务内部Swagger接口文档
5.  基于docker容器化部署


#### 工具插件

 
     
         后端框架 
         前端框架 
     
     
         
             
                 
                     核心框架 
                      Spring Boot  
                 
                 
                     服务架构 
                      Spring Cloud  
                 
                 
                     安全框架 
                      apache Shiro 、 Jwt  
                 
                 
                     持久层框架 
                      MyBatis  
                 
                 
                     数据库连接池 
                      Druid  
                 
                 
                     数据库 
                     PosgreSQL、 Redis  
                 
                 
                     工作流引擎 
                      Activiti-5.22.0  
                 
                 
                     脚本执行 
                     Flyway 
                 
                 
                     资源爬取 
                      Selenium  
                 
                 
                     消息组件 
                      RabbitMQ  
                 
                 
                     全局搜索 
                      ElasticSearch  
                 
             
         
         
             
                 
                     前端技术栈 
                      React  
                 
                 
                     前端框架 
                      Umi  
                 
                 
                     数据流框架 
                      Dva  
                 
                 
                     前端UI库 
                      Ant Design  
                 
                 
                     图表库 
                      AntV@G2  
                 
                 
                     图标库 
                      Remix Icon  
                 
                 
                     地图组件 
                      React-amap  
                 
                 
                     富文本编辑器 
                      Braft-editor  
                 
                 
                     HTTP库 
                      Axios  
                 
                 
                     拾色器 
                      React-color  
                 
                 
                     &nbsp; 
                     &nbsp; 
                 
             
         
     
 


#### 页面截图

 
     
           
           
           
     
     
           
	   
           
     
     
           
           
	   
     
     
           
	   
           
     
     
           
           
	   
     
     
           
	   
           
     
     
           
           
	   
     
     
           
	   
           
     
     
           
           
           
     
 



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e695604aa5d5ed6f53a678d04760678d4254251c9f772480d1273a08b6458da912089d0ef1f720af1988aeaaaecf53cf2)