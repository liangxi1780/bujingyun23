# mallcloud-platform

[![License](https://img.shields.io/badge/license-Apache%202-4EB1BA.svg)]
(http://u.720life.cn/g/9504ecfd7de2b26345fb4a78087ff8e39017fae1e889f3875d0fa1b09af9991c931ea6d4bfd7167edd1bb141581029dc)        

## 如果您觉得有帮助，请点右上角 "Star" 支持一下谢谢

[TOC]

## 1. 项目介绍

* **技术交流群** [ 195405248 ]
* **详细在线文档** [点击查看](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046e6d835ecf4b774474fd4ca3d48d64470672dbad0fff069a7bd7a1f167ce5398a9a11cde73f6c3ce9c62e57ca4fef4cdbb45055bc5bde065b0ae241546c62501d3d516535615f7a853f7ca092177c677e)
* **演示地址**
  * url： [http://www.yjlive.cn:8090/#/login](http://u.720life.cn/g/72b220e9d9b022ec995e86dfc1d023e0482028707eb50d1d23d50ee52f8b56e79382dbfa849dc5e26387a1c387d73024)
  * 账号密码：admin/admin
  * 应用监控账号密码：admin/admin
  * 配置中心账号密码：nacos/nacos
  * APM监控账号密码：admin/admin
  * Grafana账号：mall/mall
  * txlcn事务管理器密码：admin
  * 任务管理账号密码：admin/123456
* **演示环境有全方位的监控示例：日志系统 + APM系统 + GPE系统**

* Gitee地址：https://gitee.com/catshen/mallcloud-platform
* Github地址：https://github.com/shenzhuan/mallcloud

>   发布页面 http://m3w.cn/mallcloud  
>   h5地址  http://www.yjlive.cn:8082/#/ 
>  后台管理地址 http://www.yjlive.cn:8090 
>  小程序体验码
>  ![输入图片说明](https://images.gitee.com/uploads/images/2019/0621/100856_b901ecef_134431.png "屏幕截图.png")
>  app体验 加群下载
>  apk下载 链接: https://pan.baidu.com/s/1UiFtg3AQ2-muNjfQjsjXPw 提取码: nda2

* 前后端分离的企业级微服务架构
* 基于`Spring Boot 2.0.X`、`Spring Cloud Finchley`和`Spring Cloud Alibaba`
* 深度定制`Spring Security`真正实现了基于`RBAC`、`jwt`和`oauth2`的无状态统一权限认证的解决方案
* 提供应用管理，方便第三方系统接入
* 引入组件化的思想实现高内聚低耦合，项目代码简洁注释丰富上手容易
* 注重代码规范，严格控制包依赖，每个工程基本都是最小依赖
* 非常适合学习和企业中使用
> cloud框架和组件来源：https://gitee.com/owenwangwen/open-capacity-platform
https://gitee.com/zlt2000/microservices-platform
> 业务逻辑来源：https://github.com/shenzhuan/mallplus

&nbsp;

## 2. 项目总体架构图

![](http://processon.com/chart_image/5c7f2ad6e4b02b2ce48d6835.png?_=1554621571250)

&nbsp;

## 3. 功能介绍

* **统一认证功能**
  * 支持oauth2的四种模式登录
  * 支持用户名、密码加图形验证码登录
  * 支持手机号加密码登录
  * 支持openId登录
  * 支持第三方系统单点登录

* **分布式系统基础支撑**
  * 服务注册发现、路由与负载均衡
  * 服务降级与熔断
  * 服务限流(url/方法级别)
  * 统一配置中心
  * 统一日志中心
  * 统一分布式缓存操作类、cacheManager配置扩展
  * 分布式锁
  * 分布式任务调度器
  * 支持CI/CD持续集成(包括前端和后端)
  * 分布式高性能Id生成器
  * 分布式事务
* **系统监控功能**
  * 服务调用链监控
  * 应用拓扑图
  * 慢服务检测
  * 服务Metric监控
  * 应用监控(应用健康、JVM、内存、线程)
  * 错误日志查询
  * 慢查询SQL监控
  * 应用吞吐量监控(qps、rt)
  * 服务降级、熔断监控
  * 服务限流监控
  * 分库分表、读写分离
* **业务基础功能支撑**
  * 高性能方法级幂等性支持
  * RBAC权限管理，实现细粒度控制(方法、url级别)
  * 快速实现导入、导出功能
  * 数据库访问层自动实现crud操作
  * 代码生成器
  * 基于Hutool的各种便利开发工具
  * 网关聚合所有服务的Swagger接口文档
  * 统一跨域处理
  * 统一异常处理

&nbsp;

## 4. 模块说明

```lua
mallcloud -- 父项目，公共依赖
│  ├─mall-business -- 业务模块一级工程
│  │  ├─user-center -- 用户中心[7000]
│  │  ├─file-center -- 文件中心[5000]
│  │  ├─member-center -- 会员中心[7001]
│  │  ├─goods-center -- 商品中心[7002]
│  │  ├─order-center -- 订单中心[7003]
│  │  ├─marking-center -- 营销中心[7004]
│  │─mall-commons -- 通用工具一级工程
│  │  ├─mall-auth-client-spring-boot-starter -- 封装spring security client端的通用操作逻辑
│  │  ├─mall-common-spring-boot-starter -- 封装通用操作逻辑
│  │  ├─mall-db-spring-boot-starter -- 封装数据库通用操作逻辑
│  │  ├─mall-log-spring-boot-starter -- 封装log通用操作逻辑
│  │  ├─mall-redis-spring-boot-starter -- 封装Redis通用操作逻辑
│  │  ├─mall-ribbon-spring-boot-starter -- 封装Ribbon和Feign的通用操作逻辑
│  │  ├─mall-sentinel-spring-boot-starter -- 封装Sentinel的通用操作逻辑
│  │  ├─mall-swagger2-spring-boot-starter -- 封装Swagger通用操作逻辑
│  ├─mall-config -- 配置中心
│  ├─mall-doc -- 项目文档
│  ├─mall-gateway -- api网关一级工程
│  │  ├─zuul-gateway -- netflix-zuul[8080]
│  ├─mall-job -- 分布式任务调度一级工程
│  │  ├─job-admin -- 任务管理器[8081]
│  │  ├─job-core -- 任务调度核心代码
│  │  ├─job-executor-samples -- 任务执行者executor样例[8082]
│  ├─mall-monitor -- 监控一级工程
│  │  ├─sc-admin -- 应用监控[6500]
│  │  ├─log-center -- 日志中心[6200]
│  ├─mall-uaa -- spring-security认证中心[8000]
│  ├─mall-register -- 注册中心Nacos[8848]
│  ├─mall-transaction -- 事务一级工程
│  │  ├─txlcn-tm -- tx-lcn事务管理器[7970]
│  ├─mall-demo -- demo一级工程
│  │  ├─txlcn-demo -- txlcn的demo
│  │  ├─sharding-jdbc-demo -- sharding-jdbc的demo
```

&nbsp;
关注公众号


 
后台功能列表
 
小程序功能列表
 

 **_uniapp_** 

uni-app 是一个使用 Vue.js 开发跨平台应用的前端框架，开发者编写一套代码，可编译到iOS、Android、H5、小程序等多个平台。

 


## 5. 截图（点击可大图预览）

 
	 
           
           
     
	 
           
           
     
     
           
           
     
     
           
           
     
     
           
           
     
     
           
           
     
     
           
           
     
 





 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e2b4bf7bb8b9c1dea358131d4554906c139b4f4a2c95b9a5ced4fac80bd2d29942ff3570402ae9a02598e4d6ee094c70f11c07bcb3357792f49e756dc92bb6015)