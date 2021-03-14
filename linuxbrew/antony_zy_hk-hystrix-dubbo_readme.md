# dubbo-hystrix
dubbo集成hystrix熔断器

### 一、背景
在微服务架构中通常会有多个服务层调用，基础服务的故障可能会导致级联故障，进而造成整个系统不可用的情况，这种现象被称为服务雪崩效应。服务雪崩效应是一种因“服务提供者”的不可用导致“服务消费者”的不可用,并将不可用逐渐放大的过程。  

如果下图所示：A作为服务提供者，B为A的服务消费者，C和D是B的服务消费者。A不可用引起了B的不可用，并将不可用像滚雪球一样放大到C和D时，雪崩效应就形成了。
![](image/雪崩效应.png)

### 二、简介
熔断器的原理如同电力过载保护器。它可以实现快速失败，如果它在一段时间内侦测到许多类似的错误，会强迫其以后的多个调用快速失败，不再访问远程服务器，从而防止应用程序不断地尝试执行可能会失败的操作，使得应用程序继续执行而不用等待修正错误，或者浪费CPU时间去等到长时间的超时产生。

### 三、项目说明
1、：dubbo-consumer、dubbo-provider分别作为服务的消费者和生产者，所有熔断相关配置是在消费者中配置。  
2、dubbo-consumer 项目pom文件说明：  
有两种方案可以集成hystrix：   

方案一：基于springboot项目，熔断方式是针对单个方法(不限于rpc调用)熔断  
方案二：需要配置熔断过滤器，熔断方式是针对所有rpc接口统一熔断
![](image/熔断方案依赖.png)

### 四、熔断方案一  
1、springboot启动类添加注解 `@EnableCircuitBreaker`  
![](image/方案一启动类配置.png)  

2、要熔断方法上添加注解`@HystrixCommand(fallbackMethod="yourfunction")`  
针对不同的业务自定义熔断后调用的方法
![](image/方案一熔断方法注解配置.png)  

3、熔断策略配置  
配置文件：  
`$PWD/dubbo-consumer/src/main/resources/application.properties`
![](image/熔断配置文件.png)  
可以指定更多策略，如错误率多少后熔断等，可参考：`http://blog.csdn.net/harris135/article/details/77879148?locationNum=3&fps=1`

### 五、熔断方案二
1、将核心类`DubboHystrixCommand` 、`HystrixFilter`添加到项目中  
![](image/方案二配置说明1.png) 
 
2、新建dubbo过滤器配置`com.alibaba.dubbo.rpc.Filter`,注意，此配置需放在META-INF下的dubbo目录中。配置内容如下：
![](image/方案二dubbo过滤器配置.png)  

3、熔断策略配置  
可以指定超时、错误次数等策略。可以参考源码提供的方法或Hystrix官方配置说明
![](image/方案二策略配置.png)

### 六、测试
本demo使用的是方案一  
##### 1、修改配置文件
`$PWD/dubbo-consumer/src/main/resources/consumer.xml`  
![](image/服务调用配置.png)
##### 2、启动dubbo-provider项目  
cd `$PWD/dubbo-provider`  
sh `startup-code.sh`  
##### 3、启动dubbo-consumer项目  
cd `$PWD/dubbo-consumer`  
sh `startup-code.sh`  
##### 4、浏览器打开 `http://${ip}:8099/test/say`  
成功返回 from provide: hello说明rpc接口调用成功  
##### 5、修改配置文件
`$PWD/dubbo-consumer/src/main/resources/application.properties`  
将超时时间设置2000(单位ms)  
##### 6、重新启动dubbo-consumer项目
cd `$PWD/dubbo-consumer`  
sh `startup-code.sh`
##### 7、浏览器再次打开 `http://${ip}:8099/test/say`  
成功返回 timeout hystrix 说明超时熔断成功
##### 8、说明
dubbo-provider提供的rpc示例接口有3秒的睡眠时间,所以熔断配置2秒或4秒即可验证是否熔断生效。









 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e3367dee716cf8c12e7871bcf88cdca1beb498462ccc892d9f39ce7e7dc4c5bba5e0b88be1a1234273c0326028d31211da26dccd4ab597d741a435c8b2b5f5958)