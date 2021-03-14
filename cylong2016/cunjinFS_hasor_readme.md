# Hasor

&emsp;&emsp; 面向生产环境而设计的 Java 应用开发框架。它的核心设计目标是提供一个简单的交互接口给开发者，开发者可以在此基础上灵活的构建自己的应用程序。无论是应用类程序还是框架类工具 Hasor 都会给予最有力的支持。

&emsp;&emsp; 区别于其它框架的是 Hasor 有着自己一套完整的扩展体系。无论您是一般的应用工程，还是开发工具框架类项目。Hasor都会是一个强有力的基石。

----------
## 设计思想
&emsp;&emsp;Hasor 的设计思想是“ 微内核+插件 ”的方式。严格意义来说所有 Hasor 子框架都属于 Hasor 插件范畴，因此构筑成 Hasor 核心的只有 hasor-core。

### 特点
- “微内核+插件” 简单、小巧、功能强大、使用简单。
- COC原则的最佳实践，‘零’配置文件。
- 合理的整体架构规划，即是小框架也是大平台。
- 各部分全部独立，按需使用，绝不臃肿。
- 体积小，无依赖。
- 最低要求环境jdk8

### 技术体系
![avatar](https://www.hasor.net/web/_images/CC2_403A_3BD5_D581.png)

- Core 具备 Aop 并兼容 JSR-330 的Bean容器框架（[详细..](hasor-core/README.md)）
  - 提供一个支持IoC、Aop的Bean容器。
  - 基于 Module + ApiBinder 机制提供统一的插件入口。
  - 特色的 Xml 解析器。让你无需二次开发无需配置，直接读取自定义xml配置文件。
  - 支持 JSR-330
- DB 是一款基于jdbc的数据库框架，提供了JDBC操作和完整事务管理能力（[详细..](hasor-db/README.md)）
  - 提供 JDBC 操作接口 90% 兼容 SpringJDBC。
  - 与 Spring 一样，提供七种事务传播属性的控制。
  - 支持多种事务控制方式包括：手动事务控制、注解式声明事务、TransactionTemplate模板事务。
  - 支持多数据源（不支持分布式事务）
- RSF 分布式 RPC 服务框架（[详细..](hasor-rsf/README.md)）
  - 支持容灾、负载均衡、集群；支持动态发布、卸载
  - 支持服务分组、分版本
  - 多种调用方式：点对点、分布式轮询、泛化调用、同步、异步、回调、接口代理。
  - 支持虚拟机房、隐式传参、服务路由、Telnet 等高级功能。
- Web 轻量化 Web MVC 框架（[详细..](hasor-web/README.md)）
  - 提供 RESTful 风格的 mvc 开发方式。
  - 提供请求验证接口、验证支持场景化。
  - 开放的模版渲染接口，支持各种类型的模版引擎。
  - 内置文件上传组件，无需引入任何jar包。
- tConsole 专注基于 Telnet 命令行交互框架（[详细..](hasor-tconsole/README.md)）
  - 支持监听本地端口提供 Telnet 交互的界面。
  - 支持基于标准输入输出构建交互控制台的能力。
  - 利用 tConsole 可以轻松构建命令工具包。
- DataQL 服务聚合查询引擎（[详细..](hasor-dataql/README.md)）
  - 层次结构：可以产出具有数据的层次结构的查询结果。
  - 弱类型：不要求声明任何形式的类型结构。
  - 轻逻辑：仅支持表达式、取值、条件分支、lambda和函数。不支持赋值和循环
  - 编译运行：查询的执行是基于编译结果的。
  - 扩展代码片段：允许 DataQL 查询中混合其它语言的语句。

----------
### 发展状况

&emsp;&emsp; Hasor起源于2012年，当时作为  研发中心下各项目的基础手脚架。

&emsp;&emsp; 2015年7月3日，1.0.0版本发布。确立了“微内核+插件”发展策略。

&emsp;&emsp; 2016年8月18日，2.4.3版本发布，同时开始孕育全新的子项目 RSF。由此 Hasor 开始向分布式领域发展。

&emsp;&emsp; 2017年2月21日，RSF 被并入 Hasor 体系，同年 DataQL 问世。

&emsp;&emsp; 2020年2月21日，4.0.7 最稳定的版本问世。这个版本中几乎所有功的代码都被重新 Review 并重新评估每个模块的设计是否需要更新。

----------
### 最低要求
* jdk8
* servlet 2.3

----------
### 相关连接
* QQ群：193943114
* [![License](https://img.shields.io/badge/license-Apache%202-4EB1BA.svg)](https://www.apache.org/licenses/LICENSE-2.0.html)
[![Maven Central](https://maven-badges.herokuapp.com/maven-central/net.hasor/hasor-core/badge.svg)](https://maven-badges.herokuapp.com/maven-central/net.hasor/hasor-core)
[![Build Status](https://travis-ci.org/zycgit/hasor.svg?branch=master)](https://travis-ci.org/zycgit/hasor)
[![Build Status](https://travis-ci.org/zycgit/hasor.svg?branch=dev)](https://travis-ci.org/zycgit/hasor)
* Docs : [http://www.hasor.net/](http://u.720life.cn/g/f705dfc389dec58b30f7e61ae57c368d46623e958959f78f3a16e55ec8270486)



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ec9c5a5ba61c4d13302a7e0201b4ba81b1ea4b5c93147f08669a8d1b8adf60855b7093eb9531894b90cd6c6be0a62cb2a)