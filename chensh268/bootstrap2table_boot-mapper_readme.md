# boot-mapper

#### 项目介绍
boot-mapper基于SpringBoot2.0.2版本，使用mybatis集成redis二级缓存。 

#### 极速入门
[入门配置](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ea90b048cf610179f4e6a533e1de6cadc629ce081fd2b0771f14998d2c3dad84d85fca04f056a1363d98167b86a8ecd2f)   &nbsp;[分布式事务](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ea90b048cf610179f4e6a533e1de6cadc20fd14fef4eff1b3bb8eed05c99653047619bbc6c91e3802006c582035fdf97faa3fe0cc2bd0d285c4c391b6f6a7af20)  &nbsp;[SpringCloud](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ea90b048cf610179f4e6a533e1de6cadcbbb010c20235b93ce3371bea67c81098)   &nbsp;[Dubbo](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ea90b048cf610179f4e6a533e1de6cadcdf1e6a526873fab1a548381b4a22f731)


#### 技术选型
    ● 系统核心框架：SpringBoot
    ● 定时任务调度：ElasticJob+Zookeeper
    ● 数据持久框架：MyBatis
    ● 数据库连接池：Alibaba Druid
    ● 系统监控插件：JavaMelody+Druid
    ● 系统缓存框架：Redis-cluster
    ● 系统前端框架：Freemaker+AdminLte
    ● 搜索引擎框架：Solr/SolrCloud
    ● 分布式线程锁：Redisson
    ● 分布式限流器：Redisson
    ● 系统消息队列：ActiveMq 
 
#### **项目特点**   

> * 配套Mybatis二级缓存，默认缓存5分钟（支持手动配置），可以提高系统性能。 
> * 配套[代码生成工具](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ea90b048cf610179f4e6a533e1de6cadc49b1a630892dec46b6596b2eb277a888ca5908af38ffce7b60ef134ebbb69f45):快速生成前后端代码，极大的提高开发效率。 
> * 引入[HibernateValidator](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ea90b048cf610179f4e6a533e1de6cadccdcc0ae61df288eab8b72d45af0ecd6e1b7e05946027e4eb0f49a44601a1af1a1fc7b323147e61dd8296ceabbdfdf144d0dc8fc60fc0ce35f24b572910dc6cf92393d93bacce5465d30d490e8d1ec5cd129629610bd78fe9a15d3055bbfefa1c)校验框架，轻松实现后端校验。 
> * 引入druid,javaMelody监控系统各项指标，分析系统瓶颈。 
> * 前端采用freemarker模板化引擎,页面采用bootstrap-table灵活强大的表格插件。 
> * 前端使用layui弹出层框架，极大的简化了弹出层的开发过程。
> * 前端采用JqueryValidate插件,快捷方便进行数据验证。 
> * 后端配置swagger在线文档，极大的降低前后端项目成员的沟通成本，快速同步文档。  
> * 配置druid,fastjson,cors,xss,redis-cluster等组件服务。 
> * 配置全局异常处理，通用日志打印,pagehelper分页。 
> * 配置redisson集群模式,使用分布式锁，保证并发的数据一致性。 
> * 配置全局errorPage和welcomeFile完善全局异常处理，优化异常处理代码。 
> * 配置devtools热部署，针对page目录下的css,js,html页面资源修改之后，项目不需要重新启动。 
> * 配置elastic-job定时器，强悍的分布式定时任务配置。 
> * 配置https安全协议，提高系统安全性,配置log4j日志，系统出现异常自动发送邮件。 

#### **项目结构**
```
boot-mapper
│ 
├─doc  项目SQL语句
│ 
├─common 公共配置
│ 
├─framework 框架配置
│ 
├─modules 功能模块
│  ├─controller 控制器层
│  ├─service 业务逻辑层
│  ├─dao    数据持久层
│  │  ├─mapper  SQL文件
│  │  └─persist 持久层接口
│  └─model 数据库实体类
│ 
├─StartUpApplication 项目启动类
│  
├──resources
│  ├─page 页面资源
│  │  ├─static 静态资源
│  │  │  ├─css  css样式
│  │  │  ├─js   js文件 
│  │  │  ├─images   图片文件 
│  │  │  ├─adminLTE 模板组件  
│  │  │  └─plugins  前端插件
│  │  │
│  │  └─view  前端页面
│  │     ├─error 系统错误页
│  │     ├─inc   公共资源页面
│  │     └─其他   系统功能页面
│  │
│  ├─application.properties 配置文件
│  ├─banner.txt  自定义启动图标
│  ├─mybatis_config.xml mybatis配置项
│  └─secure.jks  ssl安全证书
```
#### **软件环境** 
- JDK1.8
- MySQL5.5+
- Maven3.0+
 
#### **环境配置:** 
- 1.项目依赖redis-cluster集群,zookeeper,activeMq,solr工具,目前工具运行环境(win7 x64)。 
- 2.doc目录里面有初始化sql，运行项目前，请先创建mysql(编码UTF-8)。 
- 3.工具地址:https://pan.baidu.com/s/1Bm7udGJc40xEENFgnJjsIw
- 5.配置文档：https://gitee.com/bootstrap2table/boot_master/wikis/welcome
	 
#### **启动说明:**
- 1.创建mysql数据库isec实例,运行doc目录里面的sql文件。 
- 2.启动redis集群(127.0.0.1:6379~6384，密码:qdone)。 
- 3.启动activeMq(默认单机版)。 
- 4.启动solr(默认单机版)。 
- 5.启动zookeeper(默认单机版本2181)。 
- 6.运行StartUpApplication启动项目，浏览器访问https://localhost:9090/solr/init 
	
#### **友情链接：**
- GitHub：https://github.com/apple987/boot_walk  
- mycat版本: https://gitee.com/bootstrap2table/boot_master/tree/feature/mycat 
- sharding-jdbc版本: https://gitee.com/bootstrap2table/boot-sharding 
- jtaDruid版本: https://gitee.com/bootstrap2table/boot_master/tree/feature/jta/druid 


#### **问题反馈：**
- 意见反馈：https://gitee.com/bootstrap2table/boot-mapper/issues
- 作者姓名：付为地 
- 作者QQ: 1335157415 
- 作者邮箱: m15171479289@163.com 

		
        


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ea90b048cf610179f4e6a533e1de6cadc5dad76f532f998b26b46be39fb2955db9612b4dfa51e18e7711e7e3442c761625363d7fa313dce7effee5698caa2c07e)