#PublicCMS 2017

       

##简介

PublicCMS是采用2017年最新主流技术开发的免费开源JAVACMS系统。架构科学，轻松支持上千万数据、千万PV；支持全站静态化，SSI，动态页面局部静态化等为您快速建站，建设大规模站点提供强大驱动，也是企业级项目产品原型的良好选择。

##获取可运行程序

https://git.oschina.net/sanluan/PublicCMS-war
https://github.com/sanluan/PublicCMS-war

##获取稳定版源码

https://git.oschina.net/sanluan/PublicCMS
https://github.com/sanluan/PublicCMS
https://code.csdn.net/zyyy358/publiccms

##参与研发(预览版)

https://git.oschina.net/sanluan/PublicCMS-preview
https://github.com/sanluan/PublicCMS-preview

##相关下载及文档(知识库)

https://github.com/sanluan/PublicCMS-lib
https://git.oschina.net/sanluan/PublicCMS-lib

##授权

该软件永久开源免费(MIT 授权协议)

##结构说明

* data\publiccms	PublicCMS数据目录
* doc			文档
* publiccms		工程源码
* publiccms-gradle	Gradle配置文件
* publiccms-maven	Maven配置文件
* LISCENSE		授权文件
* README.md		说明
* Update History.md	更新历史

##部署运行

* 根据文档部署工程
* 数据脚本内置管理员账号admin，密码admin

##演示

* 演示站点：https://www.publiccms.com/
* 后台演示：https://cms.publiccms.com/admin/ 演示账号/密码 test/test
* 接口演示：https://cms.publiccms.com/interface.html

##更新记录

###V2017.0318更新：

框架升级:

1. Spring Framework升级到4.3.7
1. Hibernate Search升级到5.5.6
1. Hibernate升级到5.1.3
1. Jackson升级到2.8.6
1. mysql-connector-java升级到5.1.40
1. 源码与gralde,maven配置分离
1. 新增gradle、maven插件：maven-eclipse，maven-idea，gradle-idea

新增功能:

1. 新增免重启的数据库配置、初始化、升级引导程序
1. 新增静态文件管理
1. 新增配置管理
1. 新增站点默认设置
1. 新增部署错误提示
1. 新增工程内置默认动态站点
1. 新增多站点静态文件支持
1. 新增域名格式提示
1. 新增通配域名设置
1. 新增分类是否包含子分类内容设置
1. 新增模块是否作为菜单展示设置
1. 新增分词器设置、默认中文分词器
1. 新增关键词处理函数
1. 新增UserAgeent获取指令，UserAgent解析函数
1. 新增模板demo
1. 新增模板制作帮助页面
1. 新增推荐位异步渲染支持
1. 新增多条内容、分类、推荐位扩展字段获取函数
1. 新增接口授权功能

其他提升:

1. 新增Spring Boot启动方式支持
1. 持久层增加Mybatis
1. 新增Hibernate Redis缓存组件
1. 重构内存缓存、增加redis缓存支持
1. 取消大部分匿名类写法
1. 增加内容扩展字段类型
1. 将方法内可复用变量提升为类静态变量
1. 配置中心登陆注册设置合并
1. 邮件发送改为线程池执行发送任务
1. 域名取消端口区分
1. 模板默认所有输出进行HTML转义
1. 关联关系表取消自增主键改为联合主键
1. 界面修改，LOGO修改
1. 模型由数据库存储改为文件存储
1. 简化站点配置，站点取消资源站点属性
1. 配置文件结构调整
1. 优化推荐位输出
1. 优化jsonp支持，安全性提升
1. 接口测试页面美化
1. 指令自定义名称支持
1. 优化配置文件结构及路径

模板升级所需修改：

1. 需要以HTML输出的字段需要加 ?no_esc
1. 取消所有?html内置函数调用
1. 将数据目录中resource目录下所有文件移动到web目录下，将模板中所有site.resourcePath改为site.sitePath

数据库升级所需修改：

1. 将配置文件中cms.autoInstall设置为true,启动项目后访问首页，进入启动引导程序，然后选择升级数据库

鸣谢：

感谢 心路(xinlu) 提交的代码：Mybatis代码自动生成工具
感谢 Alex.MAO 提交的BUG：添加域名bug，分类修改页面选择内容路径bug
感谢 JARVIS 提交的BUG：分类页面内容模板路径赋值bug
感谢 firework 提交的BUG：推荐位模板编辑页面不能使用网站文件


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e7bba384613ff31dec17415d00779b1c82135fe92669ddbcbf8e4b94b4a89a2126fa5e378e7a023410cde91d1f0c88e2d)