
# ApiBoot
[![Maven Central](https://img.shields.io/maven-central/v/org.minbox.framework/api-boot.svg?label=Maven%20Central)](https://search.maven.org/search?q=g:%22org.minbox.framework%22%20AND%20a:%22api-boot%22) [![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://github.com/weibocom/motan/blob/master/LICENSE) ![](https://img.shields.io/badge/JDK-1.8+-green.svg) ![](https://img.shields.io/badge/SpringBoot-1.5+_2.0+-green.svg)

`ApiBoot`是一款基于`SpringBoot1.x`、`SpringBoot2.x`的接口服务集成基础框架，内部提供了框架的封装集成，让接口开发者完成开箱即用，不再为搭建接口框架而犯愁，从而极大的提高开发效率。
通过在我的`SpringBoot`系列教程中得到的学习者的反馈，才决定来封装一套对应我文章的基础框架，`ApiBoot`内的每一个框架的具体讲解都在文章内进行了详细说明，如果有不明白的可以通过如下途径访问我的文章：

- [我的博客 - 恒宇少年De成长之路](http://u.720life.cn/g/95f6eb6c58370f2034ed070bc34738ed978c2195491011e0133395d7d63270f1)
- [我的简书](http://u.720life.cn/g/8a0e6e781ca1335d5641e0f9d5e96ab9030daa31ff39823a253d786055d03a90f39b573ed9ad3d9bdcf6fb2ac0617737)

## 主要功能

- **服务资源安全** ：通过整合`SpringSecurity` + `Oauth2`来完成接口服务的安全性，安全拦截路径内的请求必须携带`请求令牌`才可以访问到资源内容，资源内容可配置指定身份、权限访问。
- **服务授权认证中心**：服务授权以及认证是由`Oauth2`来担任，通过`password`授权模式获取`请求令牌`后访问资源服务，一个配置即可开启`Jwt`格式化`AccessToken`
- **文档自动生成**：通过集成`Swagger2`来完成文档的侵入式生成，侵入式文档后期会被替代，`ApiBoot Security Oauth`已默认排除`swagger2`相关的资源路径。
- **返回JSON格式化**：使用阿里巴巴的`FastJson`来完成返回`Json`字符串的格式化，自动扫描装载自定义的`ValueFilter`实现类，用于自定义返回格式化。
- **数据库ORM框架**：`mybatis-enhance`是一款由我开源的数据库持久化框架，基于`mybatis`进行封装编写，可以完成动态查询数据，语法与`SQL`语法几乎一致，内置常用方法提供直接调用，支持方法命名规则查询，一个接口方法就可以自动完成查询，不再编写`SQL`语句。
- **动态数据源**：完成项目的多数据源配置、内部集成`druid`、`HikariCP`数据源实现方式，配置主从数据源、多数据库类型数据源、多种数据源实现方式集成。
- **自动分页插件**：`mybatis-pageable`是一款由我开源的自动化分页插件，直接摆脱编写`分页代码`，仅仅需要传递的分页参数就可以自动进行查询，目前支持主流的**12**种数据库。
- **代码生成插件**：`code-builder`是一款由我开源的代码生成插件，直接摆脱实体类的生成，支持自定义`freemarker`模板来完成自定义生成类文件，比如：`Service`、`Controller`、`Mapper`等。
- **七牛云资源处理**：集成七牛云提供的SDK来完成文件的上传、下载等方法实现，开箱即用。
- **阿里云OSS资源处理**：集成阿里云OSS提供的SDK来完成文件的上传、下载等方法实现，开箱即用。
- **阿里云短信**：集成阿里云提供的SMS服务，简单配置即可完成短信发送，覆盖全球的短信服务，友好、高效、智能的互联化通讯能力，帮助企业迅速搭建客户触达通道。

更多功能请参考 [更多功能列表](http://u.720life.cn/g/54145d0471d91890860f7f8463c030460ec3b565d2d40b474523466e878645a1f7a56e19372220343b61b2c9b05c6e1ba6d62d8088bc80c85a98ac8aa41cb8d5db60dd89ac10cb27cf012af0d5e5fa3399d27f796d9423456c65cf82a0706d71)

## 组件

- **[Spring Security](http://u.720life.cn/g/a8126de486174bbac1604ce886fda0d3c11ff9cd2c983439d13aa7ecb66a59175df0afea6546a9d9d82b1e4065da984bc06e8478deedfedda3177c8b066e617d40a84305cc806a31e422a99aca7ed2d0)**：Spring提供的安全框架，Spring家族式的设计，无缝整合SpringBoot
- **[OAuth2](http://u.720life.cn/g/6148a95d5f5fdb39059f69b52d12127e73a2afe3cabe889c95580760499a57d6)**：OAuth是一个网络授权的标准。
- **[JWT](http://u.720life.cn/g/29b44050880331fd3d2682a984e1a32d)**：JSON Web Token是目前流行的跨域认证解决方案，用于格式化OAuth2生成的Token。
- **[Quartz](http://u.720life.cn/g/beb95a72271892e3173f0dad802e5ddf2956fdb02d87d3a76552cdc447c2fba3)**：分布式定时任务调度框架
- **[Swagger2](http://u.720life.cn/g/144fc7dac4f8956d4599e1fe5c1bbcf883c55dd9d71a04eb7bc64e107270e142)**：Swagger是一款API文档生成工具，自动扫描代码进行生成可运行测试的文档。
- **[Mybatis Enhance](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304624e3dce48c28cd379b25fbe68948122e37764ac9bc065377d1299881c9226b55)**：`Enhance`是对于原生的`MyBatis`的增强编写，不影响任何原生的使用，使用后完全替代`mybatis-core`、`mybatis-spring`以及`mybatis-spring-boot-starter`，可以使用`SpringBoot`配置文件的形式进行配置相关的内容，尽可能强大的方便快速的集成`MyBatis`。
- **[DataSource Switch](http://u.720life.cn/g/54145d0471d91890860f7f8463c030460ec3b565d2d40b474523466e878645a1f7a56e19372220343b61b2c9b05c6e1ba6d62d8088bc80c85a98ac8aa41cb8d5540fa3155383ac6b836e41adee0a6b42a119037f95132471c232a8ef85d5c000f5eb085217ad8115042fbc66f95da0f08e4f6a50452bbc86c93ccb3f9a28a4c7)**：一款多数据源自动切换框架，可配置多种数据库类型数据源集成、主从数据源配置。
- **[Mybatis Pageable](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304624e3dce48c28cd379b25fbe68948122ef61a06a87032265ff2daf3e05d32d468)**：`MyBatis-Pageable`是一款自动化分页的插件，基于`MyBatis`内部的插件`Interceptor`拦截器编写完成，拦截`Executor.query`的两个重载方法计算出分页的信息以及根据配置的数据库`Dialect`自动执行不同的查询语句完成总数量的统计。
- **[Code Builder](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304619557ef3c07a4ef7507c3783b11aa6db61220c3a14909a36abf5f866d97f5c4d)**：`code-builder`是一款代码生成`maven mojo`插件，通过简单的配置就可以完成数据库内`Table`转换`Entity`或者其他实体类，想怎么生成完全根据你的个人业务逻辑，`code-builder`尽可能的完善的提供数据库内的一些定义的信息，让你更方便更灵活的来生成`Java`文件。

更多组件请参考[更多集成组件](http://u.720life.cn/g/54145d0471d91890860f7f8463c030460ec3b565d2d40b474523466e878645a1f7a56e19372220343b61b2c9b05c6e1ba6d62d8088bc80c85a98ac8aa41cb8d5db60dd89ac10cb27cf012af0d5e5fa3399d27f796d9423456c65cf82a0706d71)

## 怎么使用？

### 添加版本依赖

在使用`ApiBoot`时需要再`pom.xml`文件内的`dependencyManagement`标签内添加如下配置：

```xml
 
   
     
       org.minbox.framework 
       api-boot-dependencies 
       2.0.5.RELEASE 
       pom 
       import 
     
   
 
```

由于`ApiBoot`内后期规划集成的内容比较多，所以根据了`SpringBoot`的版本规划来进行了管理维护，这样在添加使用`ApiBoot`的依赖时就不再需要添加`版本号`，统一交由`api-boot-dependencies`进行管理。

> 注意：该版本默认添加了`spring-boot-dependencies`依赖。

## 使用Demo

`ApiBoot`会为每一个依赖提供一个演示代码集成子项目，都在`api-boot-samples`项目下，为了更好地解释`ApiBoot`的每一个依赖功能，恒宇少年会在每一个`sample`下添加当前项目的`readme`进行详细介绍。

Demo列表：

- [ApiBoot Security Oauth](http://u.720life.cn/g/54145d0471d91890860f7f8463c030460ec3b565d2d40b474523466e878645a1f7a56e19372220343b61b2c9b05c6e1b009f2a1dc089eb7504418375d80bfbfa1db1431f6f45f602e7eb745184470b0a17ecdd0c2c0e9c897c9ada19926569121054168a1b912ea0357dd7754162fbbe)
- [ApiBoot Swagger](http://u.720life.cn/g/54145d0471d91890860f7f8463c030460ec3b565d2d40b474523466e878645a1f7a56e19372220343b61b2c9b05c6e1b009f2a1dc089eb7504418375d80bfbfa1db1431f6f45f602e7eb745184470b0a5333a20ec5f59ce277110029c50c52c8)
- [ApiBoot Http Converter](http://u.720life.cn/g/54145d0471d91890860f7f8463c030460ec3b565d2d40b474523466e878645a1f7a56e19372220343b61b2c9b05c6e1b009f2a1dc089eb7504418375d80bfbfa1db1431f6f45f602e7eb745184470b0a4ada7b57b3fcc0518844ab8f24c0e420)
- [ApiBoot Alibaba OSS](http://u.720life.cn/g/54145d0471d91890860f7f8463c030460ec3b565d2d40b474523466e878645a1f7a56e19372220343b61b2c9b05c6e1b009f2a1dc089eb7504418375d80bfbfa1db1431f6f45f602e7eb745184470b0aa002a230307d027c2a1b4b78eda7804d)
- [ApiBoot Alibaba SMS](http://u.720life.cn/g/54145d0471d91890860f7f8463c030460ec3b565d2d40b474523466e878645a1f7a56e19372220343b61b2c9b05c6e1b009f2a1dc089eb7504418375d80bfbfa1db1431f6f45f602e7eb745184470b0a9db9f9de19898a3a317bde8c4048e579)
- [ApiBoot Quartz](http://u.720life.cn/g/54145d0471d91890860f7f8463c030460ec3b565d2d40b474523466e878645a1f7a56e19372220343b61b2c9b05c6e1b009f2a1dc089eb7504418375d80bfbfa1db1431f6f45f602e7eb745184470b0a78d8076f660c82daf6888c353c302d3b)
- [ApiBoot DataSource Switch](http://u.720life.cn/g/54145d0471d91890860f7f8463c030460ec3b565d2d40b474523466e878645a1f7a56e19372220343b61b2c9b05c6e1b009f2a1dc089eb7504418375d80bfbfa1db1431f6f45f602e7eb745184470b0abab5de7cb7edd9ad9cab3e092c9c6765e844febf22cf133927cd8d97b3f93fe3)
- [ApiBoot Resource Load](http://u.720life.cn/g/54145d0471d91890860f7f8463c030460ec3b565d2d40b474523466e878645a1f7a56e19372220343b61b2c9b05c6e1b009f2a1dc089eb7504418375d80bfbfa1db1431f6f45f602e7eb745184470b0ae117dca359319dfa98f03ce922894702)
- [ApiBoot Message Push](http://u.720life.cn/g/54145d0471d91890860f7f8463c030460ec3b565d2d40b474523466e878645a1f7a56e19372220343b61b2c9b05c6e1b009f2a1dc089eb7504418375d80bfbfa1db1431f6f45f602e7eb745184470b0afe5cdb5edd45e51f5011624d60462549)

## 更新日志

`ApiBoot`每一次发版都会有相应的更新日志，点击访问[更新日志wiki]( )

## 版本管理规范

项目的版本号格式为 x.x.x 的形式，其中 x 的数值类型为数字，从 0 开始取值，且不限于 0~9 这个范围。

- SpringBoot1.x版本对应ApiBoot版本1.x.x
- SpringBoot2.x版本对应ApiBoot版本2.x.x

集成新的第三方框架为小版本更新，对应修改第三位版本数值，如：2.0.1 -> 2.0.2

## 开源交流

### 社区交流

#### 恒宇少年邮件

[jnyuqy@gmail.com](mailto:jnyuqy@gmail.com)

#### 恒宇少年微信

yuqiyu999

#### 钉钉群

![](https://github.com/hengboy/api-boot/blob/master/dingding_group.JPG)

### 项目结构

```
. api-boot
├── api-boot-projects
│   ├── api-boot-autoconfigure
│   ├── api-boot-common
│   ├── api-boot-dependencies
│   ├── api-boot-parent
│   └── api-boot-starters
├── api-boot-samples
│   ├── api-boot-sample-alibaba-oss
│   ├── api-boot-sample-alibaba-sms
│   ├── api-boot-sample-http-converter
│   ├── api-boot-sample-datasource-switch
│   ├── api-boot-sample-security-oauth-jwt
│   ├── api-boot-sample-quartz    
│   └── api-boot-sample-swagger
└── tools
```

### 开源许可

`ApiBoot`采用`Apache2`开源许可。



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ea24ceaebf3f5cbe329b1f8dee1478441f1c7225c16a62ca4369becc943ed424aa1aca35213c7dc0d013e24e1576269b6)