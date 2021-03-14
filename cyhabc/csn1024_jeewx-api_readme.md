JEEWX-API  微信极速SDK
===============
  （JAVA语言同时支持微信公众号\企业微信\支付窗\小程序\微博等）
===============
最新版本： 1.2.2（发布日期：20181106）
官网：[www.jeewx.com](http://u.720life.cn/g/777ad498d3808edff841aa7bd3054dfde98a66dc2acf421b2dadef665a780beb) 



一、项目介绍：
-----------------------------------
 JEEWX-API 是第一个JAVA版微信极速SDK，集成企业微信SDK，支付窗SDK和微博SDK，可以快速的基于她进行微信公众号、企业微信、支付窗、微博应用开发。
 基于 jeewx-api 开发可以立即拥有简单易用的API，让开发更加轻松自如，节省更多时间。


二、技术交流
-----------------------------------
* 	QQ交流群： ④289709451
* 	技术论坛： www.jeecg.org
* 	技术文档： [http://jeewx-api.mydoc.io](http://u.720life.cn/g/cf5a9fb2455278602da0023c2b4e9d34620d7c3cfb8a575c6ef47b2b822578af)



三、Jeewx-api 集成方法
-----------------------------------
### [1].maven 方式
    在pom.xml 添加jeewx-api 1.2.2依赖
     
		 org.jeecgframework 
		 jeewx-api 
		 1.2.2 
	 
	
### [2].非maven方式
         直接拷贝jeewx-api-1.2.2.jar进项目Lib中
		 




四、测试代码
-----------------------------------

    public static void main(String[] args) {
		try {
			String accesstoken = "yALYWcUbB1hdURQvJ-Qn1jbyq5E0qNraZixnxhC1wtN5sKrAfHifyFHHpRWiUnZ1xnhjN_dcnYqFAgpJqeJJybx2NOVoEDZd7SFLjwFIvM8AJv3a8EGarbY0jo--4vuqUNNhADAQJJ";
			String user_openid = "o8QKAuAyDxxfyuBZ9ugSMR4SR5XQ";
			JwUserAPI.getWxuser(accesstoken, user_openid);
		} catch (WexinReqException e) {
			// TODO Auto-generated catch block
			e.printStackTrace();
		}
		
	}

	
### 公众号体、小程序商城

![github](http://www.jeecg.org/data/attachment/forum/201601/25/180314mjvputsot6hhtvoa.jpg "jeewx521")
![github](https://static.oschina.net/uploads/img/201810/15180859_25Ok.jpg "jeewx521")
    


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ec0e0753f2a2909ab20546d084790db811876133340945e9f13bc0d75228926d2665e9ea9b6aaae964cecad00a6af313f)