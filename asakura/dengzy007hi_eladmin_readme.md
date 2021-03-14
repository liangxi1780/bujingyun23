 EL-ADMIN 后台管理系统 
 

[![AUR](https://img.shields.io/badge/license-Apache%20License%202.0-blue.svg)](https://github.com/elunez/eladmin/blob/master/LICENSE)
[![star](https://gitee.com/elunez/eladmin/badge/star.svg?theme=white)](https://gitee.com/elunez/eladmin)
[![GitHub stars](https://img.shields.io/github/stars/elunez/eladmin.svg?style=social&label=Stars)](https://github.com/elunez/eladmin)
[![GitHub forks](https://img.shields.io/github/forks/elunez/eladmin.svg?style=social&label=Fork)](https://github.com/elunez/eladmin)

 

#### 项目简介
一个基于 Spring Boot 2.1.0 、 Spring Boot Jpa、 JWT、Spring Security、Redis、Vue的前后端分离的后台管理系统

**开发文档：**  [https://el-admin.vip](http://u.720life.cn/g/e8b18fae46c3fd1d2190dc2d09befb78944309aa0accad13dbfdd2f054024a73)

**体验地址：**  [https://el-admin.xin](http://u.720life.cn/g/e8b18fae46c3fd1d2190dc2d09befb78582c996c0cfe65e10599a3bf84d2cac9)

**账号密码：** `admin / 123456`

#### 项目源码

|     |   后端源码  |   前端源码  |
|---  |--- | --- |
|  github   |  https://github.com/elunez/eladmin   |  https://github.com/elunez/eladmin-web   |
|  码云   |  https://gitee.com/elunez/eladmin   |  https://gitee.com/elunez/eladmin-web   |

#### 主要特性
- 使用最新技术栈，社区资源丰富。
- 高效率开发，代码生成器可一键生成前后端代码
- 支持数据字典，可方便地对一些状态进行管理
- 支持接口限流，避免恶意请求导致服务层压力过大
- 支持接口级别的功能权限与数据权限，可自定义操作
- 自定义权限注解与匿名接口注解，可快速对接口拦截与放行
- 对一些常用地前端组件封装：表格数据请求、数据字典等
- 前后端统一异常拦截处理，统一输出异常，避免繁琐的判断
- 支持在线用户管理与服务器性能监控，支持限制单用户登录
- 支持运维管理，可方便地对远程服务器的应用进行部署与管理

####  系统功能
- 用户管理：提供用户的相关配置，新增用户后，默认密码为123456
- 角色管理：对权限与菜单进行分配，可根据部门设置角色的数据权限
- 菜单管理：已实现菜单动态路由，后端可配置化，支持多级菜单
- 部门管理：可配置系统组织架构，树形表格展示
- 岗位管理：配置各个部门的职位
- 字典管理：可维护常用一些固定的数据，如：状态，性别等
- 系统日志：记录用户操作日志与异常日志，方便开发人员定位拍错
- SQL监控：采用druid 监控数据库访问性能，默认用户名admin，密码123456
- 定时任务：整合Quartz做定时任务，加入任务日志，任务运行情况一目了然
- 代码生成：高灵活度生成前后端代码，减少大量重复的工作任务
- 邮件工具：配合富文本，发送html格式的邮件
- 免费图床：使用sm.ms图床，用作公共图片上传使用，该图床不怎么稳定，不太建议使用
- 七牛云存储：可同步七牛云存储的数据到系统，无需登录七牛云直接操作云数据
- 支付宝支付：整合了支付宝支付并且提供了测试账号，可自行测试
- 服务监控：监控服务器的负载情况
- 运维管理：一键部署你的应用

#### 项目结构
项目采用按功能分模块的开发方式，结构如下

- `eladmin-common` 为系统的公共模块，各种工具类，公共配置存在该模块

- `eladmin-system` 为系统核心模块也是项目入口模块，也是最终需要打包部署的模块

- `eladmin-logging` 为系统的日志模块，其他模块如果需要记录日志需要引入该模块

- `eladmin-tools` 为第三方工具模块，包含：图床、邮件、云存储、本地存储、支付宝

- `eladmin-generator` 为系统的代码生成模块，代码生成的模板在 system 模块中

#### 详细结构

```
- eladmin-common 公共模块
    - annotation 为系统自定义注解
    - aspect 自定义注解的切面
    - base 提供了Entity、DTO基类和mapstruct的通用mapper
    - config 自定义权限实现、redis配置、swagger配置、Rsa配置等
    - exception 项目统一异常的处理
    - utils 系统通用工具类
- eladmin-system 系统核心模块（系统启动入口）
	- config 配置跨域与静态资源，与数据权限
	    - thread 线程池相关
	- modules 系统相关模块(登录授权、系统监控、定时任务、运维管理等)
- eladmin-logging 系统日志模块
- eladmin-tools 系统第三方工具模块
- eladmin-generator 系统代码生成模块
```
    
#### 系统预览
 
     
           
           
     
     
           
           
     
     
           
           
     
     
           
           
     
 

#### 特别鸣谢

- 感谢 [JetBrains](http://u.720life.cn/g/a27ddb2b79548d3a829f3f0224b2480df14d1ffd85a4ccde00704ed260130e46) 提供的非商业开源软件开发授权

- 感谢 [PanJiaChen](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304603c6efa7d0c1ce77680f5b6f938bd6cef861f7dd6d31dc89ca07ef0b5d2b912f) 大佬提供的前端模板

- 感谢 [Moxun](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046f1b6e98a14e45e669721135af994ebd5) 大佬提供的前端 Curd 通用组件

- 感谢 [zhy6599](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ebbddea5af9395aecada70800b5551b82) 大佬提供的后端运维管理相关功能

- 感谢 [j.yao.SUSE](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304696f636b4a119cb1b4341a3bd104a9be6f23cc0696675a5eeb40a638dcd892f5e) 大佬提供的匿名接口与Redis限流等功能

- 感谢 [d15801543974](http://u.720life.cn/g/54145d0471d91890860f7f8463c030465a1b6199fdf73961c2a66fde6fb023ea) 大佬提供的基于注解的通用查询方式

#### 项目捐赠
项目的发展离不开你的支持，请作者喝杯咖啡吧☕  [Donate](http://u.720life.cn/g/e8b18fae46c3fd1d2190dc2d09befb782c19e0425e3faaf13215106a6528069b)

#### 反馈交流
- QQ交流群：891137268



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e509ef915e1a7c41cb26bfa2f238d524848e70ed4b4c2bd21c38cb61e2e3ecf2e7b09a54e81b9124ff642c1d7e8a4aee4)