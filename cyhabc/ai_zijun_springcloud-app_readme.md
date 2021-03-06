# springcloud-rbac

## 系统介绍

- spring-cloud-rbac 是以spring-cloud为核心的权限管理框架，技术栈包括：spring-cloud,consul，gateway,hystrix，turbine，zipkin，mybatis、spring-security、redis，业务模块包括：用户管理，角色管理、权限管理，字典管理。

## 业务功能

- 1.用户管理：用户增删改查与角色关系
- 2.角色管理：角色增删改查与权限关系
- 3.菜单管理：菜单增删改查（树形结构）
- 4.字典管理：字典增删改查

## 技术栈

- springcloud 整合
- consul 注册中心
- gateway 路由中心
- turbine 断路器监控聚合
- zipkin 链路监控
- springBoot ioc，aop
- mybatis ORM  
- springsecurity 会话
- redis 缓存

## 部署

- 1.导入数据库脚本springcloud.sql
- 2.启动redis
- 3.启动rabittmq
- 4.启动consul
- 5.启动配置中心config
- 6.启动权限中心system
- 7.启动调度中心schedule
- 8.启动网关中心gateway
- 9.访问端口http://127.0.0.1:1101/html/login.html

## 相关命令

- 1.注册中心启动
consul agent -dev

- 2.链路监控启动
java -jar zipkin-server-2.10.1-exec.jar --zipkin.collector.rabbitmq.addresses=localhost --zipkin.collector.rabbitmq.username=guest --zipkin.collector.rabbitmq.password=guest

- 3.断路器集群监控地址
http://localhost:8989/turbine.stream

- 4.配置中心刷新
curl -X POST http://localhost:8081/actuator/bus-refresh

## qq交流群

- 74745979



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e4fbca0b22f66ac6fa02d862c7ab81dcf9995e5fe8fb62b793f0d0edd3e38a4d7b777ad457a11d392c49e5c45eb43e711)