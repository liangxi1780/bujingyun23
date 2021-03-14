捷微H5活动开源平台（h5huodong.com）
==========
特点：（采用JAVA微服务框，插件式组件化、开发H5营销活动，支持独立部署，解决微信活动大用户、高并发问题）

P3-Weixin 
==========
特点：（微服务框架，松耦合、插件模式、组件化）

技术交流
==========
* 官网：[H5活动营销平台](http://u.720life.cn/g/f55f85ca313e25bebe4e6d36eb38ad63d083ba7e95538b909deb391a4c83c0ac)
* 论坛：[www.jeecg.org](http://u.720life.cn/g/b4fcde2c1409bb1f59ad66363fddb32316db2e8cce2c772ae0d20db42a78d5d7)
* 捷微H5活动开发群: 237161527

演示公众号（H5活动汇）
==========
![github](http://www.jeecg.org/data/attachment/forum/201601/25/180314mjvputsot6hhtvoa.jpg "jeewx521")

### 微信H5活动插件列表（陆续更新..）
	  1.微信砍价活动   P3-Biz-gzbargain
	  2.摇一摇送卡券   P3-Biz-shaketicket
	  3.九宫格活动     P3-Biz-jiugongge
	  4.斧头帮砍价     P3-Biz-commonftb
	  
	  
### 砍价活动-效果图
![github](http://www.jeecg.org/data/attachment/forum/201601/25/180710anjfgtn677nojgg0.png "jeecg")
### 九宫格活动-效果图
![github](http://www.jeecg.org/data/attachment/forum/201601/25/180716vp55nguk5ggwqngw.png "jeecg")
### 斧头帮砍价-效果图
![github](http://www.jeecg.org/data/attachment/forum/201601/25/180500iwpg1agqm778wggp.png "jeecg")
### 摇一摇送卡券-效果图
![github](http://www.jeecg.org/data/attachment/forum/201601/25/180718zwfdl9ml1a15w8jf.png "jeecg")


【开发文档】

![github](http://img.blog.csdn.net/20151028163509595?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQv/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/Center "jeecg")
* [  文档下载来点我](http://u.720life.cn/g/b4fcde2c1409bb1f59ad66363fddb3235c7498b3747e0b953f7e153f50db9c74fd672b8bf1b3c72466c60f642fedb3cb6d6f8cc29b300a68c0bc689ab13d2eb3)



	  
【架构说明】

    1.P3-weixin 采用SpringMvc + Mybatis + Velocity + Maven(构建) 框架技术
    2.插件引入方式
        pom.xml文件中，引入新开发的插件
         
 	     
			 org.jeecgframework 
			 P3-Biz-gzbargain 
			 2.0.0 
		 
	3.项目启动访问方式：
	  采用maven方式，启动Web项目
      http://localhost:8080/P3-Web/{页面访问地址}
    4.页面层面不能采用jsp，需要采用模板语言Velocity
    5.实现插件式开发，按照模块进行开发，每个模块可以单独达成jar包
	6.数据库配置文件：
	  src/main/resources/db.properties
	  
	  
【开发入门】

	1.Eclipse + Maven + JDK7
    2.项目以Maven方式导入eclipse
	3.执行Mysql数据库脚本，每个项目脚本单独提供
	    P3-Web\doc\db\p3-base-init.sql
		P3-Biz-jiugongge\doc\db\jiugongge-init.sql
		P3-Biz-gzbargain\doc\db\gzbargain-init.sql
		P3-Biz-commonftb\doc\db\commonftb-init.sql
		P3-Biz-shaketicket\doc\db\shaketicket-init.sql
		
		完整项目SQL脚本：
		docs\p3-weixin-all-mysql.sql
	4.采用maven方式，启动主项目P3-Web，命令：tomcat:run
      活动访问地址：
	     http://localhost:8080/P3-Web/gzbargain/toIndex.do?actId=actgzbargain00001&openid=oR0jFt_DTsAUJebWqGeq3A1VWfRw&subscribe=1
	  说明：插件不能单独启动，maven方式引入到Web项目
	5.系统默认登录账号 admin/123456
	  
	
【代码生成器】

	1.工具类：P3-Web/src/main/java/org/jeecgframework/p3/cg/util/CodeToolUtil.java
	2.配置文件：P3-Web/src/main/resources/p3-cg-config.properties



### H5活动营销平台（后台）
![github](http://img.blog.csdn.net/20160830143702156?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQv/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/Center "jeecg")
![github](http://img.blog.csdn.net/20151028202206676?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQv/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/Center "jeecg")
![github](http://www.jeecg.org/data/attachment/forum/201601/25/182100gwfrlwssjbp278wf.png "jeecg")


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e4d4b0938205846439fa354657a616754c9a8a3ba487992567168766da0314f0fea9c0627820fb00a5419efbd288d46fc)