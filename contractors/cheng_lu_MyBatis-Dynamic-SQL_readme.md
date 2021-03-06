# MyBatis Dynamic SQL

[![Build Status](https://travis-ci.org/mybatis/mybatis-dynamic-sql.svg?branch=master)](https://travis-ci.org/mybatis/mybatis-dynamic-sql)
[![Coverage Status](https://coveralls.io/repos/github/mybatis/mybatis-dynamic-sql/badge.svg?branch=master)](https://coveralls.io/github/mybatis/mybatis-dynamic-sql?branch=master)
[![Maven central](https://maven-badges.herokuapp.com/maven-central/org.mybatis.dynamic-sql/mybatis-dynamic-sql/badge.svg)](https://maven-badges.herokuapp.com/maven-central/org.mybatis.dynamic-sql/mybatis-dynamic-sql)
[![Sonatype Nexus (Snapshots)](https://img.shields.io/nexus/s/https/oss.sonatype.org/org.mybatis.dynamic-sql/mybatis-dynamic-sql.svg)](https://oss.sonatype.org/content/repositories/snapshots/org/mybatis/dynamic-sql/mybatis-dynamic-sql/)
[![License](http://img.shields.io/:license-apache-brightgreen.svg)](http://www.apache.org/licenses/LICENSE-2.0.html)

## What Is This?
This library is a framework for generating dynamic SQL statements.  Think of it as a typesafe SQL templating library,
with additional support for MyBatis3 and Spring JDBC Templates.

The library will generate full DELETE, INSERT, SELECT, and UPDATE statements formatted for use by MyBatis or Spring.
The most common use case is to generate statements, and a matching set of parameters, that can be directly used
by MyBatis.  The library will also generate statements and parameter objects that are compatible with Spring JDBC
templates.

The library works by implementing an SQL-like DSL that creates an object containing a full SQL statement and any
parameters required for that statement.  The SQL statement object can be used directly by MyBatis as a parameter to a mapper method.

The library also contains extensions for Kotlin that enable an idiomatic Kotlin DSL.

See the following pages for further information:

| Page | Comments|
|------|---------|
|[Quick Start](src/site/markdown/docs/quickStart.md) | Shows a complete example of building code for this library |
|[MyBatis3 Support](src/site/markdown/docs/mybatis3.md) | Information about specialized support for [MyBatis3](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304603f7b0f3323829049382145887a1f0de7e86d76775999fb349e03d52e0388f60). The examples on this page are similar to the code generated by [MyBatis Generator](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304602d75ec6f7ef29bab0759c73f5fdf49997b16c203063ed2ad9d38fb1be612af0) |
|[Kotlin Support with MyBatis3](src/site/markdown/docs/kotlinMyBatis3.md) | Information about the Kotlin extensions and Kotlin DSL when using MyBatis3 as the runtime |
|[Spring Support](src/site/markdown/docs/spring.md) | Information about specialized support for Spring JDBC Templates |
|[Kotlin Support with Spring](src/site/markdown/docs/kotlinSpring.md) | Information about the Kotlin extensions and Kotlin DSL when using Spring JDBC Template as the runtime |
|[Spring Batch Support](src/site/markdown/docs/springBatch.md) | Information about specialized support for Spring Batch using the [MyBatis Spring Integration](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046e9022f6afe2c4fdd5b08a5686a5c8395cbb22b9e7ed13755c5d55416d598772b) |

## Requirements

The library has no dependencies.  Java 8 or higher is required.



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ef6e8d3c3d805aaae7d3146f475e5f9dbac55378f91dd30a504e23a59112f15f81fd5a283debd0c4ccf9ee1ef207ffa1c768bc3483bb38f868a5fc4d9be49331a)