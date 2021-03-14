# kitty-cloud
Spring Cloud 架构搭建的开源社区技术网站


## 后端技术栈

**[Kitty](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304633eb701bc385e042cb647067ebc525653324f36ac4fb5ad9081cc1435100f265)**：Spring Cloud & Spring Cloud Alibaba 基础框架，内置了 Cat 监控，互联网公司落地 Spring Cloud 架构必备。

**[Spring Cloud](http://u.720life.cn/g/c6d1b26d763f49c99d62f7dd7e1f263d74791681f9785d83f6cd6c957366ad1dd6abd36b3d488c22bff8dcabd4ce747f)**：Spring 微服务全家桶。

**[Spring Cloud Alibaba](http://u.720life.cn/g/54145d0471d91890860f7f8463c030460e6a7dcd7c5d55e4e87daf4d62e47dcd06b31a84d9eaf8e80806caf9193fa975)**：致力于提供微服务开发的一站式解决方案。

**[Sentinel](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046c089fd6330326c1ada4902057b5192ed0b411e1038b68aabe61a75621963e3fe)**：把流量作为切入点，从流量控制、熔断降级、系统负载保护等多个维度保护服务的稳定性。

**[Nacos](http://u.720life.cn/g/54145d0471d91890860f7f8463c030464ab8bd4ffa2989824d7cb8e96d7b7c73)**：一个更易于构建云原生应用的动态服务发现、配置管理和服务管理平台。

**[Dubbo](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046034d0637ce610285d4f7df3b758b07af)**：Apache Dubbo™ 是一款高性能 Java RPC 框架。

**[Cat](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304652a6ce7ad73cc660b1bc2ebb38d26aae)**：基于 Java 开发的实时应用监控平台，为美团点评提供了全面的实时监控告警服务。

**[MyBatis-Plus](http://u.720life.cn/g/df1e7c2b9c31e9f2d40cc7686887d9ad7fbc646d1663eff27294c0fbb0c2e07f)**：MyBatis的增强版。

**[Spring Data MongoDB](http://u.720life.cn/g/c6d1b26d763f49c99d62f7dd7e1f263d74791681f9785d83f6cd6c957366ad1d284a934344406f8df21ac317734a4de4)**：Spring 中对MongoDB操作的客户端框架。

**[JetCache](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046ff66fd07c805edc7c5593f8eb0e5e22c44ee2abac7a082ff402030919e92d9b0)**：基于Java的缓存系统封装，提供统一的API和注解来简化缓存的使用。

**[ElasticSearch](http://u.720life.cn/g/54145d0471d91890860f7f8463c030466e836c5dd85610d86e6f01486f462e2c0d9e4b426066af1ff2b4626bce8b1132)**：ElasticSearch 是一个开源，分布式，RESTful搜索引擎。

## 核心功能

* 微服务架构（Spring Cloud & Spring Cloud Alibaba）
* 支持RPC/HTTP双协议（Dubbo和Feign远程调用）
* 分布式链路跟踪（Sleuth + ELK）
* 熔断限流（基于Sentinel的熔断限流）
* Cat监控（Mybatis, Feign, Dubbo, MongoDB, ElasticSearch等都有埋点监控）
* 全局幂等（基于redisson的分布式锁 + 注解 + 多级存储的幂等组件）
* 分布式ID分发（基于Leaf改造，扩展了RPC获取ID服务）
* 分布式任务调度（基于XXL-JOB的任务调度）
* MongoDB，ElasticSearch的使用（业务服务中使用）

## 项目文档

* 文档地址：[http://cxytiandi.com](http://u.720life.cn/g/16402775b42f20462ff8b28ac6055fa8f15f2337aae81140a5cfd55eb79e52724f1d27bd085827143af3bf8ac854efd2)

## 项目模块

* kitty-cloud-common：公共模块，通用的工具类
* kitty-cloud-user：用户服务
* kitty-cloud-article：文章服务
* kitty-cloud-comment：评论服务
* kitty-cloud-gateway：Web网关
* kitty-cloud-search：搜索服务
* kitty-cloud-job：定时任务
* 开发中。。。。。。

## 项目演示

请大家不要随便改变配置内容，想要实验的自己本地安装就可以了，多谢合作。

* Nacos控制台：[http://47.105.66.210:8848/nacos](http://u.720life.cn/g/a8bcf92563ea0f691512acaf43f95e41ff3dc2635e23e73c0ee8634890a4378b) nacos/nacos
* Cat控制台：[http://47.105.66.210:8080/cat](http://u.720life.cn/g/a8bcf92563ea0f691512acaf43f95e418af856866507d79294a932c390904c0e)
* Sentinel控制台：[http://47.105.66.210:8300](http://u.720life.cn/g/a8bcf92563ea0f691512acaf43f95e4102888756ad78e59c495f0337618dfc7a) sentinel/sentinel
* XXL-JOB控制台：[http://47.105.66.210:8010/xxl-job-admin/](http://u.720life.cn/g/a8bcf92563ea0f691512acaf43f95e41e9ae656e97916a4a6465ebfe69c0e8def8354fd0058d816f7435c0c286351a15) admin/123456

# 公众号

公众号 ***猿天地*** 会持续更新Kitty Cloud 和 微服务相关技术文章，请关注。技术交流群请加我微信jihuan900

![](doc/images/2685774-17a60e1ead7fd232.png)




 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e5ed80ca75ea832e97181cb61ca043c743d92bf5e0194b3d1aa81157fd9b4f828ab0df6796301e08bad7f68e0accd4c1a)