##分布式缓存中间件##
  方便实现缓存的分布式，集群，负载均衡，故障自动转移，并兼容多种缓存存储的分布式缓存中间件。 用于解决分布式架构中的分布式缓存环节。

##特点：##
 1. 代码少，便于扩展。
 2. 兼容阿里云memcache，redis，ssdb。
 3. 规范缓存使用接口，屏蔽底层缓存实现。
 4. 通过配置连接字符串即可切换不同存储引擎，可以混合不同存储引擎组成缓存集群部署。（如部分redis，部分memcache）
 5. 动态负载均衡，故障转移，线上无缝平行扩展和扩容，方便运维。

##不同存储介质##
       

        ///  
        /// Redis 
        /// 数据存内存,适合内存大小范围内大量缓存。（若是频繁失效的缓存数据，大量热点数据，建议使用redis）
        ///  
        Redis,
        ///  
        /// SSDB
        /// 数据热点存内存，大量数据存磁盘。（若是命中率较低，命中热点数据，大量冷数据，建议使用ssdb）
        ///  
        SSDB,
        ///  
        /// Memcached
        ///  
        Memcached,
        ///  
        /// SQLServer内存表
        ///  
        SqlServer,
        ///  
        /// 阿里云的缓存服务OCS
        ///  
        AliyunMemcached,

##备注：##
 1. 属于半研究性项目，已在线上阿里云memcache环境使用。

##未来发展:##
 1. 分布式缓存中间件平台化，实现缓存监控，预警，性能报告等，性能数据收集至监控平台。
 2. 扩展分布式缓存的其他特点。
 3. 环形一致性hash对负载均衡和故障转移的支持。  

开源相关群: .net 开源基础服务 **238543768** 
(大家都有本职工作，也许不能及时响应和跟踪解决问题，请谅解。)

##.net 开源第三方开发学习路线 ##

- 路线1:下载开源源码->学习开源项目->成功部署项目（根据开源文档或者QQ群项目管理员协助）->成为QQ群相关项目管理员->了解并解决日常开源项目问题->总结并整理开源项目文档并分享给大家或推广->成为git项目的开发者和参与者
- 路线2:下载开源源码->学习开源项目->成功部署项目（根据开源文档或者QQ群项目管理员协助）->在实际使用中发现bug并提交bug给项目相关管理员
- 路线3:下载开源源码->学习开源项目->成功部署项目（根据开源文档或者QQ群项目管理员协助）->自行建立开源项目分支->提交分支新功能给项目官方开发人员->官方开发人员根据项目情况合并新功能并发布新版本

## 关于.net 开源生态圈的构想 ##
 .net 生态闭环 ：官方开源项目->第三方参与学习->第三方改进并提交新功能或bug->官方合并新功能或bug->官方发布新版本 
 为什么开源?  .net 开源生态本身弱,而强大是你与我不断学习，点滴分享,相互协助，共同营造良好的.net生态环境。 
 开源理念:  开源是一种态度，分享是一种精神，学习仍需坚持，进步仍需努力，.net生态圈因你我更加美好。 

by 车江毅


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ed423fb7431d870f4513f3d4426d9d7a3f19ef8d2e915d47b8d526aa02c12cb0b0d4c0d8dcd5a4e52798433888e85a23732142a286a2ea750095a20265b20c0ec4eb9a3a266b98a8091453f3f58ffb2f0)