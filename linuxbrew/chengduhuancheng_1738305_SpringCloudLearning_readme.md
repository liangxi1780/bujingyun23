
>转载请标明出处： 
> https://blog.csdn.net/forezp/article/details/70148833
> 本文出自[方志朋的博客](http://u.720life.cn/g/57ba3eb2aac14af39b4a67728efad82096a209ca820e16cb7913252b42ccd51d)

 
     
         
         
        扫码关注有惊喜
     
     
         （转载本站文章请注明作者和出处  方志朋的博客 ） 
     
 

[CSDN 2018 年 博客之星，请为我投一票，感谢！~](http://u.720life.cn/g/ce3f6174933242f367d8a4cd3fa79dedb8a702fb295a6e7b81086ff6dfc248a8037c9eeaee977757742d94af763d3bdd7975afb41c72d2771aabc27faa44ea53)

欢迎大家访问我的个人博客：https://www.fangzhipeng.com/

错过了这一篇，你可能再也学不会 Spring Cloud 了！Spring Boot做为下一代 web 框架，Spring Cloud 作为最新最火的微服务的翘楚，你还有什么理由拒绝。赶快上船吧，老船长带你飞。终章不是最后一篇，它是一个汇总，未来还会写很多篇。



我为什么这些文章？一是巩固自己的知识，二是希望有更加开放和与人分享的心态，三是接受各位大神的批评指教，有任何问题可以联系我: miles02@163.com .

码农下载：[https://git.oschina.net/forezp/SpringCloudLearning](http://u.720life.cn/g/3e7e8f170da15d1979f4c6b1321cc36b8dc900fdbf0c07a49f8065bad0694056cf842a75cde8bfdbfe7a48cea8c14dfdcc0411ecf726fe0103061ec431c8b81e)

github下载：[https://github.com/forezp/SpringCloudLearning](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046321f82ba43e74c5568429965d6ec38ff66f08dd114a8a6f556fcb9725e87dc75),记得star哦！

### 欢迎购买我的书《深入理解Spring Cloud与微服务构建》

![1.jpg](https://upload-images.jianshu.io/upload_images/2279594-3d9ee1555f555040.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/150)

[京东购买](http://u.720life.cn/g/7b2b4b420a3d295955078cf4db9efbc3b3c563910a7619522ef6491dd7218b90d575e35417472dfa91bcddc87026f60e)  [当当购买](http://u.720life.cn/g/c4870a3df4dbf9b3f895a193ff995ebebd439742d149f1424b0a5b01d88dd1f18ed1a23f3ce412b7265d475263c79d80) [亚马逊购买](http://u.720life.cn/g/cb03c2a1672c12ec833030607d89ad067466e292b2df49a584e8e01adac7f08c7c190a4693e471cb9eb4423ce2bc25de93481daa81cd104407b5777b9d1858b869e7deeaf01fa39b5adc556b2f3a49be8afedcbd5d75e523fc8aca5cb531b04eacb45840d270b0f0e716686a15366bac)

#### CSDN专栏汇总：[史上最简单的 SpringCloud 教程](http://u.720life.cn/g/5997fd1f539dfbe7c9c67736234755a4a6289c8202d9ee07795bb8bf69a7d2612ef83f7306593d38d3ef8310d2848720e4949831b165b603f9610e8feac4e266)

### 《史上最简单的 SpringCloud 教程》系列：

### Finchley版本 

欢迎大家访问我的个人博客：https://www.fangzhipeng.com/

Spring Cloud Finchley; Spring Boot 2.0.3

* [史上最简单的 SpringCloud 教程 | 第一篇: 服务的注册与发现（Eureka）(Finchley版本)](http://u.720life.cn/g/5997fd1f539dfbe7c9c67736234755a4a6289c8202d9ee07795bb8bf69a7d26142fe46ae724633a58a494be61597aea0ca4c6a6d3a03632ebf72eb0263df6057)
* [史上最简单的SpringCloud教程 | 第二篇: 服务消费者（rest+ribbon）(Finchley版本)](http://u.720life.cn/g/5997fd1f539dfbe7c9c67736234755a4a6289c8202d9ee07795bb8bf69a7d26142fe46ae724633a58a494be61597aea0d620f960e0ace07b3b27f0b9ae839ac5)
* [史上最简单的SpringCloud教程 | 第三篇: 服务消费者（Feign）(Finchley版本)](http://u.720life.cn/g/5997fd1f539dfbe7c9c67736234755a4a6289c8202d9ee07795bb8bf69a7d26142fe46ae724633a58a494be61597aea00853cd8cea1a9efb685fc8aea093d5fe)
* [史上最简单的SpringCloud教程 | 第四篇:断路器（Hystrix）(Finchley版本)](http://u.720life.cn/g/5997fd1f539dfbe7c9c67736234755a4a6289c8202d9ee07795bb8bf69a7d26142fe46ae724633a58a494be61597aea0e057aed76da0c9ca6059f64f6642a6b0)
* [ 史上最简单的SpringCloud教程 | 第五篇: 路由网关(zuul)(Finchley版本)](http://u.720life.cn/g/5997fd1f539dfbe7c9c67736234755a4a6289c8202d9ee07795bb8bf69a7d26142fe46ae724633a58a494be61597aea0e1c9b49c545db829188af7f45e7345bf)
* [史上最简单的SpringCloud教程 | 第六篇: 分布式配置中心(Spring Cloud Config)(Finchley版本)](http://u.720life.cn/g/5997fd1f539dfbe7c9c67736234755a4a6289c8202d9ee07795bb8bf69a7d26142fe46ae724633a58a494be61597aea0fc1ddd1a967c6db4cdc2d7e8bc1d42d3)
* [史上最简单的SpringCloud教程 | 第七篇: 高可用的分布式配置中心(Spring Cloud Config)(Finchley版本)](http://u.720life.cn/g/5997fd1f539dfbe7c9c67736234755a4a6289c8202d9ee07795bb8bf69a7d26142fe46ae724633a58a494be61597aea0fef3c60f1160b4a1f7cd6141b02025bf)
* [史上最简单的SpringCloud教程 | 第八篇: 消息总线(Spring Cloud Bus)(Finchley版本)](http://u.720life.cn/g/5997fd1f539dfbe7c9c67736234755a4a6289c8202d9ee07795bb8bf69a7d26142fe46ae724633a58a494be61597aea07c335f2561afa63d8b1f51c72771b3f0)
* [史上最简单的SpringCloud教程 | 第九篇: 服务链路追踪(Spring Cloud Sleuth)(Finchley版本)](http://u.720life.cn/g/5997fd1f539dfbe7c9c67736234755a4a6289c8202d9ee07795bb8bf69a7d26142fe46ae724633a58a494be61597aea0b62a6f0fb5c50880645d75a29bd57f15)
* [史上最简单的SpringCloud教程 | 第十篇: 高可用的服务注册中心(Finchley版本)](http://u.720life.cn/g/5997fd1f539dfbe7c9c67736234755a4a6289c8202d9ee07795bb8bf69a7d26142fe46ae724633a58a494be61597aea0e4c7ea65e8dde57ec64789a72a5e296a)

* [史上最简单的SpringCloud教程 | 第十二篇: 断路器监控(Hystrix Dashboard)(Finchley版本)](http://u.720life.cn/g/5997fd1f539dfbe7c9c67736234755a4a6289c8202d9ee07795bb8bf69a7d26142fe46ae724633a58a494be61597aea07e635ac0aa980809fe6a6c18a7a02f22)
* [史上最简单的SpringCloud教程 | 第十三篇: 断路器聚合监控(Hystrix Turbine)(Finchley版本)](http://u.720life.cn/g/5997fd1f539dfbe7c9c67736234755a4a6289c8202d9ee07795bb8bf69a7d26142fe46ae724633a58a494be61597aea0dc4f9edf436fc2bd54f535f0ff56f66a)
* [史上最简单的SpringCloud教程 | 第十四篇: Spring Cloud Gateway初体验](http://u.720life.cn/g/ce3f6174933242f367d8a4cd3fa79dedb8a702fb295a6e7b81086ff6dfc248a8860b1d0b9989323b1d9e9b057f08f13550ae5ab948a660783f61a97f0120a02d)
* [史上最简单的SpringCloud教程 | 第十五篇: Spring Cloud Gateway 之Predict篇](http://u.720life.cn/g/ce3f6174933242f367d8a4cd3fa79dedb8a702fb295a6e7b81086ff6dfc248a8bba8186ff400f23613f215a6458868edf0a0487a9a1c92c1cc23a63909bff305)
* [史上最简单的SpringCloud教程 | 第十六篇: Spring Cloud Gateway 之filter篇](http://u.720life.cn/g/ce3f6174933242f367d8a4cd3fa79dedb8a702fb295a6e7b81086ff6dfc248a8379b8d3947c94d3a965670444667e7a7c7197f1a43971498ee67685bdc27280d)
*  [史上最简单的SpringCloud教程 | 第十七篇: Spring Cloud Gateway 之限流篇](http://u.720life.cn/g/ce3f6174933242f367d8a4cd3fa79dedb8a702fb295a6e7b81086ff6dfc248a8379b8d3947c94d3a965670444667e7a76d9b4a64c0b66214205f9cf2b1cdeab2)
*  [史上最简单的SpringCloud教程 | 第十八篇: spring cloud gateway之服务注册与发现](http://u.720life.cn/g/ce3f6174933242f367d8a4cd3fa79dedb8a702fb295a6e7b81086ff6dfc248a87e83b28dd650dc9a3801c013621c07068d68dbf274b7c2697fbde4dee2c30eaa)

### 源码篇：

* [深入理解Feign之源码解析](http://u.720life.cn/g/5997fd1f539dfbe7c9c67736234755a4a6289c8202d9ee07795bb8bf69a7d26105f4e300c35af8ae4c2640a18bd35d1ed2ab3f885bd59a79de53057b2d7fa0b5)
* [深入理解Eureka之源码解析](http://u.720life.cn/g/5997fd1f539dfbe7c9c67736234755a4a6289c8202d9ee07795bb8bf69a7d261ba43bbac9182718d5d06be8eb580992dd5c60b43bbdca87d1c5891a50d28f6d9)
* [深入理解Ribbon之源码解析](http://u.720life.cn/g/5997fd1f539dfbe7c9c67736234755a4a6289c8202d9ee07795bb8bf69a7d261b38fcf620c723fc40c596c3fb4fa737eeaf7ad19baf2776f188fbfc3b0202410)
*  [ 深入理解Hystrix之文档翻译](http://u.720life.cn/g/5997fd1f539dfbe7c9c67736234755a4a6289c8202d9ee07795bb8bf69a7d261b6b6ce62c18ff520494933ce15438acc2968acd7c2a4cca127bf725dd01490dd)
* [深入理解Zuul之源码解析](http://u.720life.cn/g/5997fd1f539dfbe7c9c67736234755a4a6289c8202d9ee07795bb8bf69a7d2611aa0ff62f55753b2351332401e12bdeb2bb88d9c213080fc771b90aa8427d9d1)

### 进阶篇

* [ Spring Cloud Sleuth超详细实战](http://u.720life.cn/g/5997fd1f539dfbe7c9c67736234755a4a6289c8202d9ee07795bb8bf69a7d26121a4941ae1f46f0d39189222a75b6949716d7d9bc45c50b4cb7bc0c7290c2faf)
* [拜托！面试请不要再问我Spring Cloud底层原理](http://u.720life.cn/g/ce3f6174933242f367d8a4cd3fa79dedb8a702fb295a6e7b81086ff6dfc248a80a18d6c0d6bede51a679615784d6d3436624f9488ed7f0172637df058be54a41)
*  [微服务注册中心如何承载大型系统的千万级访问？](http://u.720life.cn/g/ce3f6174933242f367d8a4cd3fa79dedb8a702fb295a6e7b81086ff6dfc248a80a18d6c0d6bede51a679615784d6d343fd54ce11f86aef5c45ce1d078ef0d354)
*  [每秒上万并发下的Spring Cloud参数优化实战](http://u.720life.cn/g/ce3f6174933242f367d8a4cd3fa79dedb8a702fb295a6e7b81086ff6dfc248a80a18d6c0d6bede51a679615784d6d34342161dd8db9aaaaf81016b6cfdd78d7c)


#### D版本

* [史上最简单的 SpringCloud 教程 | 第一篇: 服务的注册与发现（Eureka）](http://u.720life.cn/g/5997fd1f539dfbe7c9c67736234755a4a6289c8202d9ee07795bb8bf69a7d261a24e0fbecdb420200284ca2b3ef6516328e5be395a370e2e4a448227f39a64ed)
* [史上最简单的SpringCloud教程 | 第二篇: 服务消费者（rest+ribbon）](http://u.720life.cn/g/5997fd1f539dfbe7c9c67736234755a4a6289c8202d9ee07795bb8bf69a7d2619b33a2c763410d47f481484ea73f9144a1b9df593bb087c30986ca37610165a0)
* [史上最简单的SpringCloud教程 | 第三篇: 服务消费者（Feign）](http://u.720life.cn/g/5997fd1f539dfbe7c9c67736234755a4a6289c8202d9ee07795bb8bf69a7d261acceefa4028d5bd4f2f60e13e8be257f823a5ed91ddd508965a89f45f43c4cec)
* [史上最简单的SpringCloud教程 | 第四篇:断路器（Hystrix）](http://u.720life.cn/g/5997fd1f539dfbe7c9c67736234755a4a6289c8202d9ee07795bb8bf69a7d2613cc73e70b4f97a0dc7272123f9ba6e62eb74a2be393996885104aa7159f4448a)
* [ 史上最简单的SpringCloud教程 | 第五篇: 路由网关(zuul)](http://u.720life.cn/g/5997fd1f539dfbe7c9c67736234755a4a6289c8202d9ee07795bb8bf69a7d2613cc73e70b4f97a0dc7272123f9ba6e629dd1cfc3f7d96f913e59018b62376fb9)
* [史上最简单的SpringCloud教程 | 第六篇: 分布式配置中心(Spring Cloud Config)](http://u.720life.cn/g/5997fd1f539dfbe7c9c67736234755a4a6289c8202d9ee07795bb8bf69a7d2611ebeedc5c78e35729372a7bc99310cf4414105af953aaaea3187bea6e0834c8f)
* [史上最简单的SpringCloud教程 | 第七篇: 高可用的分布式配置中心(Spring Cloud Config)](http://u.720life.cn/g/5997fd1f539dfbe7c9c67736234755a4a6289c8202d9ee07795bb8bf69a7d2611ebeedc5c78e35729372a7bc99310cf49fc16e898b67ce62865e7738ed5786e4)
* [史上最简单的SpringCloud教程 | 第八篇: 消息总线(Spring Cloud Bus)](http://u.720life.cn/g/5997fd1f539dfbe7c9c67736234755a4a6289c8202d9ee07795bb8bf69a7d2612ef83f7306593d38d3ef8310d2848720116767a9cdaafd105bfb1ebfd92a5c63)
* [史上最简单的SpringCloud教程 | 第九篇: 服务链路追踪(Spring Cloud Sleuth)](http://u.720life.cn/g/5997fd1f539dfbe7c9c67736234755a4a6289c8202d9ee07795bb8bf69a7d261b585c906054dc96506c82047aad9d1f4c44347fd03046fdae9ccb0edb3efa5bd)
* [史上最简单的SpringCloud教程 | 第十篇: 高可用的服务注册中心](http://u.720life.cn/g/5997fd1f539dfbe7c9c67736234755a4a6289c8202d9ee07795bb8bf69a7d261f407fe1558a65147a0ba2ce9c8c83e226d4aa1a2161baada9940f12ed1149cf5)
* [史上最简单的SpringCloud教程 | 第十一篇:docker部署spring cloud项目](http://u.720life.cn/g/5997fd1f539dfbe7c9c67736234755a4a6289c8202d9ee07795bb8bf69a7d26144db679ba0236f285bbd2a0852ef707e035a1be9027c9f0398c5ca8d61a3f1e5)
* [史上最简单的SpringCloud教程 | 第十二篇: 断路器监控(Hystrix Dashboard)](http://u.720life.cn/g/5997fd1f539dfbe7c9c67736234755a4a6289c8202d9ee07795bb8bf69a7d26102841c8cc46c97890d442ec1d3c475e1f6d2b14b0cc0c8e7f4d896d86e28dcc9)
* [史上最简单的SpringCloud教程 | 第十三篇: 断路器聚合监控(Hystrix Turbine)](http://u.720life.cn/g/5997fd1f539dfbe7c9c67736234755a4a6289c8202d9ee07795bb8bf69a7d261eefdda4938d93a27eee369e4fc6493d2c6eb8e93dc13936552d11ff22d7210da)
* [ 史上最简单的 SpringCloud 教程 | 第十四篇: 服务注册(consul)](http://u.720life.cn/g/5997fd1f539dfbe7c9c67736234755a4a6289c8202d9ee07795bb8bf69a7d261623eb66740c74458826a3046daeca1e92730edaf278ec1bd3354680d2fc0c188)
*  未完。。。
*  还有很多篇。。。
 
### 番外篇：

* [如何使用MongoDB+Springboot实现分布式ID?](http://u.720life.cn/g/5997fd1f539dfbe7c9c67736234755a4a6289c8202d9ee07795bb8bf69a7d261acf16319c8bfa5bed4741f732391f2c2274af37e4f120b019bedb048138834a0)
* [ 如何在springcloud分布式系统中实现分布式锁？](http://u.720life.cn/g/5997fd1f539dfbe7c9c67736234755a4a6289c8202d9ee07795bb8bf69a7d2617f4a8ca257d94359b60a7d43790ac33beb7f2e355808f708d471db99a4b780c8)
* [ 如何用Redlock实现分布式锁](http://u.720life.cn/g/5997fd1f539dfbe7c9c67736234755a4a6289c8202d9ee07795bb8bf69a7d26168912d7ae100de5d4d206e12c3f044c25bd4a347654aa4838c484523a66306d6)
* [ 如何在IDEA启动多个Spring Boot工程实例](http://u.720life.cn/g/5997fd1f539dfbe7c9c67736234755a4a6289c8202d9ee07795bb8bf69a7d2613305ff67d4ec0db50c05d34e1f43ebac83fc3c135a3a9484c6ee1a2a58c5e77d)
* [ JWT如何在Spring Cloud微服务系统中在服务相互调时传](http://u.720life.cn/g/5997fd1f539dfbe7c9c67736234755a4a6289c8202d9ee07795bb8bf69a7d2613c6015d47294d125f03ede2ff65004895d79926d604b4c866d7c15c207e89cca)




### 怎么支持我？

* 这个系列会持续更新，敬请关注！


* 关注我的公众号,精彩内容不能错过！

 
     
         
         
        扫码关注有惊喜
     
     
         （转载本站文章请注明作者和出处  方志朋的博客 ） 
     
 




 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e9eda0622e2934f1f6cde89601b897ca345c733ef4814d8e245fc015aad4ffa7f3e516b4abaff74571e569ef4342be26f60cdd5ea4fcb7d8e78285ee7579b27a5124269386ae631ad0a2a345ec244e3b2)