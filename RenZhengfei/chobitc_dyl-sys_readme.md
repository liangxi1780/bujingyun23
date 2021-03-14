# 后台权限管理系统（dyl-sys）

  项目简介： 
    layui升级成2.15版本~~~~~~~~
    1、dyl-sys由Java编写的后台管理系统，架构简单易懂，二次开发非常简单，初学者上手更容易
    2、 目前有很多类似的后台框架，个人使用后还是感觉有的太老，有的架构太臃肿，数据库框架方面摒弃Hibernate Mybatis
           这种臃肿的框架（反正个人不喜欢用）就使用原生的方便调试，方便查看。权限方面摒弃shiro这种复杂的框架，结合业务需求，
           自定义注解和标签来实现简单，让项目看起来很简洁，都是些日常开发中实用的功能。
    3、可以随意新增菜单并配置增删改查的权限。
    4、项目技术分层明显，用户可以根据自己的业务模块进行相应地扩展，很方便二次开发。
    5、统一的日志记录出口，能实时记录发生异常的url地址，准确定位异常原因，解决bug。
    6、如果您在使用过程中遇到问题，项目交流群：60652257，欢迎加入。邮箱:84829698@qq.com，代码会不定期更新
  
  技术架构： 
  
     1、技术架构：Spring Spring MVC、LayUi、JdbcTemplate Oracle等。
     2、功能说明：
       2.1、用户管理：创建系统用户，及设置角色
       2.2、角色管理：创建角色及分配角色权限
       2.3、菜单管理：创建系统菜单，并设置访问地址及菜单拥有子权限
       2.4、定时器管理：通过数据库实时配置定时器创建及删除。
       2.5、数据库监控：采用ali durid实时监控数据库
       2.6、通过log4j实时记录用户的访问地址，便于后续统计栏目访问情况。
       2.7、权限管理后台通过自定义注解、前台通过自定义标签结合实现，简单易懂。
       2.8、代码生成器：选择一个表或者视图，选择对应的模板生成代码并打包下载。
     3、使用说明：
      3.0、本项目JDK默认显示的是1.6，用户可以自行选择1.6+。
      3.1、数据库使用oracle/mysql 双版本，根据需求选择其中一个即可，初始化脚本位于项目中的WebRoot/db/dyl-sys-for(oracle/mysql).sql。
      3.2、修改src/config/config.properties下的日志路径。
      3.3、后台的登陆路径为http://ip:端口/login!intologin.do,开发管理员：dev/123 系统管理员：admin/admin   
          
  前端项目概览： 
    ![菜单管理](https://git.oschina.net/uploads/images/2017/0526/165909_c142f8b3_493165.png "菜单管理")
	![用户管理](https://git.oschina.net/uploads/images/2017/0526/165937_68409e41_493165.png "用户管理")
	![角色管理](https://git.oschina.net/uploads/images/2017/0526/170026_b94a4693_493165.png "角色管理")
	![定时任务管理](https://git.oschina.net/uploads/images/2017/0526/170046_2099722b_493165.png "定时任务管理")
	![数据库监控](https://git.oschina.net/uploads/images/2017/0526/170116_457c17c0_493165.png "数据库监控")
    ![代码生成器](https://git.oschina.net/uploads/images/2017/0601/155516_d37b13ad_493165.png "代码生成器")
    ![日志管理](https://git.oschina.net/uploads/images/2017/0606/104747_689ba984_493165.png "日志管理")
![通用上传](https://git.oschina.net/uploads/images/2017/0622/161538_7480fae3_493165.png "在这里输入图片标题")


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6eb6b9e286ffe45a74e034dd8b5045d04e9941b082f823a20bfeab2e144868b8778e716c7a956093c000419bde2fd09886)