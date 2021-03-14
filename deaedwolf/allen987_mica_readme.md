## mica（云母）
[![Build Status](https://www.travis-ci.org/lets-mica/mica.svg?branch=master)](https://www.travis-ci.org/lets-mica/mica)
![JAVA 8](https://img.shields.io/badge/JDK-1.8+-brightgreen.svg)
[![Mica Maven release](https://img.shields.io/nexus/r/https/oss.sonatype.org/net.dreamlu/mica-bom.svg?style=flat-square)](https://mvnrepository.com/artifact/net.dreamlu/mica-bom)
[![Mica maven snapshots](https://img.shields.io/nexus/s/https/oss.sonatype.org/net.dreamlu/mica-bom.svg?style=flat-square)](https://oss.sonatype.org/content/repositories/snapshots/net/dreamlu/mica-bom)
[![Codacy Badge](https://api.codacy.com/project/badge/Grade/eadcb54f2ec14f31b8abf3ab13ad2d4d)](https://app.codacy.com/app/ChunMengLu/mica?utm_source=github.com&utm_medium=referral&utm_content=lets-mica/mica&utm_campaign=Badge_Grade_Settings)
[![GitHub](https://img.shields.io/github/license/lets-mica/mica.svg?style=flat-square)](https://github.com/lets-mica/mica/blob/master/LICENSE)

`Mica`，Spring Cloud 微服务开发核心包，支持 `web` 和 `webflux`。

`注意`：`snapshots` 版本会及时响应，修复最新的 `bug` 或者必要的需求。

| 依赖         | 版本              |
| ------------ | ----------------- |
| Spring | 5.x |
| Spring Boot  | 2.1.x             |
| Spring Cloud | Greenwich 版 |

![犬夜叉-云母](docs/img/mica-001.jpeg)

想要了解更多可加入【如梦技术】QQ 群：`479710041`。

## 模块划分
### mica-auto
1. 编译期生成 `spring.factories`。
2. 编译期生成 `spring-devtools.properties`。
3. 编译期生成 `FeignClient` 信息到 `spring.factories` 中，供 `mica-pro` 中完成 `Feign` 自动化配置。

`源码地址`：[https://gitee.com/596392912/mica-auto](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6edd9cc4708a4f3db68bdd558caedb032fdfc5f3aa488ebe5957bdc31cfd95328f)

### mica-core
- 常用工具包，基于 `Spring-core` 扩展增强，无其他依赖。
- 增强 cglib Bean copy，高性能（接近直接 get set），支持链式 bean，支持类型转换 。
- `$` 工具类快捷方法，不用再记忆到底有哪些工具类。
- 统一消息返回体，封装得更加好用。
- Jaskson Read Write HttpMessageConverter，分读写的消息转换器。
- Spring 枚举转换器，规则同 Jackson。

### mica-http
- `mica-http` 是 `okhttp` 的封装，Fluent 语法的 http 工具包，语法参考 HttpClient Fluent API。

### mica-launcher
- 项目启动器
- 启动信息打印
- 系统环境处理
- spi 扩展

### mica-boot
- 支持 `Spring boot web` 和 `Spring boot webflux`。
- 异步配置。
- 异常处理，未知异常发送 Event 事件，方便监听收集。
- swagger 自动化配置，加入 jar 包即可。
- jackson 配置。
- 文件上传配置。
- 文件下载，支持断点续传，浏览器兼容好。
- 请求日志打印，方便开发。
- url 版本号和 header 版本处理。

### mica-boot-test
- 方便 mica-boot 测试，注入 mica-launcher 中注入的参数。

### mica-log4j2
- mica log4j 配置。
- 基于 disruptor 异步日志，高性能。
- 非开发环境将 System.out 和 err 写入 log。

### mica-captcha
- 验证码，支持 `webflux` 和 `serlvet`。

### mica-social
- 第三方登录组件

### mica-cloud
- Feign 自动降级、header 透传、版本处理，结合 `mica-auto` 自动化配置。
- RestTemplate 自动配置，基于 okhttp 增强，添加请求日志和 Header 传递。
- hystrix 熔断器增强，支持 header 透传、当前用户获取和透传。
- Apollo Properties 配置刷新。

### mica-plus-error-catch
- 未知异常收集到 spring-cloud-stream 中，方便统一处理。

### mica-plus-redis
- redis cache name # 自动配置超时时间。

### mica-plus-mongo
- mongo 复杂 tree 和 jsonNode 转换处理。

### mica-plus-swagger
- swagger 和 swagger-bootstrap-ui 依赖。

### mica-plus-ribbon
- 【优先级最高】ip 相同的服务（方便本地多服务联调）。
- 可设置选择的 ip 或者 ip 段，例如：`172.21.0.*`、`172.21.0.8*`。
- 可设定 `tag`，用于灰度，匹配：`nacos.discovery.metadata.tag`。

### mica-plus-social
- `mica-social` 自动化配置。

## 已知问题
lombok 生成的 method 问题：https://github.com/rzwitserloot/lombok/issues/1861

对于 xX 类属性名，第一个小写，第二个大写的 bean 属性名，Map -> Bean 或 Bean -> Map 存在问题。

不打算做兼容，待 lombok 新版修复。

## 协议
![LGPL v3](docs/img/lgplv3-147x51.png) 

## 用户权益
允许以引入不改源码的形式免费用于学习、毕设、公司项目、私活等。

特殊情况修改代码，但仍然想闭源需经过作者同意。

参考请注明：参考自 mica：https://github.com/lets-mica/mica

`注意`：若禁止条款被发现有权追讨 **19999** 的授权费。

## 授权用户（最佳实践）
* `pigx` 宇宙最强微服务（架构师必备）：https://pig4cloud.com
* `bladex` 完整的线上解决方案（企业生产必备）：https://bladex.vip

## 相关链接
* `示例项目`：[https://github.com/lets-mica/mica-example](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046be453ee6cca485b63092180979f2b028974b1c7b19eb6f058ae573028e9e2944)
* mica 源码 Github：[https://github.com/lets-mica](http://u.720life.cn/g/54145d0471d91890860f7f8463c030469700d62ac59d3e6d24ce9b3ac7258fe6)
* mica 源码 Gitee（码云）：[https://gitee.com/596392912/mica](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6edd9cc4708a4f3db68bdd558caedb032f)
* 文档地址（官网）：[https://www.dreamlu.net/docs/](http://u.720life.cn/g/1223673b752970deb6582301422733a66f2dc65917008f2b9d35247450152910)
* 文档地址（语雀-可关注订阅）：[https://www.yuque.com/dreamlu/mica](http://u.720life.cn/g/794be49a28e6f6b6aa755de579be43d947827ed69abb2b660d8206820cbcdb1e1c2694d30e66bda74e676284ee286ec4)

## 开源推荐
- `Avue` 一款基于 vue 可配置化的神奇框架：[https://gitee.com/smallweigit/avue](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e9a45ea68dd78dd93ab4ce0a12f91adcf597755959c1ecde8ac8b2591700d6b1d)
- `pig` 宇宙最强微服务（架构师必备）：[https://gitee.com/log4j/pig](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e003a98ff8124711bc8bb2a735eddd1c3)
- `SpringBlade` 完整的线上解决方案（企业开发必备）：[https://gitee.com/smallc/SpringBlade](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e3546460c0cd5dba4cbac39602ce9c18cfb9683eaf44923e5c878f4ad4056bdf6)
- `IJPay` 支付 SDK 让支付触手可及：[https://gitee.com/javen205/IJPay](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ef068ea679d97703e45f205b8f530ec5f)

## 鸣谢
感谢 `如梦技术VIP群` 小伙伴们的支持。

## 微信公众号

![如梦技术](docs/img/dreamlu-weixin.jpg)

精彩内容每日推荐！!


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e50b5e33af456bf03e89c7eef7b10a44e05dfc1bdb5bb0e257f02bd695117466c72ab299df61b474d24b0c6e125fdca80)