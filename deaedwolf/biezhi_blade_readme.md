 
       
 
 Based on  Java8  +  Netty4  to create lightweight, high-performance, simple and elegant Web framework 😋 
 Spend  1 hour  to learn it to do something interesting, a Spring in addition to the framework of the best choice. 
 
    🐾  Quick Start  |
    📘  Blade In Action  |
    🎬  Video Tutorial  |
    🌚  Contribution  |
    💰  Donate  |
    🇨🇳  简体中文 
 
 
       
       
       
       
       
       
       
 

***

## What Is Blade?

`Blade` is a pursuit of simple, efficient Web framework, so that `JavaWeb` development even more powerful, both in performance and flexibility.
If you like to try something interesting, I believe you will love it.
If you think this item is good can [star](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046c2d847f395043d1ba78c034749ab8a98ed3e353d8f3d2bbd49b228880dc39d08) support or [donate](http://u.720life.cn/g/4e97c56b06fd74686f0fc6b5132d4b17e2776d3a0f48e38759885b4aba2670ad) it :blush:

## Features

* [x] A new generation of MVC frameworks that do not depend on more libraries
* [x] Get rid of SSH's bloated, modular design
* [x] Source less than `500kb`, learning is also simple
* [x] Restful style routing design
* [x] Template engine support, view development more flexible
* [x] High performance, 100 concurrent qps 14w/s
* [x] Run the `JAR` package to open the web service
* [x] Streaming API style
* [x] `CSRF` and `XSS` defense
* [x] `Basic Auth` and `Authorization`
* [x] Supports plug-in extensions
* [x] Support webjars resources
* [x] Based on `cron` expression of tasks
* [x] Built-in a variety of commonly used middleware
* [x] Built-in JSON output
* [x] JDK8 +

## Overview

» Simplicity: The design is simple, easy to understand and doesn't introduce many layers between you and the standard library. The goal of this project is that the users should be able to understand the whole framework in a single day. 
» Elegance: `blade` supports the RESTful style routing interface, has no invasive interceptors and provides the writing of DSL grammar. 
» Easy deploy: support `maven` package `jar` file running. 

## Quick Start

Run with `Maven`：

Create a basic `Maven` project

```xml
 
     com.bladejava 
     blade-mvc 
     2.0.9.BETA3 
 
```

> Do not create a `webapp` project, blade is not so much trouble.

or `Gradle`:

```sh
compile 'com.bladejava:blade-mvc:2.0.9.BETA3'
```

Write `main` method, try `Hello World`：

```java
public static void main(String[] args) {
    Blade.of().get("/", ctx -> ctx.text("Hello Blade")).start();
}
```

Using browser open http://localhost:9000 so you can see the first `Blade` application!

## Contents

- [**`Register Route`**](#register-route)
    - [**`HardCode`**](#hardCode)
    - [**`Controller`**](#controller)
- [**`Get Request Parameters`**](#get-request-parameters)
    - [**`Form Parameters`**](#form-parameters)
    - [**`Path Parameters`**](#path-parameters)
    - [**`Body Parameters`**](#body-parameters)
    - [**`Parse To Model`**](#parse-to-model)
- [**`Get Environment`**](#get-environment)
- [**`Get Header`**](#get-header)
- [**`Get Cookie`**](#get-cookie)
- [**`Static Resource`**](#static-resource)
- [**`Upload File`**](#upload-file)
- [**`Set Session`**](#set-session)
- [**`Render To Browser`**](#render-to-broser)
    - [**`Render JSON`**](#render-json)
    - [**`Render Text`**](#render-text)
    - [**`Render Html`**](#render-html)
- [**`Render Template`**](#render-template)
    - [**`Default Template`**](#default-template)
    - [**`Jetbrick Template`**](#jetbrick-template)
- [**`Redirects`**](#redirects)
- [**`Write Cookie`**](#write-cookie)
- [**`Web Hook`**](#web-hook)
- [**`Logging`**](#logging)
- [**`Basic Auth`**](#basic-auth)
- [**`Change Server Port`**](#change-server-port)
- [**`Configuration SSL`**](#configuration-ssl)
- [**`Custom Exception Handler`**](#custom-exception-handler)

## Register Route

### HardCode

```java
public static void main(String[] args) {
    // Create Blade，using GET、POST、PUT、DELETE
    Blade.of()
        .get("/user/21", getting)
        .post("/save", posting)
        .delete("/remove", deleting)
        .put("/putValue", putting)
        .start();
}
```

### `Controller`

```java
@Path
public class IndexController {

    @GetRoute("signin")
    public String signin(){
        return "signin.html";
    }

    @PostRoute("signin")
    @JSON
    public RestResponse doSignin(RouteContext ctx){
        // do something
        return RestResponse.ok();
    }

}
```

## Get Request Parameters

### Form Parameters

Here is an example:

**By Context**

```java
public static void main(String[] args) {
    Blade.of().get("/user", ctx -> {
        Integer age = ctx.queryInt("age");
        System.out.println("age is:" + age);
    }).start();
}
```

**By Annotation**

```java
@PostRoute("/save")
public void savePerson(@Param String username, @Param Integer age){
    System.out.println("username is:" + username + ", age is:" + age)
}
```

The terminal sends a data test

```bash
curl -X GET http://127.0.0.1:9000/user?age=25
```

```bash
curl -X POST http://127.0.0.1:9000/save -F username=jack -F age=16
```

### Path Parameters

**By RouteContext**

```java
public static void main(String[] args) {
    Blade blade = Blade.of();
    // Create a route: /user/:uid
    blade.get("/user/:uid", ctx -> {
        Integer uid = ctx.pathInt("uid");
        ctx.text("uid : " + uid);
    });

    // Create two parameters route
    blade.get("/users/:uid/post/:pid", ctx -> {
        Integer uid = ctx.pathInt("uid");
        Integer pid = ctx.pathInt("pid");
        String msg = "uid = " + uid + ", pid = " + pid;
        ctx.text(msg);
    });
    
    // Start blade
    blade.start();
}
```

**By Annotation**

```java
@GetRoute("/users/:username/:page")
public void userTopics(@PathParam String username, @PathParam Integer page){
    System.out.println("username is:" + usernam + ", page is:" + page)
}
```

The terminal sends a data test

```bash
curl -X GET http://127.0.0.1:9000/users/biezhi/2
```

### Body Parameters

```java
public static void main(String[] args) {
    Blade.of().post("/body", ctx -> {
        System.out.println("body string is:" + ctx.bodyToString())
    }).start();
}
```

The terminal sends a data test

```bash
curl -X POST http://127.0.0.1:9000/body -d '{"username":"biezhi","age":22}'
```

### Parse To Model

This is `User` model.

```java
public class User {
    private String username;
    private Integer age;
    // getter and setter
}
```

**By Annotation**

```java
@PostRoute("/users")
public void saveUser(@Param User user){
    System.out.println("user => " + user);
}
```

The terminal sends a data test

```bash
curl -X POST http://127.0.0.1:9000/users -F username=jack -F age=16
```

**Custom model identification**

```java
@PostRoute("/users")
public void saveUser(@Param(name="u") User user){
    System.out.println("user => " + user);
}
```

The terminal sends a data test

```bash
curl -X POST http://127.0.0.1:9000/users -F u[username]=jack -F u[age]=16
```

**Body Parameter To Model**

```java
public void getUser(@BodyParam User user){
    System.out.println("user => " + user);
}
```

The terminal sends a data test

```bash
curl -X POST http://127.0.0.1:9000/body -d '{"username":"biezhi","age":22}'
```

## Get Environment

```java
Environment environment = WebContext.blade().environment();
String version = environment.get("app.version", "0.0.1");;
```

## Get Header

**By Context**

```java
@GetRoute("header")
public void getHeader(RouteContext ctx){
    System.out.println("Host => " + ctx.header("Host"));
    // get useragent
    System.out.println("UserAgent => " + ctx.userAgent());
    // get client ip
    System.out.println("Client Address => " + ctx.address());
}
```

**By Annotation**

```java
@GetRoute("header")
public void getHeader(@HeaderParam String Host){
    System.out.println("Host => " + Host);
}
```

## Get Cookie

**By Context**

```java
@GetRoute("cookie")
public void getCookie(RouteContext ctx){
    System.out.println("UID => " + ctx.cookie("UID"));
}
```

**By Annotation**

```java
@GetRoute("cookie")
public void getCookie(@CookieParam String UID){
    System.out.println("Cookie UID => " + UID);
}
```

## Static Resource

Blade built a few static resource catalog, as long as you will save the resource file in the static directory under the classpath, and then browse http://127.0.0.1:9000/static/style.css

If you want to customize the static resource URL.

```java
Blade.of().addStatics("/mydir");
```

Of course you can also specify in the configuration file. `application.properties` (location in classpath)

```bash
mvc.statics=/mydir
```

## Upload File

**By Request**

```java
@PostRoute("upload")
public void upload(Request request){
    request.fileItem("img").ifPresent(fileItem -> {
        byte[] data = fileItem.getData();
        // Save the temporary file to the specified path
        Files.write(Paths.get(filePath), data);
    });
}
```

**By Annotation**

```java
@PostRoute("upload")
public void upload(@MultipartParam FileItem fileItem){
    byte[] data = fileItem.getData();
    // Save the temporary file to the specified path
    Files.write(Paths.get(filePath), data);
}
```

## Set Session

```java
public void login(Session session){
    // if login success
    session.attribute("login_key", SOME_MODEL);
}
```

## Render To Browser

### Render JSON

**By Context**

```java
@GetRoute("users/json")
public void printJSON(RouteContext ctx){
    User user = new User("biezhi", 18);
    ctx.json(user);
}
```

**By Annotation**

This form looks more concise 😶

```java
@GetRoute("users/json")
@JSON
public User printJSON(){
    return new User("biezhi", 18);
}
```

### Render Text

```java
@GetRoute("text")
public void printText(RouteContext ctx){
    ctx.text("I Love Blade!");
}
```

### Render Html

```java
@GetRoute("html")
public void printHtml(RouteContext ctx){
    ctx.html("  I Love Blade!  ");
}
```

## Render Template

By default all template files are in the templates directory, most of the cases you do not need to change it.

### Default Template

By default, the Blade uses the built-in template engine, which is very simple if you really do a web project can try several other extensions.

```java
public static void main(String[] args) {
    Blade.of().get("/hello", ctx -> {
        ctx.attribute("name", "biezhi");
        ctx.render("hello.html");
    }).start(Hello.class, args);
}
```

The `hello.html` template

```html
 
 
 
     
     Hello Page 
 
 

     Hello, ${name} 

 
 
```

### Jetbrick Template

**Config Jetbrick Template**

Create a `BladeLoader` class load some config

```java
@Bean
public class TemplateConfig implements BladeLoader {

    @Override
    public void load(Blade blade) {
        blade.templateEngine(new JetbrickTemplateEngine());
    }

}
```

Write some data for the template engine to render

```java
public static void main(String[] args) {
    Blade.of().get("/hello", ctx -> {
        User user = new User("biezhi", 50);
        ctx.attribute("user", user);
        ctx.render("hello.html");
    }).start(Hello.class, args);
}
```

The `hello.html` template

```html
 
 
 
     
     Hello Page 
 
 

     Hello, ${user.username} 

    #if(user.age > 18)
         Good Boy! 
    #else
         Gooood Baby! 
    #end

 
 
```

[Render API](http://u.720life.cn/g/a53fd5eac14a3b6d1d78cbeb251e801c2c3438ec627cdf4af4e1eff86a298d8261c85c15730a1a40583de7cdc3efe4c6b2a32d6323708a9a1424d8e597f51b9a8d3bfb13c259e153a31a7960378153dc8b89bdf69c878d306477bae2c00b06d202c0e223ecb1348d8259b0bddc312c9861b1a85ad1f4642cc339259b31209362)

## Redirects

```java
@GetRoute("redirect")
public void redirectToGithub(RouteContext ctx){
    ctx.redirect("https://github.com/biezhi");
}
```

[Redirect API](http://u.720life.cn/g/a53fd5eac14a3b6d1d78cbeb251e801c2c3438ec627cdf4af4e1eff86a298d8261c85c15730a1a40583de7cdc3efe4c6b2a32d6323708a9a1424d8e597f51b9a8d3bfb13c259e153a31a7960378153dcd72bf96aeaf4e257b3e44de99c145cbdc5f56bbfe2fdd22795b55fca359aedcb59253c6a31dab6f8294225c775ea662b)

## Write Cookie

```java
@GetRoute("write-cookie")
public void writeCookie(RouteContext ctx){
    ctx.cookie("hello", "world");
    ctx.cookie("UID", "22", 3600);
}
```

[Cookie API](http://u.720life.cn/g/a53fd5eac14a3b6d1d78cbeb251e801c2c3438ec627cdf4af4e1eff86a298d8261c85c15730a1a40583de7cdc3efe4c6b2a32d6323708a9a1424d8e597f51b9a8d3bfb13c259e153a31a7960378153dc1463d18dd730f3195b48a7803ef462745c070c958f982097ec1aa5d4243d112d8f9263bbb90ce39416cb4b9f7364938c64fd2e13c4b971697ec6392f7016d12d)

## Web Hook

`WebHook` is the interface in the Blade framework that can be intercepted before and after the execution of the route.

```java
public static void main(String[] args) {
    // All requests are exported before execution before
    Blade.of().before("/*", ctx -> {
        System.out.println("before...");
    }).start();
}
```

## Logging

Blade using slf4-api as a log interface, the default implementation of a simple log package (modified from simple-logger), if you need complex logging you can also use custom, you only need to exclude the `blade-log` in dependencies.

```java
private static final Logger log = LoggerFactory.getLogger(Hello.class);

public static void main(String[] args) {
    log.info("Hello Info, {}", "2017");
    log.warn("Hello Warn");
    log.debug("Hello Debug");
    log.error("Hello Error");
}
```

## Basic Auth

Blade built a few middleware, when you need Basic certification can be used, of course, can also be customized to achieve.

```java
public static void main(String[] args) {
    Blade.of().use(new BasicAuthMiddleware()).start();
}
```

Specify the user name and password in the `application.properties` configuration file.

```bash
http.auth.username=admin
http.auth.password=123456
```

## Change Server Port

There are three ways to modify the port, hard coding, configuration files, start the command line parameters.

**Hard Coding**

```java
Blade.of().listen(9001).start();
```

**Configuration For `application.properties`**

```bash
server.port=9001
```

**Command Line**

```bash
java -jar blade-app.jar --server.port=9001
```

## Configuration SSL

**Configuration For `application.properties`**

```bash
server.ssl.enable=true
server.ssl.cert-path=cert.pem
server.ssl.private-key-path=private_key.pem
server.ssl.private-key-pass=123456
```

## Custom Exception Handler

Blade has already implemented an exception handler by default, and sometimes you need to deal with custom exceptions, so you can do it.

```java
@Bean
public class GlobalExceptionHandler extends DefaultExceptionHandler {
    
    @Override
    public void handle(Exception e) {
        if (e instanceof CustomException) {
            CustomException customException = (CustomException) e;
            String code = customException.getCode();
            // do something
        } else {
            super.handle(e);
        }
    }

}
```

How easy it all looks, but the features above are the tip of the iceberg, and there are more surprises to see in the documentation and sample projects:

+ [FirstBladeApp](http://u.720life.cn/g/54145d0471d91890860f7f8463c030469a007a0208bc5251bfde8254074e63f230134cf644d9145bf93c0818b7fc3d35)
+ [Blade Demos](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304692ad4bd72ce8c7417164556ba02cadbfeb6d9ff5293521e8b064fc09ee11ee33)
+ [Awesome Blade](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046cab3e32c0a219554296ebc2ac2ea8ebb0307892c34d19b48dd9b91806744262f)

## Change Logs

[See Here](http://u.720life.cn/g/4e97c56b06fd74686f0fc6b5132d4b17162c2d3c7a2e2e8c44e32f14af954c203cb34d96286c7973f6b6632da142ea1e)

## Contact

- Twitter: [biezhi](http://u.720life.cn/g/5ea88169c4a0fbd169233d52478d54fe850116c8f260a8273b1ef652e9cc1dd2)
- Mail: biezhi.me@gmail.com

## Contributors

Thanks goes to these wonderful people

 
 
| [    王爵nice  ](http://u.720life.cn/g/5ea88169c4a0fbd169233d52478d54fe850116c8f260a8273b1ef652e9cc1dd2) | [    ccqy66  ](http://u.720life.cn/g/54145d0471d91890860f7f8463c030465c70b75c734876f5cc8fd2ce7ab644e2) | [    王晓辉(Eddie)  ](http://u.720life.cn/g/54145d0471d91890860f7f8463c030465148e1ef1684025b4be458a51695f87e) | [    代码家  ](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046abe7d3e5e7fb2dd74ca2259f1546b3b2) | [    David Dong  ](http://u.720life.cn/g/54145d0471d91890860f7f8463c030463712d230fd3413b65316801b1573fd62) | [    José Vieira Neto  ](https://github.com/NetoDevel) | [    Schneeman  ](https://github.com/schneems) |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| [    Mohd Farid  ](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046c8094a4f2592ea2e40b13bbc7a3dee40) | [    sumory  ](http://u.720life.cn/g/54145d0471d91890860f7f8463c030462b5386f7738c634a58a6f728f078247f) | [    Uday K  ](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046359fc31fe05c497cf2637f8da32e37d7) | [    Antony Kwok  ](http://u.720life.cn/g/54145d0471d91890860f7f8463c030460d45f3d29f0f2ccced5014d27b31396c) | &nbsp; | &nbsp; | &nbsp; |
 

Contributions of any kind are welcome!

## Licenses

Please see [Apache License](LICENSE)



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e748a16c769b3e5e31d2327f882cacfe76483b6a2c4766a661e7c26dc2aeb2a594a68072e2bb0e23b74c677880b426a23)