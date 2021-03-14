# Open-shop是一套完全开源的微信小程序商场系统
当前版本:2.0.1  
官方网站：http://www.51app.ink/ 
QQ交流群号：877611106  
微信一对一服务群(收费)：请加微信（lalage1983）

很多人想找一套真正完全开源的微信小程序商城而找不到，现在我们团队经过整合码云开源代码后重磅对出此套完全开源程序。希望大家可以支持我们，我们会不断完善代码和推出新功能来让大家更好的使用。

======================================================================================
# 最新更能增加大家期盼的分销功能代码一并开源
# 后续spring-cloud架构商城陆续上线
======================================================================================

# ※最新版修复BUG
1.会员管理中微信名称带表情符号处理 
2.商品规格变成动态规格； 
3.商品全部用优惠券购买优化； 
4.订单重复提交过滤； 
5.微信登录缓存失效； 
6.sql防注入； 
7.等等几十记不清楚的个BUG； 

# 特点 
* 免费完整开源：基于MIT协议，源代码完全开源，无商业限制,51工作室开发团队承诺将系统永久完整开源； 
* 无BUG：经过严格测试，开箱即用； 
* 编码优雅：代码结构清晰,注解非常详细，方便小伙伴们学习和使用。； 
* 持久更新：会定期公布开发计划。并按计划提交新的功能； 
* 活跃的社群：官方QQ群有专人回复，及时耐心的解答问题； 

# 面向对象
* Open-Shop是企业在创立初期很好的技术基础框架，加快公司项目开发进度，当然也可以对现有的系统进行升级；
* 个人开发者也可以使用Open-Shop承接外包项目；
* 初学JAVA的同学可以下载源代码来进行学习交流；

# 技术框架
* 核心框架：Spring Framework 4
* 安全框架：Apache Shiro 1.2
* 视图框架：Spring MVC 4
* 持久层框架：MyBatis 3
* 数据库连接池：Alibaba Druid 1.0
* 日志管理：SLF4J 1.7、Log4j
* JS框架：Vue 2.5.1，iview，layer 3.0.3，jquery 2.2.4，jqgrid 5.1.1 
* CSS框架：Twitter bootstrap3.3.7。
* 富文本：froala_editor1.2.2

# 开发环境
建议开发者使用以下环境，这样避免版本带来的问题
* IDE:eclipse
* DB:Mysql5.8
* JDK:JAVA8
* WEB:Tomcat8

# 运行环境
* WEB服务器：Weblogic、Tomcat、WebSphere、JBoss、Jetty 等
* 数据库服务器：Mysql5.8
* 操作系统：Windows、Linux、Unix 等


# 快速体验
* 将Open-Shop项目源码通过maven形式导入eclipse；
* 导入Open-Shop.sql数据文件,注意：数据库使用utf-8编码； 
* 修改platform-admin/platform.properties文件中的数据库设置参数；
* tomcat中加载platform-framework项目
* 访问后台地址：http://ip|域名/项目发布名/
* 管理员账号，用户名：默认 密码：默认

# 小程序部署：
* 打开小程序工具；
* 选择你下载的源代码wx-mall小程序项目；
* 输入你的AppID；
* 填写你的项目名称；
* 进入之后修改config文件夹里的api.js文件，把NewApiRootUrl改为你后台接口地址即刻运行。

# 小程序演示地址
![](https://images.gitee.com/uploads/images/2019/0223/145541_9fe99a75_1293644.jpeg "演示地址")
# 后端演示地址
https://shop.51shop.ink 用户名:admin  密码:admin

# 小程序演示效果
![](https://images.gitee.com/uploads/images/2019/0223/145541_e727889d_1293644.jpeg "前段演示")

# 后端登录界面
![登录界面](https://images.gitee.com/uploads/images/2019/0223/145541_ceb02a32_1293644.jpeg "登录，小程序商城")
# 主界面
![主界面](https://images.gitee.com/uploads/images/2019/0223/145546_1c4fc356_1293644.jpeg "主界面，插件商城")
# 菜单
![菜单](https://images.gitee.com/uploads/images/2019/0223/145541_2a1e5aba_1293644.png "菜单1")

本项目来自码云上platform-wechat-mall（https://gitee.com/fuyang_lipengjun/platform）项目。
我们修复了所有发现的bug，还有自己的新功能增加。
后面会有不断的更新新功能。


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6eecb11ad33c1cd09c77717e2c484dbf00ace8f37455611bda5b1696248052add10eb848840d39d6e08240c84c4840ae628c9744508c46d72794f9d57f5c4ce8a9)