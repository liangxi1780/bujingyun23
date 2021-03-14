# Cloud-Admin(`开源项目`）
Cloud-Admin是国内首个基于`Spring Cloud`微`服务`化`开发平台`，具有统一授权、认证后台管理系统，其中包含具备用户管理、资源权限管理、网关API管理等多个模块，支持多业务系统并行开发，可以作为后端服务的开发脚手架。代码简洁，架构清晰，适合学习和直接项目中使用。核心技术采用`Spring Boot2`以及`Spring Cloud (Finchley.M8)`相关核心组件，前端采用`vue-element-admin`组件。 QQ群号：169824183

## 该项目由他人进行维护，最新地址：https://gitee.com/minull/ace-security

## 新课程筹备：Spring Cloud多租户实现，[点击查看](http://u.720life.cn/g/cfa9b519e52d9ef0bd47e1ddb695823695631520d927db2fb4402418de65ab29)

# Cloud-Enterprise（`企业效率`）[点击打开](http://u.720life.cn/g/cfa9b519e52d9ef0bd47e1ddb695823632540c11aee819a26e2ce38e95f67425)

### 开源用户登记，宣传用：[点击打开](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e9f262acdcf59d7c03fc43cd47016a301c39ba9d8f5dcf27d391b642c6300e106f715ea4aa4c79b02d87a226f85b26a28)
### 最新更新日志，[点击查看](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e9f262acdcf59d7c03fc43cd47016a301669ee75c2d5bd0fccb18d9bda1a0acd30f8b3dd3d658fc8563ddba0ce1dabc62504f16c7f861e957e92e3126f633b6f06db134268da7459e8e4dfd737928ed8f)

# 模块说明
![image.png](http://upload-images.jianshu.io/upload_images/5700335-8d69f4e885a4ec85.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

### 架构摘要
#### 服务鉴权
老A独有的通过`JWT`的方式来加强服务之间调度的权限验证，保证内部服务的安全性。

#### 监控
利用Spring Boot Admin 来监控各个独立Service的运行状态；利用Hystrix Dashboard来实时查看接口的运行状态和调用频率等。

#### 负载均衡
将服务保留的rest进行代理和网关控制，除了平常经常使用的node.js、nginx外，Spring Cloud系列的zuul和ribbon，可以帮我们进行正常的网关管控和负载均衡。其中扩展和借鉴国外项目的扩展基于JWT的`Zuul限流插件`，方面进行限流。

#### 服务注册与调用
基于Eureka来实现的服务注册与调用，在Spring Cloud中使用Feign, 我们可以做到使用HTTP请求远程服务时能与调用本地方法一样的编码体验，开发者完全感知不到这是远程方法，更感知不到这是个HTTP请求。

#### 熔断机制
因为采取了服务的分布，为了避免服务之间的调用“雪崩”，采用了`Hystrix`的作为熔断器，避免了服务之间的“雪崩”。

------

# `启动指南`

## 后端工程启动

### 项目结构
```
├─ace-security
│  │  
│  ├─ace-modules--------------公共服务模块（基础系统、搜索、OSS）
│  │ 
│  ├─ace-auth-----------------服务鉴权中心
│  │ 
│  ├─ace-oauth----------------用户认证中心
│  │ 
│  ├─ace-gate-----------------网关负载中心
│  │ 
│  ├─ace-common---------------通用脚手架
│  │ 
│  ├─ace-center---------------服务注册中心
│  │   
│  ├─ace-control--------------运维中心（监控、链路）
│  │
│  └─ace-sidebar--------------调用第三方语言
│
```

### 环境须知
- mysql一个，redis一个，rabbitmq一个
- jdk1.8
- IDE插件一个，`lombok插件`，具体百度即可

### 须知
因为AG-Admin是一个`前后端分离`的项目，所以后端的服务必须先启动，在后端服务启动完成后，再启动前端的工程。

### 最多人问：代码有漏
下载完后端代码后，记得先安装`lombok插件`，否则你的IDE会报代码缺失。

### 运行步骤
- 运行数据库脚本：依次运行数据库：ace-admin/db/init.sql、ace-auth-server/db/init.sql、ace-trace
- 修改配置数据库配置：ace-admin/src/main/resources/application.yml、ace-gate/src/main/resources/application.yml
- 按`顺序`运行main类：CenterBootstrap（ace-center）、AuthBootstrap（ace-auth-server）、AdminBootstrap（ace-admin）、GatewayServerBootstrap（ace-gateway-v2）

----

## UI工程启动[Cloud-Admin-UI][点击打开](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e36d79e3de7c3d8393231b7d2877d1ee659175147a69892076ef94a3f5d09b629)

### 环境搭建
```
node 版本：v6.11.2
npm 版本：3.10.10
```

### 开发（在UI目录下）

```bash
    
    # 安装依赖
    npm install

    ## 若上述不行则采取下面命令
    npm install --registry=https://registry.npm.taobao.org

    # 本地开发 开启服务
    npm run dev
```

浏览器访问 http://localhost:9527

### 发布
```bash
    # 构建生成环境
    npm run build:prod
```

### 目录结构
```shell
├── build                      // 构建相关  
├── config                     // 配置相关
├── src                        // 源代码
│   ├── api                    // 所有请求
│   ├── assets                 // 主题 字体等静态资源
│   ├── components             // 全局公用组件
│   ├── directive              // 全局指令
│   ├── filtres                // 全局filter
│   ├── mock                   // mock数据
│   ├── router                 // 路由
│   ├── store                  // 全局store管理
│   ├── styles                 // 全局样式
│   ├── utils                  // 全局公用方法
│   ├── view                   // view
│   ├── App.vue                // 入口页面
│   └── main.js                // 入口 加载组件 初始化等
├── static                     // 第三方不打包资源
│   └── Tinymce                // 富文本
├── .babelrc                   // babel-loader 配置
├── eslintrc.js                // eslint 配置项
├── .gitignore                 // git 忽略项
├── favicon.ico                // favicon图标
├── index.html                 // html模板
└── package.json               // package.json

```
------------

## 功能截图
### 基本功能

![img](http://upload-images.jianshu.io/upload_images/5700335-002735d1727ec11b.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![img](http://upload-images.jianshu.io/upload_images/5700335-e5e56924aaeacf1e.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![img](http://upload-images.jianshu.io/upload_images/5700335-b3044673b4a55203.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![img](http://upload-images.jianshu.io/upload_images/5700335-75151a17ae4319cf.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![img](http://upload-images.jianshu.io/upload_images/5700335-ab942829c130389e.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![img](http://upload-images.jianshu.io/upload_images/5700335-30e6df679695f150.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![img](http://upload-images.jianshu.io/upload_images/5700335-347e3e761188a824.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![img](http://upload-images.jianshu.io/upload_images/5700335-569696e4e70e5ad2.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)




## License
Apache License Version 2.0




 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6edcabdfaf30d9a7cd341976fd10006b658b69e509603cbf1e5e6b2aeb5b1e9aa39979fae7ace7d3d5b8abfb7f25d65407)