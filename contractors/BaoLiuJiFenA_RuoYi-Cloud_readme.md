## 平台简介

* 采用前后端分离的模式，微服务版本前端(基于 [RuoYi-Vue](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e4efbf9a2018792702bfb8d2f94b55c6d7a2c36c7bc4d3e3beccaae130c5d21a5)
* 后端采用Spring Boot、Spring Cloud & Alibaba。
* 注册中心、配置中心选型Nacos，权限认证使用OAuth2。
* 流量控制框架选型Sentinel。

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
账户/密码
- admin/admin123  


## 更新日志
- 2020.06.09：系统由原来的mybatis迁移到mybatis-plus
    - 具体包括更新了聚合项目的parent的pom文件，引入了相关的jar包
    - 更新了system、job、gen等三个module的pom文件，引入mybatisjar包
    - 需要在domin实体类包里面给每个实体类加上 @Tablename("table_name")标签
- 2020.06.09：添加多数据源支持
    - 具体修改了nacos的system、job、gen等三个module的yml文件，添加多个数据源
     
    - 注： 如果需要切换数据源的时候，需要在serviceImpl中的方法上添加 @DS("datasource_name")标签，如果没有标签的话默认使用主标签
- 2020.06.17：修改了访问的时候提示服务拒绝访问
    - 在网关配置 ruoyi-gateway-dev.yml 中，需要在    filters:标签下进行放行地址 /operlog和/logininfo信息
    - 修改日志信息使用 @JsonFormat(pattern = "yyyy-MM-dd HH:mm:ss")比系统时间少8小时的问题，修改为  
     @JsonFormat(pattern = "yyyy-MM-dd HH:mm:ss", timezone = "GMT+8")
    - 添加了docker的相关配置，方便后续在docker中进行环境安装部署
- 2020.06.18：
    - 修改了日志主键为全局唯一id，方便后续做多租户的时候进行扩展 
    - 新增了数据源管理选项，为后续的多租户进行管理
    - 修改了管理员无法修改自己权限的问题 
    - 修改了代码生成时，实体类标签错误的问题 
    - 新增了前端加密方法，但是还没有应用
    - 新增了定时任务，数据源过期以后对过期数据源进行删除
- 2020.06.22：
    - 对系统数据源的相关代码进行修改，完全的集成了mybatis-plus


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e4abc13c2b8ee6d6b2d00e5afc37832d18bdee77b0d0e9b8421f805a035738f2c1696a821f1c125c42563be12f3b52975)