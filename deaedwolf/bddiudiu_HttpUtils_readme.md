HttpUtils是一个追求便捷的HttpRequest工具包
------
>这是山药蛋的第一个开源项目，如有雷同不是巧合，欢迎拍砖。

### HttpUtils能帮你做什么？

##### 1.mapToQuery方法

如果你是一名web程序开发者，你一定拼过t=wxm2-login&lang=zh_CN&ajax=true这样的字符串吧。
例如：https://mp.weixin.qq.com/cgi-bin/loginpage?t=wxm2-login&lang=zh_CN。

		Map  queryMap = new HashMap ();
		queryMap.put("t", "wxm2-login");
		queryMap.put("lang", "zh_CN");
		queryMap.put("ajax", "true");
		String query = ParamUtils.mapToQuery(queryMap);
		
query就是拼接好的t=wxm2-login&lang=zh_CN&ajax=true

##### 2.queryToMap方法

		String queryString = "t=wxm2-login&lang=zh_CN&ajax=true";
		Map  queryMap =  ParamUtils.queryToMap(queryString);

使用mapToQuery方法可以将t=wxm2-login&lang=zh_CN&ajax=true这样的QueryString转换为Map键值对

##### 3. HttpRequest类使用

		HttpRequest request = new HttpRequest();
		String resultVal = request.addHeader("User-Agent", "Mozilla/5.0").addParam("username", "xxx@baidu.com").addParam("pwd", "123456").post("https://mp.weixin.qq.com/cgi-bin/login?lang=zh_CN");

或

		HttpRequest request = new HttpRequest();
		String resultVal = request.addHeader("User-Agent", "Mozilla/5.0").get("https://hao123.com");

链式调用方便快捷，一般场景中你只需要

		String resultVal = new HttpRequest().get("https://hao123.com");

##### 4. 未完待续……


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e5bb0568a48d34250d16654a8b9f05562f09abbe105b0cbeb42a45f759f178370e1468e816b187500078a9eebf6f87722)