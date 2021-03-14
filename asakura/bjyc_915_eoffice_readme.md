eoffice
=======

java  struts2 hibernate  jbpm 办公管理系统
----------------------------------------------------------------------
#导入用户数据，便于登录
	导入tool目录里面的[joffice21-user.sql];


运行方法：mvn tomcat:run -Dmaven.test.skip=tue

登录账号:admin/admin
如果想更改密码,则执行:com.palmelf.test.system.AppUserDaoTestCase类的resetPassword这个方法

-------------------------
#清空数据库关闭约束
	SET FOREIGN_KEY_CHECKS=0;
	
	
	
	demo
---------


![日程管理](https://raw.githubusercontent.com/jacarrichan/eoffice/master/demo.jpg "")


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e776143bb8b3d4e266eab461f49a1caa6745c2bb0be0bcb3de1babafb802445f596817c6577b9899b2f2f0e9e22b20bb5)