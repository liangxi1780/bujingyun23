# mall

## 说明

> 后台管理项目fork自  https://github.com/macrozheng/mall
> 基于SpringBoot+MyBatis的电商系统，包括前台商城系统及后台管理系统。

> 如果该项目对您有帮助，您可以点右上角 "Star" 支持一下 谢谢！

> 或者您可以 "follow" 一下，该项目将持续更新，不断完善功能。

> 项目交流QQ群： 168918237   117187576 (已满 )

> 如有问题或者好的建议可以在 Issues 中提。

## 前言

`mall`项目致力于打造一个完整的电商系统，采用现阶段流行技术实现。

## 项目介绍

`mall`项目是一套电商系统，包括前台商城系统及后台管理系统,h5,小程序，基于SpringBoot+MyBatis实现。
前台商城系统包含首页门户、商品推荐、商品搜索、商品展示、购物车、订单流程、会员中心、客户服务、帮助中心等模块。
后台管理系统包含商品管理、订单管理、会员管理、促销管理、运营管理、内容管理、统计报表、财务管理、权限管理、设置等模块。

### 组织结构

``` lua
mall
├── mall-mbg -- MyBatisGenerator生成的数据库操作代码
├── mall-admin -- 后台商城管理系统接口
├── mall-search -- 基于Elasticsearch的商品搜索系统
├── mall-portal -- 前台商城系统接口
├── 前端项目`mall-admin-web`  地址 请加群下载   168918237
├── h5前端项目`vue-js-master`地址 请加群下载  
├── pc前端项目`Mall-Vue-master`地址 请加群下载  
├── 小前端项目`wechatapp`地址 请加群下载
```

### 项目演示

> 后台管理系统

前端项目`mall-admin-web`地址：https://github.com/macrozheng/mall-admin-web 

项目演示地址： [http://39.98.190.128/index.html](http://u.720life.cn/g/602cbbd93ce6eec9ce45e915b1e17775e2e2e89d6d98a1032066f789ffc07370)  
  
- [后台管理系统功能演示.gif](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e4605a3c88313215a5577e31f8f5c2e3114f335cee59d417b29b09a4b540ed8f58e7925559461157fc6a8bacb5e949dddae8c5e226130f91f472ca770d51e6121)
- [小程序功能演示.gif](https://gitee.com/zscat/mall/tree/master/document/gif/小程序演示.gif)



> 前台商城系统

- 前端项目`mall-admin-web`  地址 请加群下载   168918237
- h5前端项目`vue-js-master`地址 请加群下载  
- pc前端项目`Mall-Vue-master`地址 请加群下载  
- 小前端项目`wechatapp`地址 请加群下载

https://powerdos.github.io/Mall-Vue/#/


## 目前h5项目已实现功能
1. 首页数据的展示
2. 分类页数据的展示
3. 购物车
4. 我的
5. 注册
6. 登录
7. 商品详情页
8. 商品搜索
##h5项目效果图


![](https://images.gitee.com/uploads/images/2019/0217/112713_5f032a4c_134431.png)

![](https://images.gitee.com/uploads/images/2019/0217/112713_f4cb24ab_134431.png)

![](https://images.gitee.com/uploads/images/2019/0217/112713_a17c828d_134431.png)

![](https://images.gitee.com/uploads/images/2019/0217/112713_a7afcc52_134431.png)

![](https://images.gitee.com/uploads/images/2019/0217/112713_2d82d3c8_134431.png)

![](https://images.gitee.com/uploads/images/2019/0217/112714_62baf63a_134431.png)

![](https://images.gitee.com/uploads/images/2019/0217/112715_c571472d_134431.png)


## 目前小程序项目已实现功能
1. 首页数据的展示
2. 分类页数据的展示
3. 购物车
4. 我的
5. 注册
6. 登录
7. 商品详情页
8. 商品搜索
9.下单
10.用户详情


## 目前pc项目已实现功能
1. 首页数据的展示
2. 分类页数据的展示
3. 购物车
4. 我的
5. 注册
6. 登录
7. 商品详情页
8. 商品搜索
9.下单
10.用户详情

### 技术选型

#### 后端技术

技术 | 说明 | 官网
----|----|----
Spring Boot | 容器+MVC框架 | [https://spring.io/projects/spring-boot](http://u.720life.cn/g/c6d1b26d763f49c99d62f7dd7e1f263d74791681f9785d83f6cd6c957366ad1debb29bb8c32cd47aff960e71f7893090)
Spring Security | 认证和授权框架 | [https://spring.io/projects/spring-security](http://u.720life.cn/g/c6d1b26d763f49c99d62f7dd7e1f263d74791681f9785d83f6cd6c957366ad1d51f22cbfad230da539bef50203caf238)
MyBatis | ORM框架  | [http://www.mybatis.org/mybatis-3/zh/index.html](http://u.720life.cn/g/5d88e5a59ccc688f2e74c4a956a26a215e4d93221eb26b660bea25686b89be63142caf406b6e1c14d3ab51db921e10ca)
MyBatisGenerator | 数据层代码生成 | [http://www.mybatis.org/generator/index.html](http://u.720life.cn/g/5d88e5a59ccc688f2e74c4a956a26a21a07057a36d6ca5ea426a94333449b8ee4a9090aa94e48705a0a12124d68034da)
PageHelper | MyBatis物理分页插件 | [http://git.oschina.net/free/Mybatis_PageHelper](http://u.720life.cn/g/5c954f4cd4204fb6c09a7e58aa70844d0c5e449aa2c2e2afac3f4646cf34dfd65ceb51a277771277d2a7f535bcbaead3)
Swagger-UI | 文档生产工具 | [https://github.com/swagger-api/swagger-ui](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046ee873d8b7265bda98dbeb1b913855dc8cc8fe4f2d8a7cf6393aeda706a915000)
Hibernator-Validator | 验证框架 | [http://hibernate.org/validator/](http://u.720life.cn/g/09d74cfb02196ca3ed0ec52b685384e1fd96db6373856c92099520b41f86fef5)
Elasticsearch | 搜索引擎 | [https://github.com/elastic/elasticsearch](http://u.720life.cn/g/54145d0471d91890860f7f8463c030466e836c5dd85610d86e6f01486f462e2c0d9e4b426066af1ff2b4626bce8b1132)
RabbitMq | 消息队列 | [https://www.rabbitmq.com/](http://u.720life.cn/g/0fa33e240a4f68a032ffc0865d7dcd1fb673b17d4773e9f52139fbece79cad2e)
Redis | 分布式缓存 | [https://redis.io/](http://u.720life.cn/g/70336383bbe1092dca9fcec94f2fd10823c1cea91ac1108405bfbd56f5b819fc)
MongoDb | NoSql数据库 | [https://www.mongodb.com/](http://u.720life.cn/g/5b6081b126093fbb42e8289314c4c63edef09cba29820afcfda6f238d141f89a)
Docker | 应用容器引擎 | [https://www.docker.com/](http://u.720life.cn/g/d13d2b0ef4a5c92b4f4a6e9ed4270e65b90c4c1e1b506e1a501feef81ad769e9)
Druid | 数据库连接池 | [https://github.com/alibaba/druid](http://u.720life.cn/g/54145d0471d91890860f7f8463c030464e9ab1ba10d3588ded212abb6198c62a)
OSS | 对象存储 | [https://github.com/aliyun/aliyun-oss-java-sdk](http://u.720life.cn/g/54145d0471d91890860f7f8463c030463acc10ac40ebe392ae83d014e0e2b286fe9c84bf686fc8dede39c92bd0288ee5)
JWT | JWT登录支持 | [https://github.com/jwtk/jjwt](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304637710c50c45b7e4b55624adcef685c65)
LogStash | 日志收集 | [https://github.com/logstash/logstash-logback-encoder](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304669aa5c06d8130c325d1bfa13fdfd08726e2d71470b343aedcffc515849eb90f4b7fea92e7eced4cc00b62438ea6c9e83)
Lombok | 简化对象封装工具 | [https://github.com/rzwitserloot/lombok](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304667e1b2f7ca2a7abf102cdf9e5fa5070a803dc1dd5f1c376fd8d7fb727fc2defd)

#### 前端技术

技术 | 说明 | 官网
----|----|----
Vue | 前端框架 | [https://vuejs.org/](http://u.720life.cn/g/1c3db3fec6433a3fb191bb48af91f3bb055304712f0641658c814ca15fec0089)
Vue-router | 路由框架 | [https://router.vuejs.org/](http://u.720life.cn/g/7bedfe02707a57b283aa65bf169b40685a2bcc51af184101de4b71f45db846fa)
Vuex | 全局状态管理框架 | [https://vuex.vuejs.org/](http://u.720life.cn/g/acea3f53396a46112876052cae0a3648a88a7ed218d2be0ffa10fc982c11ad04)
Element | 前端UI框架 | [https://element.eleme.io/](http://u.720life.cn/g/5fa51553afae358345e9f20b5a6e741569ec367dcef795a9cc086ceba9a9242d)
Axios | 前端HTTP框架 | [https://github.com/axios/axios](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304638015ac6a54b1cadf0934b8a0d5637d0)
v-charts | 基于Echarts的图表框架 | [https://v-charts.js.org/](http://u.720life.cn/g/04bb650c6b9547d2ac7f61bed3e715031e418e4efd3cee1a70120fe3eff14e14)
Js-cookie | cookie管理工具 | [https://github.com/js-cookie/js-cookie](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304601a18a0a98543c227ccab0f66e611f0076dc75769652863fa8e48c713794768c)
nprogress | 进度条控件 | [https://github.com/rstacruz/nprogress](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304621051bfe8a14df709920d1b59773b4a1b34b830a15281032ae36824abb143cae)

#### 架构图

##### 系统架构图

![系统架构图](document/resource/mall_system_arch.png)

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

工具 | 说明 | 官网
----|----|----
IDEA | 开发IDE | https://www.jetbrains.com/idea/download
RedisDesktop | redis客户端连接工具 | https://redisdesktop.com/download
Robomongo | mongo客户端连接工具 | https://robomongo.org/download
SwitchHosts| 本地host管理 | https://oldj.github.io/SwitchHosts/
X-shell | Linux远程连接工具 | http://www.netsarang.com/download/software.html
Navicat | 数据库连接工具 | http://www.formysql.com/xiazai.html
PowerDesigner | 数据库设计工具 | http://powerdesigner.de/
Axure | 原型设计工具 | https://www.axure.com/
MindMaster | 思维导图设计工具 | http://www.edrawsoft.cn/mindmaster
ScreenToGif | gif录制工具 | https://www.screentogif.com/
ProcessOn | 流程图绘制工具 | https://www.processon.com/
PicPick | 屏幕取色工具 | https://picpick.app/zh/

### 开发环境

工具 | 版本号 | 下载
----|----|----
JDK | 1.8 | https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html
Mysql | 5.7 | https://www.mysql.com/
Redis | 3.2 | https://redis.io/download
Elasticsearch | 2.4.6 | https://www.elastic.co/downloads
MongoDb | 3.2 | https://www.mongodb.com/download-center
RabbitMq | 5.25 | http://www.rabbitmq.com/download.html
nginx | 1.10 | http://nginx.org/en/download.html

### 搭建步骤

> 本地环境搭建

- 本地安装开发环境中的所有工具并启动，具体参考[deploy-windows.md](document/reference/deploy-windows.md);
- 克隆源代码到本地，使用IDEA或Eclipse打开，并完成编译;
- 在mysql中新建mall数据库，导入document/sql下的mall.sql文件；
- 启动mall-admin项目：直接运行com.macro.mall.MallAdminApplication的main方法即可，
  接口文档地址：http://localhost:8080/swagger-ui.html;
- 启动mall-search项目：直接运行com.macro.mall.search.MallSearchApplication的main方法即可，
  接口文档地址：http://localhost:8081/swagger-ui.html;
- 启动mall-portal项目：直接运行com.macro.mall.portal.MallPortalApplication的main方法即可，
  接口文档地址：http://localhost:8085/swagger-ui.html;
- 克隆`mall-admin-web`项目，并导入到IDEA中并完成编译[传送门](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046792cbfb2e1cb72d9aec12faeaa3f53b42e4d30c010195bd4dbc551cbb6dc82da);
- 运行命令：npm run dev,访问地址：[http://localhost:8090](http://u.720life.cn/g/e71094f6077cb9592da5b56893f0ad14118c17b6013fd67cd8fa329d270db4b6) 即可打开后台管理系统页面;

- 克隆`Mall-Vue-master`项目，并导入到IDEA中并完成编译[传送门]();
- 运行命令：npm run dev,访问地址： 即可打开pc商城页面;
- 克隆`vue-jd-master`项目，并导入到IDEA中并完成编译[传送门]();
- 运行命令：npm run dev,访问地址： 即可打开h5商城页面;
- ELK日志收集系统的搭建：参考[elk.md](document/elk/elk.md)。

> docker环境部署

- 在VirtualBox或其他环境中安装CenterOs7.2;
- 配置本地host:参考[host.txt](document/docker/host.txt),将ip地址改为虚拟机的ip地址;
- 使用maven构建`mall-admin`、`mall-search`、`mall-portal`的docker镜像，参考[docker.md](document/reference/docker.md)中的使用maven构建Docker镜像;
- 部署步骤参考[docker-deploy.md](document/docker/docker-deploy.md)进行部署。

## 参考资料

- [Spring实战（第4版）](http://u.720life.cn/g/6dda20f34a6f0cac55219074bdc5cc40f06f6970df711edfb5c1d348414fb94874c7d8266a5b6185efd63ee1a1b949e6)
- [Spring Boot实战](http://u.720life.cn/g/6dda20f34a6f0cac55219074bdc5cc40f06f6970df711edfb5c1d348414fb9486c180ea8c71c04d580e1d69d81d2096c)
- [Spring Cloud微服务实战](http://u.720life.cn/g/6dda20f34a6f0cac55219074bdc5cc40f06f6970df711edfb5c1d348414fb948464364d321cb1a480a334643657b2050)
- [Spring Cloud与Docker微服务架构实战](http://u.720life.cn/g/6dda20f34a6f0cac55219074bdc5cc40f06f6970df711edfb5c1d348414fb948227c489e37cbab294b1b2b57fd19dcbe)
- [Spring Data实战](http://u.720life.cn/g/6dda20f34a6f0cac55219074bdc5cc40f06f6970df711edfb5c1d348414fb9482882e36b00652a8cfe2abc0643c001e1)
- [MyBatis从入门到精通](http://u.720life.cn/g/6dda20f34a6f0cac55219074bdc5cc40f06f6970df711edfb5c1d348414fb9481097fddbe4540bc1da07e49abedd3367)
- [深入浅出MySQL](http://u.720life.cn/g/6dda20f34a6f0cac55219074bdc5cc40f06f6970df711edfb5c1d348414fb94820190c2bf74554faf15c565e39d313d9)
- [循序渐进Linux（第2版）](http://u.720life.cn/g/6dda20f34a6f0cac55219074bdc5cc40f06f6970df711edfb5c1d348414fb94856daf4c2ba37ce612c3939305132d8e8)
- [Elasticsearch 技术解析与实战](http://u.720life.cn/g/6dda20f34a6f0cac55219074bdc5cc40f06f6970df711edfb5c1d348414fb94809d10fa03d673745e9e7a9e54d7c3d6f)
- [MongoDB实战(第二版)](http://u.720life.cn/g/6dda20f34a6f0cac55219074bdc5cc40f06f6970df711edfb5c1d348414fb948ad6954bcaee79a1503314ae7b738637b)
- [Kubernetes权威指南](http://u.720life.cn/g/6dda20f34a6f0cac55219074bdc5cc40f06f6970df711edfb5c1d348414fb9481c9613b9a03b5eab64c1404e19eee7cc)

## 许可证

后台管理项目来自  https://github.com/macrozheng/mall
Copyright (c) 2018-2019 zscat


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e437a3d1417a583484291afe8bb72beb55e315df924c3a1ad8c067789993f52738f20c9ee22a5199165c55b8329007d32)