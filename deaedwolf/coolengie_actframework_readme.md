# ACT Framework

[![Join the chat at https://gitter.im/actframework/actframework](https://badges.gitter.im/actframework/actframework.svg)](https://gitter.im/actframework/actframework?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

## News
* ACT 1.0.0 released to Maven Central repository
* ACT 0.7.0-SNAPSHOT: rewrite JSR 303/349 Validation integration
* A [TodoBackend](http://u.720life.cn/g/7af58d3a1d84dd79627cab7442c55083976b0f5a90a359b8980b33d21e286df7) project written in ActFramework: http://github.com/greenlaw110/todomvc-act
* Actframework 正式登录[码云](http://u.720life.cn/g/3e7e8f170da15d1979f4c6b1321cc36b4217ec0b8f35c42e215abdd2ba2bf8926f0b3fdcff4fc809413a314b050999ea7d70672a1f7dbda6249f888550648025)以及[开源中国]http://www.oschina.net/p/actframework
* Actframework [benchmark set](http://u.720life.cn/g/54145d0471d91890860f7f8463c030467c6d6db0534072feca27d7039d489002f7a54df8b82bdb833c653079c45193c378ce0d439735167e7f6acb6a2dc445dad279b8c4f4cc0a2794b4ecd11caccf2419d9bff1309a83166b5bcfccc4b2050d) 
accepted by [TechEmpower Benchmark](http://u.720life.cn/g/587984922c2f36564b2cfde7aef7be58c9f8d9d505fad061d9f4529d1ab040f2b2eddc3b6bcc7bd57de81c5133959df2). Looking forward to
seeing Act in the 14 round test
* A 3rd party [simple benchmark project](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046feed511effb29e3bd3511d60221fe82164234b535c9e5791c98748698cfda8cd886b9be4aa4e9af2e38c31515b7d046c) 
shows Act's throughput is 20 times better than of Spring-boot in simple case

## Project status

* Current stable version: 1.0.0

## Install

Add the following dependency into your `pom.xml` file

```xml
     
       org.actframework 
       act 
       [1.0.0, 2.0.0) 
     
```

Add the following snippet into your `pom.xml` file if you want to get SNAPSHOT version:

```xml
   
     org.sonatype.oss 
     oss-parent 
     7 
   
```

## Features

* **A full stack MVC framework**
    * Actframework is **NOT** a servlet framework. Act app does not run in a servlet container. Instead
      it run as an independent Java application and it starts in seconds

* **Unbeatable development experience w/ great performance**
    * Never restart your app when you are developing. Act's dev mode provides hot reloading
      feature makes it the dream of every Java web app developer. Check out 
      [this 3 mins video](http://u.720life.cn/g/2bc656cc69a0e9056dae2ced9f817b904482df030ded26d1cdde0a20fff90c40df476921b005aeba042dcf46cfd8d1e2) and feel it!
    * According to [this 3rd party benchmark](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046feed511effb29e3bd3511d60221fe82164234b535c9e5791c98748698cfda8cd886b9be4aa4e9af2e38c31515b7d046c)
      Act beats most Java web framework on the market. In simple case Act can be 20 times faster than Springboot

* **Fully JSR330 Dependency Injection support**
    * ActFramework's DI support is built on top of [Genie](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046882c51494a8300a89c86137da35ede0717e40320185990229b32bcc080c18ccf), a lightweight
      yet [fast](http://u.720life.cn/g/54145d0471d91890860f7f8463c030461ca6e14842a4cb8a03fc5363e120ae7d609c0798ddcf95063db25bb4d75d2ab8) JSR330 implementation.
    * Benefit from Act's powerful class scan feature, it does not require the user to create injector from 
      modules (as the usually way you use Guice). Declare your module and your binding is automatically registered

* **Superb SPA/Mobile app support**
    * [Awesome JSON/RESTful support](http://u.720life.cn/g/2bc656cc69a0e9056dae2ced9f817b904482df030ded26d1cdde0a20fff90c40e606afeedee226f7cc63d7288f3922fe)
    * [Built-in CORS support](http://u.720life.cn/g/b0e7e73ba78cb53e5b431bb90a04f8492dc91535039ca2d432bfb3f578125ebb3f850147704dc89078a263afc6a224b87b26ae6ecdcf1cb958ed9bbd9c15648a)
    * [Session/Header mapping](http://u.720life.cn/g/b0e7e73ba78cb53e5b431bb90a04f8492dc91535039ca2d432bfb3f578125ebb722157a199f78e19fd30c107e49d22b7dd74c1511e4a08e419a1b9cf6a7106a6) so you are not limited to cookie

* **Uncompromising Security**
    * Session cookie is secure and http only, payload is signed and encrypted (optionally)
    * [Enable CSRF prevention with just one configuration item](http://u.720life.cn/g/b0e7e73ba78cb53e5b431bb90a04f8492dc91535039ca2d432bfb3f578125ebb5b82d51a570ae7dfef4e8e1f7bf64a0952f4bbd77e115bb52f1ae46fb6eb0c90)
    * XSS prevention: the default Rythm engine [escape variable output](http://u.720life.cn/g/3135f96ff32c5e2aa85c99269a79d0bef64e73d9068029dabb291d28ccb471ad91a2eb9ca42f46e1c1a3318e8678711c04e392db06e326bb95e68f916ac0801af186542928036fa0d64e77e5027c8414) by default
    * Implementing your authentication/authorisation/accounting framework using [AAA plugin](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304629395136f69a5bb025645a8e2ad3860f1fe8ddff82e3ebfd09dd2e40e88f04be)

* **Annotation aware but not annotation stack** 
    * Annotation is one of the tool ActFramework used to increase expressiveness. However 
      we do not appreciate [crazy annotation stacked code](http://u.720life.cn/g/1e37554b1e0fecefed542bca0199e2745acd0202c0de541f23cf016273f25371). 
      Instead we make the code to express the intention in a natural way and save 
      the use of annotation whenever possible.
      
      For example, for the following SpringMVC code:
      ```java
      @RequestMapping(value="/user/{userId}/invoices", method = RequestMethod.GET)
      public List listUsersInvoices(
        @PathVariable("userId") int user,
        @RequestParam(value = "date", required = false) Date dateOrNull) {
          ...
      }
      ```
      The corresponding ActFramework app code is:
      ```java
      @GetAction("/user/{user}/invoices")
      public List listUsersInvoices(int user, Date date) {
        ...
      }
      ```

* **Multi-environment configuration**
    * ActFramework supports the concept of `profile` which allows you to organize your configurations 
      in different environment (defined by profile) easily. Take a look at the following 
      configurations from one of our real project:
    
      ```text
        resources
        ├── conf
        │   ├── common
        │   │   ├── app.properties
        │   │   ├── db.properties
        │   │   ├── mail.properties
        │   │   ├── payment.properties
        │   │   └── social.properties
        │   ├── local-no-ui
        │   │   ├── app.properties
        │   │   ├── db.properties
        │   │   └── port.properties
        │   ├── local-sit
        │   │   └── app.properties
        │   ├── local-ui
        │   │   ├── app.properties
        │   │   └── db.properties
        │   ├── sit
        │   │   ├── app.properties
        │   │   └── db.properties
        │   └── uat
        ...
      ```
    Suppose on your UAT server, you start the application with JVM option `-Dprofile=uat`,
    ActFramework will load the configuration in the following sequence:
        1. Read all `.properties` files in the `/resources/conf/common` dir
        2. Read all `.properties` files in the `/resources/conf/uat` dir
    
    This way ActFramework use the configuration items defined in `uat` profile to overwrite 
    the same items defined in `common` profile. The common items that are not overwritten 
    still effective.

* **[Simple yet powerful database support](http://u.720life.cn/g/b0e7e73ba78cb53e5b431bb90a04f8495b99f23c4781533006fd0d6f903029fb16a8d796baf9168c64b8ae7b58e72ff7)**
    * [Multiple database support built in](http://u.720life.cn/g/b0e7e73ba78cb53e5b431bb90a04f849feab210f4298b27f6cc731ae7e5341027071d5c16496e26ff67db23306f92bb1)

* **[Powerful view architecture with multiple render engine support](http://u.720life.cn/g/b0e7e73ba78cb53e5b431bb90a04f84923647bf0557c275cc5bd7395ce9600860fe6c4fe96c9a62304a772c3811f43dc)**

* **Commonly used tools**
    * [Sending email](http://u.720life.cn/g/b0e7e73ba78cb53e5b431bb90a04f849276a42a1c5662f5c7a86afb9966f58580e4e8a77ffc293e0ec5e3f188b5c9966)
    * [Schedule jobs](http://u.720life.cn/g/b0e7e73ba78cb53e5b431bb90a04f849b425918df7dd07134f4a6a12c9188128)
    * [Event handling and dispatching](http://u.720life.cn/g/b0e7e73ba78cb53e5b431bb90a04f84951105f21c8f6616731d8d92797eff76f25799929f1e028bd364719ba5b236de9)

## Sample code

### A HelloWorld app

```java
package demo.helloworld;

import act.Act;
import act.Version;
import org.osgl.mvc.annotation.GetAction;

public class HelloWorldApp {

    @GetAction
    public String sayHello() {
        return "Hello World!";
    }

    public static void main(String[] args) throws Exception {
        Act.start("Hello World", Version.appVersion(), HelloWorldApp.class);
    }

}
```

See [this 7 mins video on how to create HelloWorld in Eclipse from scratch](http://u.720life.cn/g/2bc656cc69a0e9056dae2ced9f817b904482df030ded26d1cdde0a20fff90c40fa84d861787916f4575da680328f586c).
or [for users without youtube access](http://u.720life.cn/g/b504d8e64bec8ef0aa8bdfd5e05501c8583c0887f2d941bcee25876184ddaa9a3d919202cf6ffa60a9b649f1a9e36860)

### A full RESTful service

```java
package demo.rest;

import act.controller.Controller;
import act.db.morphia.MorphiaAdaptiveRecord;
import act.db.morphia.MorphiaDao;
import org.mongodb.morphia.annotations.Entity;
import org.osgl.mvc.annotation.*;

import java.util.Map;

import static act.controller.Controller.Util.notFoundIfNull;

@Entity("user")
public class User extends MorphiaAdaptiveRecord  {

    @Controller("user")
    public static class Service extends MorphiaDao  {

        @PostAction
        public User create(User user) {
            return save(user);
        }

        @GetAction
        public Iterable  list() {
            return findAll();
        }

        @GetAction("{id}")
        public User show(String id, Map  data) {
            return findById(id);
        }

        @PutAction("{id}")
        public User update(String id, Map  data) {
            User user = findById(id);
            notFoundIfNull(user);
            user.mergeValues(data);
            return save(user);
        }

        @DeleteAction("{id}")
        public void delete(String id) {
            deleteById(id);
        }
    }

    public static void main(String[] args) throws Exception {
        Act.start("RESTful Demo", Version.appVersion(), User.class);
    }

}
```

See [this 1 hour video on RESTful support](http://u.720life.cn/g/2bc656cc69a0e9056dae2ced9f817b904482df030ded26d1cdde0a20fff90c40e606afeedee226f7cc63d7288f3922fe) 
or [for user without youtube access](http://u.720life.cn/g/b504d8e64bec8ef0aa8bdfd5e05501c8583c0887f2d941bcee25876184ddaa9a9596f04b665a22c5592d3c53c97c5a80)


See [this 7 mins video to understand more about AdaptiveRecord](http://u.720life.cn/g/2bc656cc69a0e9056dae2ced9f817b904482df030ded26d1cdde0a20fff90c4042806bf20e0ddb6f62c7e00bc1153a39)
or [for user without youtube access](http://u.720life.cn/g/b504d8e64bec8ef0aa8bdfd5e05501c8583c0887f2d941bcee25876184ddaa9a672de66307304804aeb86e5b104b2e7b)

## Background

I love PlayFramework v1.x because it is simple, clear and expressive. It brought us a completely different experience 
in web development with Java. However I don't totally agree with where Play 2.X is heading for, and it looks like I am 
not the only person with the concern as per this 
[open letter to Play Framework Developers](http://u.720life.cn/g/941693b557d072bb769494a6a61fcd973a685fc0f6ba8ea5cb0fe2f7b665d334f44a95261780ebf38fdf66128ce9ad5f0efbf6e39a50a018599f283a6cfa8931847fccce170e371726137cc8f3382228). 

I [have thought of](http://u.720life.cn/g/fb656d09e9c6eb134c4a198b23c527946747d1fea18cb30fa9b490fc25e14b3bf7669bb4cf69c01cbf20f3a291b0db97a792dcdaa5f2ef5a909ecbcce1e9840be404265d331da79de2ff2242bc289857b08619e568758b5f4b0137e270a4384c) rolling out 
something that could follow the road paved by Play 1.x, something that is simple, clear, expressive and Java 
(specifically) developer friendly. About one and half year after that I decide I could start the project seriously, 
and now another one and half year passed by, I've got this ACT framework in a relatively good shape.

Happy coding!



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e34cfd6822e2b7b77b90d441f27d72eb0af332dbf687614a93c8a215fc7d1ecdbbc38a48020dbc306c05349cd8be8f509)