## httpKit - 极简、极速的Http Client

- 基于Apache httpclient 4.3.x封装,
- 支持多线程异步请求
- 加入请求连接池
- 统一的参数设置
- 管道式API设计
- 支持双向认证
- 可重复读的Response
- 对Response简单的结果处理(写文件,写流,转Json对象,转String,转byte[])
- 文件上传、下载
- 对重定向路径处理,网络代理
- 很简单的实现会话保持
- 简单的认证功能实现
- 简单的失败重试机制实现
- 暴露用户自定义拦截器
- 所有这些只有一个HttpKit入口,对! 很简单

### 下面简单的例子

- 访问百度首页,自动处理https单向认证

``` java
String url = "https://baidu.com";
//获取页面HTML
String html = HttpKit.get(url).execute().getString();
```

- 请求百度搜索关键字"oschina",并写入文件

``` java
String format = String.format("https://baidu.com/s?wd=%s&tn=98012088_5_dg&ch=11", "oschina");
HttpKit.get(format).execute().transferTo("d:/baiduSearchResult.html");
```

- 上传文件

``` java
FormPart form = FormPart.create()
// 添加额外参数
.addParameter("age", 40)
//添加文件
.addParameter("fileName", new File("d:/test.txt"));
String result = HttpKit.post("http://www.test.com").useForm(form).execute().getString();
```

- 获取oschina 验证码,并写入文件

``` java
String url = "https://www.oschina.net/action/user/captcha?t=0.1058898605559051";
String referer = "https://www.oschina.net/home/reg?goto_page=https%3A%2F%2Fwww.oschina.net%2F";
String userAgent = "Mozilla/5.0 (Windows NT 10.0; WOW64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/58.0.3029.110 Safari/537.36";

HttpKit.get(url)
.setUserAgent(userAgent)
.addHeader("Referer", referer)
.execute().transferTo("d:/img.png");
```

- 百度百科获取json,并转Map

```java
//百度百科地址
String url = "http://baike.baidu.com/api/openapi/BaikeLemmaCardApi?scope=103&format=json&appid=379020&bk_key=%s&bk_length=600";
Map  map = HttpKit.get(String.format(url, "Java")).execute().getJson(Map.class);
System.out.println(map);
```

- 设置网络代理

```java
String url ="https://my.oschina.net";
String html = HttpKit.get(url).setProxy("192.168.10.10", 1182).execute().getString();
System.out.println(html);
```

- 下面是一个综合的例子, 请求www.oschina.net做登录,并获取UserId

```java
String url = "https://www.oschina.net/action/user/hash_login";
String userAgent = "Mozilla/5.0 (Windows NT 10.0; WOW64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/58.0.3029.110 Safari/537.36";

RequestBase request = HttpKit.post(url)
.addParameter("email", "xxxxxxx")
.addParameter("pwd", Sha1Util.getSha1("xxxxxxx"))
.addParameter("verifyCode", "")
.addParameter("save_login", 1)

.addHeader("Origin", "https://www.oschina.net")
.setUserAgent(userAgent);

ResponseWrap response = request.execute();

String resultString = response.getString();
if (resultString != null && resultString.trim().length() > 0) {
	Map  json = response.getJson(Map.class);
	System.out.println("HttpKit登录失败===>" + json.get("msg"));
	return ;
}

System.out.println(response.getString());
System.out.println("登录成功===>" + response.getStatusLine());

//跳转到一个页面, 保持Session, 只需要把登录的HttpKit传到下一次请求即可
String html = HttpKit.get("https://my.oschina.net/yiq", request)
.setUserAgent(userAgent)
.execute().getString();

String userStr = "owner_id\" data-value=\"";
int dataUserIndex = html.indexOf(userStr) + userStr.length();

//获取到UserId
String userId = html.substring(dataUserIndex, html.indexOf("\">", dataUserIndex));
System.out.println("获取到UserId===>" + userId);
```

- 下载文件, 本例下载oschina验证码

```java
HttpKit.get("https://www.oschina.net/action/user/captcha?t=0.1058898605559051")
.setUserAgent("Mozilla/5.0 (Windows NT 10.0; WOW64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/58.0.3029.110 Safari/537.36")
.addHeader("Referer", "https://www.oschina.net/home/reg?goto_page=https%3A%2F%2Fwww.oschina.net%2F")
.execute().transferTo("d:/img.png");
```

- 多线程请求百度云查询域名是否被注册

```java
String url = "https://cloud.baidu.com/api/bcd/search/status";
String Referer = "https://cloud.baidu.com/product/bcd/search.html?keyword=";
String req = "{\"domainNames\":[{\"label\":\"%s\",\"tld\":\"com\"}]}";
String userAgent = "Mozilla/5.0 (Windows NT 6.1; WOW64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/60.0.3107.4 Safari/537.36";

ExecutorService service = Executors.newScheduledThreadPool(30);

ResponseHandler  resp = new ResponseHandler () {
	@Override
	public CheckDomainResult handleResponse(HttpResponse response) throws ClientProtocolException, IOException {
		ResponseWrap responseWrap = new ResponseWrap(response);
		return responseWrap.getJson(CheckDomainResult.class);
	}
};

int count = 100;
RequestFuture [] futures = new RequestFuture[count];

try {
	
	for (int i = 0; i   future = request.executeCallback(service, resp);
		futures[i] = future;
	}
	
	//获取结果
	for (RequestFuture  result : futures) {
		Accurate accurate = result.get().getResult().getAccurate()[0];
		System.out.println("域名:" + accurate.getDomainName() + " 状态:" +accurate.getStatus());
	}
	
} catch (Exception e) {
	e.printStackTrace();
} finally {
	service.shutdown();
}
```

- 双向认证请求

```java
String string = HttpKit.post("https://wwwt.est.com")
.setJKS(new File("jksFile.jks"), "xxxx")
.execute().getString();

System.out.println(string);
```

## License

Apache License Version 2.0



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ee5d087fa6690cb63316559e6f9abc1760e6bde4069a49ec39b83a963a9b9c51b4a0dfc2cc6bdf4f3b1dc642da456f6b9)