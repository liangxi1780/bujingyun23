# central-platform


  
  
   
   

 

### 欢迎进群（群内领资料）

`一键加群`

   

![](https://i.imgur.com/kxpc628.png)

#### 项目介绍
从无到有搭建企业级微服务框架，为企业级项目提供一套完善的，运行稳定，多种分布式问题的解决方案;

central-platform简称CP，基于Spring Cloud(Cloud-Finchley.SR2) 、Spring Boot(2.0.2.RELEASE)
集成layui前后分离的开发平台,其中包括Gateway网关、Oauth认证服务、User用户服务、
Eureka注册中心等多个服务, 为微服务开发所需配置管理、服务发现、断路器、智能路由、
微代理等,努力为企业级打造最全面的微服务开发解决方案;




# 组织结构
central-platform

| 名称      | 项目名称            | 说明                                       |
| ------- | --------------- | ---------------------------------------- |
| API工具包  | api-commons     | 存放Model层，和部分工具类                          |
| Cloud网关 | api-gateway     | 基于Spring Cloud构建gateway网关服务，采用OAuth2.0认证体系，管理所有服务的负载，可以集群部署； |
| 业务中心    | business-center | 主要包括前端项目，用户中心，文件中心等服务                    |
| 配置中心    | config-center   | 配置中心，管理整个微服务的配置;                         |
| 数据封装    | db-core         | 数据库逻辑封装                                  |
| 任务中心    | job-center      | 基于xxl-job实现的Demo，可以直接使用                  |
| 监控中心    | monitor-center  | 基于Spring Boot Admin，对应用状态进行监控，对服务调用进行追踪和对熔断进行监测;集成zipkin链式追踪服务 |
| 认证中心    | oauth-center    | 基于SpringSecurity进行安全认证，采用OAuth2.0认证体系，对客户端、用户进行认证及授权，支持多种模式； |
| 注册中心    | register-center | 采用Euraka构建服务注册中心，负责服务注册于发现               |
| 脚本模块    | sql             | 存放sql脚本                                  |


#### 演示地址

http://59.110.164.254:8066 

账号/密码
admin/admin

#### 安装教程

1.下载代码

```
 git clone https://gitee.com/GeekPerson/central-platform.git
```

2.启动对应的服务

a.先启动 register-center 注册中心的 eureka-server 注册服务

b.在启动 api-gateway 网关服务

c.再启动 oauth-center 认证中心 oauth-server 认证服务

d.在启动 business-center 业务中心的 对应服务 file-center user-center back-center

e.启动 monitor-center 监控中心 admin-server zipkin-center



完整教程可以加群联系开源作者，因一些七牛OSS账号 和 邮箱账号问题；请按照对应的配置进行设置

![](https://gitee.com/GeekPerson/central-platform/raw/master/z-doc/images/%E6%9C%AA%E6%A0%87%E9%A2%98-1.jpg)

#### 截图预览 

![](https://gitee.com/GeekPerson/central-platform/raw/master/z-doc/images/QQ%E6%88%AA%E5%9B%BE20180827235123.png)

用户管理

![](https://gitee.com/GeekPerson/central-platform/raw/master/z-doc/images/QQ%E6%88%AA%E5%9B%BE20180827235514.png)

角色管理

![](https://gitee.com/GeekPerson/central-platform/raw/master/z-doc/images/QQ%E6%88%AA%E5%9B%BE20180827235606.png)

菜单管理

![](https://gitee.com/GeekPerson/central-platform/raw/master/z-doc/images/QQ%E6%88%AA%E5%9B%BE20180827235658.png)

权限管理

![](https://gitee.com/GeekPerson/central-platform/raw/master/z-doc/images/QQ%E6%88%AA%E5%9B%BE20180827235729.png)

应用管理

![](https://gitee.com/GeekPerson/central-platform/raw/master/z-doc/images/QQ%E6%88%AA%E5%9B%BE20180827235806.png)

token管理

![](https://gitee.com/GeekPerson/central-platform/raw/master/z-doc/images/QQ%E6%88%AA%E5%9B%BE20180827235841.png)

监控中心

![](https://gitee.com/GeekPerson/central-platform/raw/master/z-doc/images/QQ%E6%88%AA%E5%9B%BE20180827235915.png)

文档中心

![](https://gitee.com/GeekPerson/central-platform/raw/master/z-doc/images/QQ%E6%88%AA%E5%9B%BE20180827235941.png)

Zipkin监控

![](https://gitee.com/GeekPerson/central-platform/raw/master/z-doc/images/QQ%E6%88%AA%E5%9B%BE20180828001041.png)

文件中心
![](https://gitee.com/GeekPerson/central-platform/raw/master/z-doc/images/QQ%E6%88%AA%E5%9B%BE20180828001120.png)

个人信息

![](https://gitee.com/GeekPerson/central-platform/raw/master/z-doc/images/QQ%E6%88%AA%E5%9B%BE20180828001208.png)

任务调度
![](https://gitee.com/GeekPerson/central-platform/raw/master/z-doc/images/QQ%E6%88%AA%E5%9B%BE20180901233132.png)


![](https://gitee.com/GeekPerson/central-platform/raw/master/z-doc/images/QQ%E6%88%AA%E5%9B%BE20180901233301.png)


![](https://gitee.com/GeekPerson/central-platform/raw/master/z-doc/images/QQ%E6%88%AA%E5%9B%BE20180901233320.png)



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e8a6c9f14497665db81c89ed2841b4b77edcfb127fa0cd77f1c1a3545e3ba9b6843b399740b8f6a68ec6dd6e490fd0a493c0075e48174679e7944e2a0e920d791)