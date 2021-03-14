# mall

 
     
     
     
     
     
     
     
 

## 前言

`mall`项目致力于打造一个完整的电商系统，采用现阶段流行技术实现。

## 项目文档

- 文档地址：[http://www.macrozheng.com](http://u.720life.cn/g/4be43d4431b74113e94135d65b656655cd96a5080e7b0355478a11a3a41c913c)
- 备用地址：[https://macrozheng.github.io/mall-learning](http://u.720life.cn/g/e01ef929783d0ec15a491ae173b16c03b77a8a82ac3635dfbad31c2820c23744cc90eebbf7570092e79aaf46b44a6e00)

## 项目介绍

`mall`项目是一套电商系统，包括前台商城系统及后台管理系统，基于SpringBoot+MyBatis实现。前台商城系统包含首页门户、商品推荐、商品搜索、商品展示、购物车、订单流程、会员中心、客户服务、帮助中心等模块。后台管理系统包含商品管理、订单管理、会员管理、促销管理、运营管理、内容管理、统计报表、财务管理、权限管理、设置等模块。

### 项目演示

#### 后台管理系统

前端项目`mall-admin-web`地址：https://github.com/macrozheng/mall-admin-web

项目演示地址： [http://www.macrozheng.com/admin/index.html](http://u.720life.cn/g/4be43d4431b74113e94135d65b6566555054465abe0fa2ad2b8ce6e41db2f38fd851d13461cae50f1f7715249c222ee7)  

![后台管理系统功能演示.gif](/document/resource/mall-admin.gif)

#### 前台商城系统

前端项目`mall-app-web`地址：敬请期待......

项目演示地址：[http://www.macrozheng.com/app/index.html](http://u.720life.cn/g/4be43d4431b74113e94135d65b6566550f4c8ab22f296364d97c779587e2667e1ef0b670e981b391ae2eb808ce60cc23)

![前台商城系统功能演示.gif](/document/resource/mall-app.gif)

### 组织结构

``` lua
mall
├── mall-common -- 工具类及通用代码
├── mall-mbg -- MyBatisGenerator生成的数据库操作代码
├── mall-security -- SpringSecurity封装公用模块
├── mall-admin -- 后台商城管理系统接口
├── mall-search -- 基于Elasticsearch的商品搜索系统
├── mall-portal -- 前台商城系统接口
└── mall-demo -- 框架搭建时的测试代码
```

### 技术选型

#### 后端技术

| 技术                 | 说明                | 官网                                                         |
| -------------------- | ------------------- | ------------------------------------------------------------ |
| SpringBoot           | 容器+MVC框架        | [https://spring.io/projects/spring-boot](http://u.720life.cn/g/c6d1b26d763f49c99d62f7dd7e1f263d74791681f9785d83f6cd6c957366ad1debb29bb8c32cd47aff960e71f7893090) |
| SpringSecurity       | 认证和授权框架      | [https://spring.io/projects/spring-security](http://u.720life.cn/g/c6d1b26d763f49c99d62f7dd7e1f263d74791681f9785d83f6cd6c957366ad1d51f22cbfad230da539bef50203caf238) |
| MyBatis              | ORM框架             | [http://www.mybatis.org/mybatis-3/zh/index.html](http://u.720life.cn/g/5d88e5a59ccc688f2e74c4a956a26a215e4d93221eb26b660bea25686b89be63142caf406b6e1c14d3ab51db921e10ca) |
| MyBatisGenerator     | 数据层代码生成      | [http://www.mybatis.org/generator/index.html](http://u.720life.cn/g/5d88e5a59ccc688f2e74c4a956a26a21a07057a36d6ca5ea426a94333449b8ee4a9090aa94e48705a0a12124d68034da) |
| PageHelper           | MyBatis物理分页插件 | [http://git.oschina.net/free/Mybatis_PageHelper](http://u.720life.cn/g/5c954f4cd4204fb6c09a7e58aa70844d0c5e449aa2c2e2afac3f4646cf34dfd65ceb51a277771277d2a7f535bcbaead3) |
| Swagger-UI           | 文档生产工具        | [https://github.com/swagger-api/swagger-ui](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046ee873d8b7265bda98dbeb1b913855dc8cc8fe4f2d8a7cf6393aeda706a915000) |
| Hibernator-Validator | 验证框架            | [http://hibernate.org/validator/](http://u.720life.cn/g/09d74cfb02196ca3ed0ec52b685384e1fd96db6373856c92099520b41f86fef5) |
| Elasticsearch        | 搜索引擎            | [https://github.com/elastic/elasticsearch](http://u.720life.cn/g/54145d0471d91890860f7f8463c030466e836c5dd85610d86e6f01486f462e2c0d9e4b426066af1ff2b4626bce8b1132) |
| RabbitMq             | 消息队列            | [https://www.rabbitmq.com/](http://u.720life.cn/g/0fa33e240a4f68a032ffc0865d7dcd1fb673b17d4773e9f52139fbece79cad2e)       |
| Redis                | 分布式缓存          | [https://redis.io/](http://u.720life.cn/g/70336383bbe1092dca9fcec94f2fd10823c1cea91ac1108405bfbd56f5b819fc)                       |
| MongoDb              | NoSql数据库         | [https://www.mongodb.com/](http://u.720life.cn/g/5b6081b126093fbb42e8289314c4c63edef09cba29820afcfda6f238d141f89a)         |
| Docker               | 应用容器引擎        | [https://www.docker.com/](http://u.720life.cn/g/d13d2b0ef4a5c92b4f4a6e9ed4270e65b90c4c1e1b506e1a501feef81ad769e9)           |
| Druid                | 数据库连接池        | [https://github.com/alibaba/druid](http://u.720life.cn/g/54145d0471d91890860f7f8463c030464e9ab1ba10d3588ded212abb6198c62a) |
| OSS                  | 对象存储            | [https://github.com/aliyun/aliyun-oss-java-sdk](http://u.720life.cn/g/54145d0471d91890860f7f8463c030463acc10ac40ebe392ae83d014e0e2b286fe9c84bf686fc8dede39c92bd0288ee5) |
| JWT                  | JWT登录支持         | [https://github.com/jwtk/jjwt](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304637710c50c45b7e4b55624adcef685c65) |
| LogStash             | 日志收集工具        | [https://github.com/logstash/logstash-logback-encoder](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304669aa5c06d8130c325d1bfa13fdfd08726e2d71470b343aedcffc515849eb90f4b7fea92e7eced4cc00b62438ea6c9e83) |
| Lombok               | 简化对象封装工具    | [https://github.com/rzwitserloot/lombok](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304667e1b2f7ca2a7abf102cdf9e5fa5070a803dc1dd5f1c376fd8d7fb727fc2defd) |

#### 前端技术

| 技术       | 说明                  | 官网                                                         |
| ---------- | --------------------- | ------------------------------------------------------------ |
| Vue        | 前端框架              | [https://vuejs.org/](http://u.720life.cn/g/1c3db3fec6433a3fb191bb48af91f3bb055304712f0641658c814ca15fec0089)                     |
| Vue-router | 路由框架              | [https://router.vuejs.org/](http://u.720life.cn/g/7bedfe02707a57b283aa65bf169b40685a2bcc51af184101de4b71f45db846fa)       |
| Vuex       | 全局状态管理框架      | [https://vuex.vuejs.org/](http://u.720life.cn/g/acea3f53396a46112876052cae0a3648a88a7ed218d2be0ffa10fc982c11ad04)           |
| Element    | 前端UI框架            | [https://element.eleme.io/](http://u.720life.cn/g/5fa51553afae358345e9f20b5a6e741569ec367dcef795a9cc086ceba9a9242d)       |
| Axios      | 前端HTTP框架          | [https://github.com/axios/axios](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304638015ac6a54b1cadf0934b8a0d5637d0) |
| v-charts   | 基于Echarts的图表框架 | [https://v-charts.js.org/](http://u.720life.cn/g/04bb650c6b9547d2ac7f61bed3e715031e418e4efd3cee1a70120fe3eff14e14)         |
| Js-cookie  | cookie管理工具        | [https://github.com/js-cookie/js-cookie](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304601a18a0a98543c227ccab0f66e611f0076dc75769652863fa8e48c713794768c) |
| nprogress  | 进度条控件            | [https://github.com/rstacruz/nprogress](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304621051bfe8a14df709920d1b59773b4a1b34b830a15281032ae36824abb143cae) |

#### 架构图

##### 系统架构图

![系统架构图](document/resource/mall_micro_service_arch.jpg)

##### 业务架构图

![系统架构图](document/resource/mall_business_arch.png)

#### 模块介绍

##### 后台管理系统 `mall-admin`

- 商品管理：[功能结构图-商品.jpg](document/resource/mind_product.jpg)
- 订单管理：[功能结构图-订单.jpg](document/resource/mind_order.jpg)
- 促销管理：[功能结构图-促销.jpg](document/resource/mind_sale.jpg)
- 内容管理：[功能结构图-内容.jpg](document/resource/mind_content.jpg)
- 用户管理：[功能结构图-用户.jpg](document/resource/mind_member.jpg)

##### 前台商城系统 `mall-portal`

[功能结构图-前台.jpg](document/resource/mind_portal.jpg)

#### 开发进度

![项目开发进度图](document/resource/mall_dev_flow.png)

## 环境搭建

### 开发工具

| 工具          | 说明                | 官网                                            |
| ------------- | ------------------- | ----------------------------------------------- |
| IDEA          | 开发IDE             | https://www.jetbrains.com/idea/download         |
| RedisDesktop  | redis客户端连接工具 | https://redisdesktop.com/download               |
| Robomongo     | mongo客户端连接工具 | https://robomongo.org/download                  |
| SwitchHosts   | 本地host管理        | https://oldj.github.io/SwitchHosts/             |
| X-shell       | Linux远程连接工具   | http://www.netsarang.com/download/software.html |
| Navicat       | 数据库连接工具      | http://www.formysql.com/xiazai.html             |
| PowerDesigner | 数据库设计工具      | http://powerdesigner.de/                        |
| Axure         | 原型设计工具        | https://www.axure.com/                          |
| MindMaster    | 思维导图设计工具    | http://www.edrawsoft.cn/mindmaster              |
| ScreenToGif   | gif录制工具         | https://www.screentogif.com/                    |
| ProcessOn     | 流程图绘制工具      | https://www.processon.com/                      |
| PicPick       | 图片处理工具        | https://picpick.app/zh/                         |
| Snipaste      | 屏幕截图工具        | https://www.snipaste.com/                       |

### 开发环境

| 工具          | 版本号 | 下载                                                         |
| ------------- | ------ | ------------------------------------------------------------ |
| JDK           | 1.8    | https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html |
| Mysql         | 5.7    | https://www.mysql.com/                                       |
| Redis         | 3.2    | https://redis.io/download                                    |
| Elasticsearch | 6.2.2  | https://www.elastic.co/downloads                             |
| MongoDb       | 3.2    | https://www.mongodb.com/download-center                      |
| RabbitMq      | 3.7.14 | http://www.rabbitmq.com/download.html                        |
| Nginx         | 1.10   | http://nginx.org/en/download.html                            |

### 搭建步骤

> Windows环境部署

- Windows环境搭建请参考：[mall在Windows环境下的部署](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046792cbfb2e1cb72d9aec12faeaa3f53b4af0e5608fba7f311ac1f4b4100ca1badc63fa25bf4e4f98a0108b9d45f6d84d26330f60de907ca7f270a41cb1e0b87465d64b4c68ce7b36830d9a2dd11705cd5);
- 注意：只启动mall-admin,仅需安装mysql即可;
- 克隆`mall-admin-web`项目，并导入到IDEA中完成编译[传送门](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046792cbfb2e1cb72d9aec12faeaa3f53b42e4d30c010195bd4dbc551cbb6dc82da);
- `mall-admin-web`项目的安装及部署请参考：[mall前端项目的安装与部署](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046792cbfb2e1cb72d9aec12faeaa3f53b4af0e5608fba7f311ac1f4b4100ca1badc63fa25bf4e4f98a0108b9d45f6d84d26330f60de907ca7f270a41cb1e0b874672f05b9d989712debfef58eb26575d02);
- ELK日志收集系统的搭建请参考：[SpringBoot应用整合ELK实现日志收集](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046792cbfb2e1cb72d9aec12faeaa3f53b4af0e5608fba7f311ac1f4b4100ca1bad0d0084e59fb4dd0153c4179cbb2dd444f49bc26e72b336f24500eab2168f07e21cb70aa91dd6b8beb1c5f45c446e6cad)。

> Docker环境部署

- 使用虚拟机安装CentOS7.6请参考：[虚拟机安装及使用Linux，看这一篇就够了！](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046792cbfb2e1cb72d9aec12faeaa3f53b4af0e5608fba7f311ac1f4b4100ca1badbe3e73e6d1f7e7b5c83fcfaaef88c45694abc13fb29353eb7cee2af14d1a741b18f664062dddab7805e59013e386e79a)；
- Docker环境的安装请参考：[开发者必备Docker命令](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046792cbfb2e1cb72d9aec12faeaa3f53b4af0e5608fba7f311ac1f4b4100ca1badbe3e73e6d1f7e7b5c83fcfaaef88c45694075cb5d246af424c5265566850dd4c)；
- 本项目Docker镜像构建请参考：[使用Maven插件为SpringBoot应用构建Docker镜像](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046792cbfb2e1cb72d9aec12faeaa3f53b4af0e5608fba7f311ac1f4b4100ca1badbe3e73e6d1f7e7b5c83fcfaaef88c456e3f190929d039e9eae5f0788e5ffa7dbfc74d1c5637b5f55ec22e29f31a06258)；
- 本项目在Docker容器下的部署请参考：[mall在Linux环境下的部署（基于Docker容器）](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046792cbfb2e1cb72d9aec12faeaa3f53b4af0e5608fba7f311ac1f4b4100ca1badc63fa25bf4e4f98a0108b9d45f6d84d26330f60de907ca7f270a41cb1e0b87469d9238c837d09754e8f07355e47d2f2d)；
- 本项目使用Docker Compose请参考： [mall在Linux环境下的部署（基于Docker Compose）](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046792cbfb2e1cb72d9aec12faeaa3f53b4af0e5608fba7f311ac1f4b4100ca1badc63fa25bf4e4f98a0108b9d45f6d84d26330f60de907ca7f270a41cb1e0b874696185b278f07f8f004f9ea73b672480f880a2628cac312bdd45ea1a2d463d40f)。

## 参考资料

- [Spring实战（第4版）](http://u.720life.cn/g/6dda20f34a6f0cac55219074bdc5cc40f06f6970df711edfb5c1d348414fb94874c7d8266a5b6185efd63ee1a1b949e6)
- [Spring Boot实战](http://u.720life.cn/g/6dda20f34a6f0cac55219074bdc5cc40f06f6970df711edfb5c1d348414fb9486c180ea8c71c04d580e1d69d81d2096c)
- [Spring Cloud微服务实战](http://u.720life.cn/g/6dda20f34a6f0cac55219074bdc5cc40f06f6970df711edfb5c1d348414fb948464364d321cb1a480a334643657b2050)
- [Spring Cloud与Docker微服务架构实战](http://u.720life.cn/g/6dda20f34a6f0cac55219074bdc5cc40f06f6970df711edfb5c1d348414fb948227c489e37cbab294b1b2b57fd19dcbe)
- [Spring Data实战](http://u.720life.cn/g/6dda20f34a6f0cac55219074bdc5cc40f06f6970df711edfb5c1d348414fb9482882e36b00652a8cfe2abc0643c001e1)
- [MyBatis从入门到精通](http://u.720life.cn/g/6dda20f34a6f0cac55219074bdc5cc40f06f6970df711edfb5c1d348414fb9481097fddbe4540bc1da07e49abedd3367)
- [深入浅出MySQL](http://u.720life.cn/g/6dda20f34a6f0cac55219074bdc5cc40f06f6970df711edfb5c1d348414fb94820190c2bf74554faf15c565e39d313d9)
- [循序渐进Linux（第2版）](http://u.720life.cn/g/6dda20f34a6f0cac55219074bdc5cc40f06f6970df711edfb5c1d348414fb94856daf4c2ba37ce612c3939305132d8e8)
- [Elasticsearch 权威指南](http://u.720life.cn/g/de3742c0ac7bbef6b8feb3a0318f0771bbb0e604f9f4f790157c841c30dca5889a80aa9bbfc4d47bcc1956d6cbda8bacdb7c4813066e6a5c88037e13a42e5ba47803bb87ff505b7a264e47b86da87981)
- [Elasticsearch 技术解析与实战](http://u.720life.cn/g/6dda20f34a6f0cac55219074bdc5cc40f06f6970df711edfb5c1d348414fb94809d10fa03d673745e9e7a9e54d7c3d6f)
- [MongoDB实战(第二版)](http://u.720life.cn/g/6dda20f34a6f0cac55219074bdc5cc40f06f6970df711edfb5c1d348414fb948ad6954bcaee79a1503314ae7b738637b)
- [Kubernetes权威指南](http://u.720life.cn/g/6dda20f34a6f0cac55219074bdc5cc40f06f6970df711edfb5c1d348414fb9481c9613b9a03b5eab64c1404e19eee7cc)
- [Pro Git](http://u.720life.cn/g/0699e533b96232c5e210af6ab5668134f26d4ce8eb73c737efb58c5e94ea6f74)

## 公众号

mall项目全套学习教程连载中，**关注公众号**第一时间获取。

![公众号图片](http://macro-oss.oss-cn-shenzhen.aliyuncs.com/mall/banner/qrcode_for_macrozheng_258.jpg)

## 许可证

[Apache License 2.0](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046792cbfb2e1cb72d9aec12faeaa3f53b4fab9353890a58877a29d4ce044fe2f9559f8e3233d6357ed0b056838163ab9e8)

Copyright (c) 2018-2019 macrozheng



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ee049397826262d09da318f6111d8180bee2bae5d892053e80c18dc863c030780316cdb1f3220b7e18351642e5853ec4b)