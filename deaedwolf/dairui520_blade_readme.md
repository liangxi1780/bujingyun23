
[![](https://dn-biezhi.qbox.me/LOGO_BIG.png)](http://bladejava.com)

[![Build Status](https://img.shields.io/travis/biezhi/blade.svg?style=flat-square)](https://travis-ci.org/biezhi/blade)
[![maven-central](https://img.shields.io/maven-central/v/com.bladejava/blade-core.svg?style=flat-square)](http://search.maven.org/#search%7Cga%7C1%7Cg%3A%22com.bladejava%22)
[![License](https://img.shields.io/badge/license-Apache%202-4EB1BA.svg?style=flat-square)](https://www.apache.org/licenses/LICENSE-2.0.html)
[![Gitter](https://badges.gitter.im/biezhi/blade.svg)](https://gitter.im/biezhi/blade?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge)

[中文说明](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046c2d847f395043d1ba78c034749ab8a98b434235d3c94079259373d8e46f9effc21e76d43a8cd0ff800d11158b2cafaf3)

## What Is Blade?

Blade is a lightweight MVC framework. It is based on the principles of simplicity and elegance. 
If you like it, please [star and fork it](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046dc86d920f6d3de06430391556ea76627). Thank you!

## Features

* [x] Lightweight: the code is simple and the structure is clear
* [x] Modular (you can choose which components to use)
* [x] Supports plug-in extension mechanism
* [x] RESTful style routing interface
* [x] Supports multiple configuration files (currently properties, json and coding)
* [x] Embedded jetty server and template engine support
* [x] Supports JDK 1.6 and up

## Overview

* Simplicity: The design is simple, easy to understand and doesn't introduce many layers between you and the standard library. The goal of this project is that the users should be able to understand the whole framework in a single day.
* Elegance: `blade` supports the RESTful style routing interface, has no invasive interceptors and provides the writing of DSL grammar.

## Get Start

To get started, first [include the Blade library](http://u.720life.cn/g/a09a304ce03eeabaa4a3b10836b72266f6e9be2d300beb039dff9efec7ae7e33bea4cc1c74bbf2ffa7eb33656aba166e) :

Grab via `Maven`：

```xml
 
	 com.bladejava 
	 blade-core 
	 1.6.2 
 
 
	 com.bladejava 
	 blade-startup 
	 1.0.1 
 
```
or `Gradle`:
```sh
compile 'com.bladejava:blade-core:1.6.2'
compile 'com.bladejava:blade-startup:1.0.1'
```

Create `Main` method like this：

```java
public class App {
	
	public static void main(String[] args) {
		Blade blade = me();
		blade.get("/", (request, response) -> {
			response.html(" Hello blade! ");
		});
		blade.listen(9001).start();
	}
}
```

Run it and point your browser to [http://localhost:9001](http://u.720life.cn/g/e71094f6077cb9592da5b56893f0ad149aff18e806dc26b21d32974e8960eca3). There you go, you've just created your first Blade app!

## API Example

```java
public static void main(String[] args) {
	Blade blade = me();
	blade.get("/user/21", getxxx);
	blade.post("/save", postxxx);
	blade.delete("/del/21", deletexxx);
	blade.put("/put", putxxx);
	blade.listen(9001).start();
}
```

## REST URL Parameters

```java
public static void main(String[] args) {
	Blade blade = me();
	blade.get("/user/:uid", (request, response) -> {
		Integer uid = request.paramAsInt("uid");
		response.text("uid : " + uid);
	});
	
	blade.get("/users/:uid/post/:pid", (request, response) -> {
		Integer uid = request.paramAsInt("uid");
		Integer pid = request.paramAsInt("pid");
		String msg = "uid = " + uid + ", pid = " + pid;
		response.text(msg);
	});
	
	blade.listen(9001).start();
}
```

## Form URL Parameters

```java
public static void main(String[] args) {
	Blade blade = me();
	blade.get("/user", (request, response) -> {
		Integer uid = request.queryAsInt("uid");
		response.text("uid : " + uid);
	});
	blade.listen(9001).start();
}
```

## Upload File

```java
public void upload_img(Request request, Response response){
	
	FileItem[] fileItems = request.files();
	if(null != fileItems && fileItems.length > 0){
		
		FileItem fileItem = fileItems[0];
		File file = fileItem.getFile();
		
		String fileRealPath = "your upload file path!";
		
		nioTransferCopy(file, fileRealPath);
	}
}
```

## Route Config File

`route.conf`

```sh
GET		/					IndexRoute.home
GET		/signin				IndexRoute.show_signin
POST	/signin				IndexRoute.signin
GET		/signout			IndexRoute.signout
POST	/upload_img			UploadRoute.upload_img
```

## Route Intercept

```java
public static void main(String[] args) {
	Blade blade = me();
	blade.before("/.*", (request, response) -> {
		System.out.println("before...");
	});
	blade.listen(9001).start();
}
```

## DSL DB Operation

```java
// query
List  posts =
	AR.find("where title like ? order by id desc limit ?,?", title, page, count).list(Post.class);

// save
String insertSql = "insert into t_post (title, content, view_count, create_time) values (?,?,?,?)";
AR.update(insertSql, title, content, 0, new Date()).commit();

// update
AR.update("update t_post set title = ? and content = ? where id = ?",title, content, id).commit();

// delete
AR.update("delete from t_post where id = ?",id).commit()
```

You may refer to these examples for additional guidance:

+ [Hello Blade](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046c2d31ed5712b8569bccfcd65db30ed04c1a6f7feaa3ba652e5437c10b3a36908)
+ [BBS WebSite](http://u.720life.cn/g/00dfd25147ea8efc0e2165e740dde032b32b9226362260b9844e5be5b9273a84)
+ [API Doc](http://u.720life.cn/g/a09a304ce03eeabaa4a3b10836b72266a1ee3da6a1805c1146520fe349827a46)
+ [User Guide](http://u.720life.cn/g/a09a304ce03eeabaa4a3b10836b7226664457eef64134252a14385ed3a7149fc)
+ [Version Changes](LAST_VERSION.md)
+ [Examples](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046c2d31ed5712b8569bccfcd65db30ed04)

## Plan

- 1. Add the test code
- 2. Optimize the code base
- 3. Optimization of concurrent ability
	
## Update

[update log](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046c2d847f395043d1ba78c034749ab8a9897fd9023b0e0add79826adce2a3699d0d4efc5c467dad3a70a8df2697ef4a55e)

## Contact

- Blog:[https://biezhi.me](http://u.720life.cn/g/0660f4e248161c8e0a585f05fdc87ef7dfc2d2c60af992f34672236a839ee960)
- Mail: biezhi.me@gmail.com

## Contributor

Thank you very much for the developers to help in the project, if you are willing to contribute, welcome!

- [mfarid](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046c8094a4f2592ea2e40b13bbc7a3dee40)
- [daimajia](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046abe7d3e5e7fb2dd74ca2259f1546b3b2)
- [shenjie1993](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304633ab53f1dbb6dd02cfe05a8371c89252)
- [sumory](http://u.720life.cn/g/54145d0471d91890860f7f8463c030462b5386f7738c634a58a6f728f078247f)
- [udaykadaboina](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046359fc31fe05c497cf2637f8da32e37d7)
- [SyedWasiHaider](http://u.720life.cn/g/54145d0471d91890860f7f8463c030468f891ec91ee1c3afbf59f99df3997d5c8f4982a731075414dc249026c1f777aa)
- [Awakens](http://u.720life.cn/g/54145d0471d91890860f7f8463c030460d45f3d29f0f2ccced5014d27b31396c)
- [shellac](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046659e2a9c085e7775b87da78c8cc735d9)
- [SudarAbisheck](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046bb7f85f59dab1a6e9990dc70e2ded424)

## Licenses

Please see [Apache License](LICENSE)



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ed54e74b68782e3d4cb68aecac5e209cebd438ea0a3c7aa79574a655a175d52a7c6196b5aaaf28f31d585f09109e6d28a)