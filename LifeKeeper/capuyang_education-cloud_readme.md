  
    
   
    
    
    
    
  分布式在线教育  
 一个各行业都适用的分布式在线教育系统。该系统基于Spring Cloud Alibaba微服务化开发平台， 核心技术采用Spring Boot 2.2.0以及Spring Cloud (Hoxton.RELEASE) 相关核心组件，采用Nacos注册和配置中心，前端采用vue-element-admin组件 


### 官方QQ群（加群免费获取sql脚本）

  1093045884 可加 
> QQ群：1093045884


### 相关工程
##### 在线教育系统(education-cloud)：[码云地址](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e623289fbb5915aa93e97000d2d1eccbc5c55d625367d3424ab2e4419192941b0) 
##### 前端门户工程(education-cloud-web-ui)：[码云地址](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e623289fbb5915aa93e97000d2d1eccbc77e6aed4b3d4e63b75984c290f14d8976beac153ee67f65d817f91d316e1ca3a)
##### 后台管理工程(education-cloud-web-admin)：[码云地址](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e623289fbb5915aa93e97000d2d1eccbc299bd451d4bf46d16be2e96845ef546b4c16cd896d6c59a92354d9d00c608126)
> 在线教育系统采用前后端分离架构，前端为独立工程。  
- education-cloud是后台工程，核心框架：Spring Cloud Alibaba 
- education-cloud-web是前端门户工程，核心框架：Vuejs + Nuxt.js  
- education-cloud-admin是后台管理工程，核心框架：vue-element-admin


## 技术选型

- 服务注册与发现：`Nacos`
- 熔断器：`Hystrix` + `Turbine`
- 客户端负载均衡：`Ribbon`
- 内部服务调用：`Feign`
- 网关：`Spring Cloud Zuul`
- 认证鉴权： `JWT`
- 程序监控：`Spring Boot Admin` / `Spring Boot Actuator`
- 分布式配置中心：`Nacos`
- 数据库：`MySQL 5.7`
- 部署：`Docker` + `docker-compose`
- 构建工具：`Maven`
- 后台 API 文档：`swagger-bootstrap-ui`
- 文件系统：`阿里云`
- 缓存：`Redis`
- 前端：`vue`

### 项目介绍（如果对你有用，请给个star！）
education-cloud 致力于打造一个各行业都适用的分布式在线教育系统。系统采用前后端分离模式，前台采用vue.js为核心框架，后台采用Spring Cloud Hoxton.RELEASE、Spring Cloud JWT& Spring Cloud Alibaba为核心框架。系统目前主要功能有课程点播功能，支持多家视频云的接入，课程附件管理功能，支持多家存储云的接入，讲师管理功能，支持讲师入驻功能，可以帮助个人或者企业快速搭建一个轻量级的在线教育平台。
该系统具有如下特点：

* 前后端分离架构，客户端和服务端纯Token交互；

* 微服务防护，客户端请求资源只能通过微服务网关获取；

* 集成Prometheus，SpringBootAdmin，多维度监控微服务；

* 集成Spring Cloud Alibaba Nacos服务治理和集中配置管理；

* 集成Zuul网关熔断机制

* 集成Swagger接口文档 为swagger-bootstrap-ui，界面更友好，通过网关统一聚合后端微服务API文档

* 微服务Docker化，使用Docker Compose一键部署；

* 集成Skywalking APM；

* 集成ELK，集中管理日志，便于问题分析；

* 支持Kubernetes集群部署（开发中）；

* 提供详细的使用文档和搭建教程 （不断完善中）；

### 前台主要功能介绍
* 首页功能，导航模块（自定义导航设置），广告模块（自定的轮播设置），课程模块（自定义课程设置）
* 列表功能，分类模块（自定义分类设置），搜索模块（自定义搜索设置）
* 课程详情页功能，课程介绍、目录的展示和购买、播放功能等
* 个人中心，具有个人信息设置、密码修改、订单管理、学习记录等功能
* 讲师中心，讲师信息管理、课程管理（课程的添加、修改）、收益管理等功能

### 后台主要功能介绍
* 权限管理功能，多角色多用户自定义配置
* 系统配置功能，自定义进行站点配置及第三方参数配置
* 讲师管理功能，讲师申请入驻，后台具有审核功能
* 课程管理功能，讲师管理自有课程，后台具有审核功能
* 用户登录功能，同一时间只允许同一个账号在同一个地方登录，防止账号共享
* 广告管理功能，后台自定义广告设置，增加营销效果
* 支付功能模块，待集成微信和支付宝支付

### 项目组织结构

```
education-cloud
├── education-cloud-gateway -- 基于Zuul网关模块
├── education-cloud-job -- 任务模块
├── education-cloud-server-admin -- 监控模块
├── education-cloud-course -- 课程模块
|        |─education-cloud-course-feign  课程模块API接口
|        │─education-cloud-course-service  课程服务模块
├── education-cloud-system -- 系统管理模块
|        |─education-cloud-system-feign  系统管理模块API接口
|        |─education-cloud-system-service  系统管理服务模块
├── education-cloud-user --用户模块
|        |─education-cloud-user-feign  用户模块API接口
|        |─education-cloud-user-service  用户服务模块
├── education-cloud-util -- 公共模块
├── doc -- 配置及说明文档
         |─config  中间件配置文件以及系统配置文件
         |─deploy  工具环境安装指南
         |─docker  docker环境部署文件
         |─script  项目一键部署脚本，主要启动docker-compose服务
         |─sql     项目数据库文件
```

### 部署方面, 目前支持传统手动部署和docker部署：
- IDEA 启动
- jar部署
- docker（基于rancher的容器管理平台）部署
- k8s部署 （正后续支持）


### 演示地址
##### 前端演示地址：[领课教育](http://u.720life.cn/g/8c571719c33567a16cd84331785533d1fd5c539dc74a1a032cf74bbb60dda76a) | 后台演示地址：[运营后台](http://u.720life.cn/g/a710d429e037acae8ee051c30ea4b417b50642df58e2c7b49588c30c39d185e0)

## 项目运行（部署文档完善中....）

> ### Windows环境部署(IDEA 启动)

  ####后端启动

-  运行项目之前，请确认以环境下载并安装，安装方式可以参考doc/deploy目录安装指南，`MySql5.7+`、`Redis4+`、`elastisearch6.8.3`、`Nocos1.2`（使用搜索elastisearch需安装中文分词器IKAnalyzer）;
-  创建`education-course`、`education-system`、`education-user`、`nacos`四个数据库，数据库脚本文件放置在项目doc/sql（包括nacos sql）文件夹下，直接导入即可;
-  安装IDEA并导入项目源码,导入之前，IDEA需要安装lombok插件。源码仓库：git clone https://gitee.com/wewwww/education-cloud.git;
-  导入之后，检查nacos中各个微服务相关配置文件配置的mysql，redis,elastisearch（注意配置文件es的集群名称）连接配置是否正确;
-  项目启动有先后顺序，大家要按照以下顺序启动。
   - 启动课程服务`education-cloud-course` 直接运行com.education.cloud.CourseServiceApplication的main函数即可；
   - 启动系统管理服务`education-cloud-system` 直接运行com.education.cloud.SystemServiceApplication的main函数即可；
   - 启动用户服务`education-cloud-user` 直接运行com.education.cloud.UserServiceApplication的main函数即可；
   - 启动网关服务`education-cloud-gateway` 直接运行com.education.cloud.GatewayApiApplication的main函数即可；
   - 启动任务服务`education-cloud-job` 直接运行com.education.cloud.CrontabPlanApplication的main函数即可；
   - 启动监控服务`education-cloud-server-admin` 直接运行com.education.cloud.server.admin.ServerAdminApplication的main函数即可；
   
-  查看微服务状态 http://localhost:5721/ 账号密码 admin/123456
-  测试接口文档访问地址 http://localhost:5840/api/doc.html

  #### 前端启动

 ##### 运营管理系统运行

- 前端运行需要用到node，Node版本:9.0.0以上
- 使用 npm install -g cnpm --registry=https://registry.npm.taobao.org
- 安装依赖：cnpm install
- 本地开发 启动项目：npm run dev
- 打包正式环境：npm run build
- 访问地址：http://localhost:5800/
 

 ##### 前端门户系统导入运行

- 前端运行需要用到Node，Node版本: 9.0.0以上
- npm install -g cnpm --registry=https://registry.npm.taobao.org
- cnpm install
- npm run dev
- 前端访问地址：http://127.0.0.1:3000/
 

> ### Docker环境部署

 #### 后端启动
 
- 使用虚拟机安装CentOS7.5+或者使用云服务器，安装方式自行百度.
- Docker、docker-compose、Harbor环境的安装请参考 doc/deploy目录
- 请在IDEA中，在项目根目录下即`education-cloud`执行 mvn install ,会自动把各个服务打包成镜像并上传到Harbor仓库(打包机也需要安装Docker环境，可参考doc/deploy下指南)
- 前端项目打包参考下方`前端启动`，前端项目打完包，需要手动把镜像推送到镜像仓库，具体可参考个前端项目readme说明
- 本项目使用docker-compose自动化部署
 - 部署文件
   - 查看doc/docker/各个docker-compose文件
   - 把 docker文件夹下的所有docker-compose文件上传到Linux服务器的一个目录下，最好新建一个文件夹把各个docker-compose文件和下方的脚本文件放置一个目录
   
 - 为了方便部署，采用shell脚本一键部署的方式，具体查看doc/script/start.sh （支持传入参数 pull、run、pullrun、stop、restart、removeAll）脚本文件。
   - 脚本文件中的镜像名称前缀变量`BASE_IMAGE_NAME`，请修改为你在harbor中的镜像前缀
   - 执行脚本前请赋予执行权限：`./chmod u+x start.sh`
   - 前后端项目都打包完成上传到Harbor仓库，执行 `./start.sh pullrun` 表示拉去镜像并创建容器

  #### 前端启动（使用docker，需要手动构建镜像并推送到远程仓库）

 ##### 运营管理系统运行
 
- git https://gitee.com/wewwww/ducation-cloud-web-admin.git
- 进入到`education-cloud-admin`目录，例如执行 `docker build -t 127.0.0.1/edu-cloud/education-admin-web:latest .` 即可构建镜像，然后把镜像推送到远程仓库Harbor即可
- 前端项目需要手动推送到远程仓库,比如Harbor仓库 命令： `docker push 127.0.0.1/edu-cloud/education-admin-web:latest`
- 前后端服务都正常启动 访问地址：http://127.0.0.1:5800/
- 账号/密码 13800000000/123456
 

 ##### 前端门户系统导入运行

- git https://gitee.com/wewwww/education-cloud-web-ui.git
- 进入到`education-cloud-web`目录，例如执行 `docker build -t 127.0.0.1/edu-cloud/education-cloud-ui-web:latest .` 即可构建镜像，然后把镜像推送到远程仓库Harbor即可
- 前端项目需要手动推送到远程仓库,比如Harbor仓库 命令： `docker push 1127.0.0.1/edu-cloud/education-admin-web:latest`
- 前后端服务都正常启动 访问地址：http://127.0.0.1:3000/
- 账号/密码 13800138001/123456

 ##### ELK日志搭建
 ```

  下载镜像 docker pull sebp/elk:700
  启动镜像 , 指定es的内存
  docker run -p 5601:5601 -p 9200:9200 -p 5044:5044 -p 4560:4560 -e ES_MIN_MEM=128m  -e ES_MAX_MEM=1024m -it --name elk sebp/elk:700
  需要修改 logstash 配置，新建命令窗口，进行下面的docker命令
  通过exec命令进入容器
  docker exec -it elk /bin/bash
  进入容器后，修改 /etc/logstash/conf.d/02-beats-input.conf
    input {
        tcp {
            port => 4560
            codec => json_lines
    
        }
    
    }
    output{
        elasticsearch {
        hosts => ["localhost:9200"]
    
        }
    
    }

  保存后，退出容器。然后重启容器，让我们的配置生效。
  docker restart elk
  访问http://localhost:5601/

 ```



 ### 部署视频 敬请期待......
 
 >  如果对您对此项目有兴趣，可以点 "Star" 支持一下 谢谢！ ^_^
 
 >  或者您可以 "follow" 一下
 >

### 鸣谢
该项目参考了领课教育系统，感谢领课网络提供的这么优秀的项目
 








 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ee9ee17395097ca823eba265a99282c6ef89f2f066f09632b6f6e3667f8522b16cc97ec627e5024e0f982ddd5b3883112)