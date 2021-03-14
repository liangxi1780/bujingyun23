## 平台简介

* 采用前后端分离的模式，微服务版本前端(基于 [RuoYi-Vue](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e4efbf9a2018792702bfb8d2f94b55c6d7a2c36c7bc4d3e3beccaae130c5d21a5)
* 后端采用Spring Boot、Spring Cloud & Alibaba。
* 注册中心、配置中心选型Nacos，权限认证使用OAuth2。
* 流量控制框架选型Sentinel。
* 感谢[ruoyi-cloud-design](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6eb684cb0962e3f2fc4f8e7d02cea8138e1ed27289bd0e270cce38525ea38af829)，[pig]https://gitee.com/log4j/pig
* 如需不分离应用，请移步 [RuoYi](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e4efbf9a2018792702bfb8d2f94b55c6d9e1d98050ff9fe2689f6766885d19856)，如需分离应用，请移步 [RuoYi-Vue](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e4efbf9a2018792702bfb8d2f94b55c6d7a2c36c7bc4d3e3beccaae130c5d21a5)
* 阿里云优惠券：[点我进入](http://u.720life.cn/g/cc176fdce68265104b8a4a80987ffe391b38d10272d6f7e6bbea5e66f680df661dba876d2f78944feec0003f6e9b6eb71b339b2f7b24a9cd5b6b07506292016ea5b666e59bb23dde9ee07238bfec4295)，腾讯云优惠券：[点我领取]https://cloud.tencent.com/redirect.php?redirect=1025&cps_key=198c8df2ed259157187173bc7f4f32fd&from=console


## 系统模块

~~~
com.ruoyi     
├── ruoyi-ui              // 前端框架 [80]
├── ruoyi-gateway         // 网关模块 [8080]
├── ruoyi-auth            // 认证中心 [9200]
├── ruoyi-api             // 接口模块
│       └── ruoyi-api-system                          // 系统接口
├── ruoyi-common          // 通用模块
│       └── ruoyi-common-core                         // 核心模块
│       └── ruoyi-common-datascope                    // 权限范围
│       └── ruoyi-common-log                          // 日志记录
│       └── ruoyi-common-redis                        // 缓存服务
│       └── ruoyi-common-security                     // 安全模块
│       └── ruoyi-common-swagger                      // 系统接口
├── ruoyi-modules         // 业务模块
│       └── ruoyi-system                              // 系统模块 [9201]
│       └── ruoyi-gen                                 // 代码生成 [9202]
│       └── ruoyi-job                                 // 定时任务 [9203]
├── ruoyi-visual          // 图形化管理模块
│       └── ruoyi-visual-monitor                      // 监控中心 [9100]
├──pom.xml                // 公共依赖
~~~

## 架构图

 

## 内置功能

1.  用户管理：用户是系统操作者，该功能主要完成系统用户配置。
2.  部门管理：配置系统组织机构（公司、部门、小组），树结构展现支持数据权限。
3.  岗位管理：配置系统用户所属担任职务。
4.  菜单管理：配置系统菜单，操作权限，按钮权限标识等。
5.  角色管理：角色菜单权限分配、设置角色按机构进行数据范围权限划分。
6.  字典管理：对系统中经常使用的一些较为固定的数据进行维护。
7.  参数管理：对系统动态配置常用参数。
8.  通知公告：系统通知公告信息发布维护。
9.  操作日志：系统正常操作日志记录和查询；系统异常信息日志记录和查询。
10. 登录日志：系统登录日志记录查询包含登录异常。
11. 在线用户：当前系统中活跃用户状态监控。
12. 定时任务：在线（添加、修改、删除)任务调度包含执行结果日志。
13. 代码生成：前后端代码的生成（java、html、xml、sql）支持CRUD下载 。
14. 系统接口：根据业务代码自动生成相关的api接口文档。
15. 服务监控：监视当前系统CPU、内存、磁盘、堆栈等相关信息。
16. 在线构建器：拖动表单元素生成相应的HTML代码。
17. 连接池监视：监视当前系统数据库连接池状态，可进行分析SQL找出系统性能瓶颈。

## 在线体验

- admin/admin123  
- 陆陆续续收到一些打赏，为了更好的体验已用于演示服务器升级。谢谢各位小伙伴。

演示地址：http://ruoyi.vip  
文档地址：http://doc.ruoyi.vip

## 演示图

 
     
           
           
     
     
           
           
     
     
           
           
     
	 
           
           
     	 
     
           
           
     
	 
           
           
     
	 
           
           
     
	 
           
           
     
     
           
           
     
 


## 若依微服务交流群

QQ群： [![加入QQ群](https://img.shields.io/badge/42799195-blue.svg)](https://jq.qq.com/?_wv=1027&k=yqInfq0S) 点击按钮入群。


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6edab54a7be56d547672e6555de2176b3b45f1174bf5ab56b38d50ea125c21c78224fccb7fcc4338627fc1807b3a49c9fa)