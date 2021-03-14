> 很多天没有更新 由于一些事
>
> 自己也想明白了 嘴长在别人身上 做好自己就行
>
> 6月20 继续完善项目


---

## xbin-store
[![License](https://img.shields.io/badge/license-GPL-blue.svg)](LICENSE)
[![GitHub stars](https://img.shields.io/github/stars/xubinux/xbin-store.svg?style=social&label=Stars)](https://github.com/xubinux/xbin-store)[![GitHub forks](https://img.shields.io/github/forks/xubinux/xbin-store.svg?style=social&label=Fork)](https://github.com/xubinux/xbin-store)

模仿国内知名B2C网站,实现的一个分布式B2C商城

进群讨论 群 626068936 

Dubbox 版本:

* GitHub 地址 : https://github.com/xubinux/xbin-store
* OSChina 地址 : http://git.oschina.net/binu/xbin-store

Spring Cloud 版本:

* GitHub 地址 : https://github.com/xubinux/xbin-store-cloud
* OSChina 地址 : http://git.oschina.net/binu/xbin-store-cloud


使用技术:

* 后台
	* 使用`Spring Boot` 构建整个项目 去除 XML 配置
	* `Maven`构建项目
	* `Jenkins`作为持续集成
	* 采用`Dubbox`作为RPC框架
	* `kryo`序列化
	* 使用`Spring`+`Spring MVC`+`MyBatis`SSM框架
	* 数据库连接池使用`druid`
	* 数据库使用`MySQL`和`Redis`
	* 页面引擎采用 `Beetl`
	* 网页采用`freemarker`生成静态化页面
	* 存储采用`FastDFS`存储图片等文件
	* 采用`Solr`实现搜索服务
	* `Swagger2` 生成 RESTful Apis文档
	* 负载均衡使用`Nginx`、`keepalived`实现高可用
	* 采用`Spring Scheduled`做任务调度
	* 消息中间件采用`RabbitMQ`
	* 在分布式事务上则采用了[TCC](http://u.720life.cn/g/54145d0471d91890860f7f8463c030468b6bd99793f83abd7c131be7b49d49e2e1bd88e03c311d6356f3d596cb2be46a)解决订单支付方面时效性要求性高的分布式事务,可靠的消息服务则来解决如会计记录等时效性要求低的分布式事务.
* 前台
	* 采用基于[AdminLTE](http://u.720life.cn/g/54145d0471d91890860f7f8463c030469938d875cf47e5488f379f965eb2a0745e6b8f3c0029e0f6d8e8db173b9167bf)的[roncoo-adminLTE]https://github.com/roncoo/roncoo-adminLTE
	* AdminLTE集成太多Js这里就不一一列举了
	
## xbin-mobile 移动端
http://git.oschina.net/orangehs/xbin-mobile

> 目前由 orange 开发,有兴趣可以联系

## Pull Request
内容可以是优化、新功能、Bug修复等。

期待您的 `Pull Request`

## 运行教程    启动了 5 台虚拟机＋ 7 台 Tomcat ＋ 9 个 Dubbox 服务 内存使用情况

## 常见问题

1. 编译失败
	
	编译不成功的都是缺少jar包 麻烦配置Nexus 然后更新整个项目去下载jar包 
	在继续编译 如还失败 **请查看本地maven仓库jar是否真正下载下来**
	
2. 编译成功启动失败

	请确保你先启动了zookeeper 并且配置对了zookeeper地址 需要连接数据的请配置好数据密码
	service服务有启动顺序 请查看项目依赖图 看看你需要启动的服务依赖那些服务 
	
3. 启动不了

	90%是你的jar问题 




 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e2a7bdd43fcef6cbc558c10a0026fe0666d688bc7f61b4f99688cc9c6748ab17f969649afe0e4b65acd4548741f7c7427)