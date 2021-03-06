
## Coody Framework

#### 背景：

一名野生的民间技术爱好者，早期活跃于各网络安全论坛，而后由白帽转战编程。因谋生而从事互联网技术研发四年有余。

浑浑噩噩已经22岁了，看着朋友圈各种晒宝宝照片的老同学，只得感叹光阴似箭。而单身的笔者，随着岁月的流逝，寂寞空虚冷愈加强烈。故此，笔者选择通过技术研究来饱和业余生活。

#### 前言：

    Coody Framework 是由笔者业余时间编写的一套Ioc框架。由最初的项目内置代码发展至今的Maven中央仓库。历时4个月有余。

    而在今后的时间里，Coody Framework将不断完善，争取今年内发布一套成熟的release版本。同时，笔者也会自带成功案例。

#### 用途与优势：
    
    Coody Framework是一套轻量化Ioc框架。除分布式(即Rcc模块)未完成外，其余均已经过笔者本地测试。全框架大小214kb。
    
    Coody Framework 依赖cglib-3.2、log4j-1.2、noson-1.0.7。

    基于Coody Framework框架的web项目启动耗时约370ms(在i5 2320上所耗费的时间)、加上tomcat所消耗的时间，约4s-5s
    
    基于Coody Framework框架的测试用例已在服务器长跑3个月有余：http://czone.icoody.cn/ 

    Coody Framework框架包含以下模块

        coody-core ：框架核心包，包括Ioc+Aop的实现，包括相关工具和超类。

        coody-web  ：框架web-mvc的实现包，实现了mvc功能体系。

        coody-cache：框架缓存的实现，实现了基础缓存，切面缓存，并提供相关切面技术的支持。

        coody-jdbc ：框架orm的实现，实现了基于mysql下基础操作的封装，实现了各种简易操作，拓展了切面事物。
        
        coody-task ：框架定时任务的实现，基于cron实现了定时任务，提供了注解定时任务的支持。

        coody-rcc  ：框架分布式的实现，提供注册中心、序列化、通信协议等接口。字节码创建子类的实现(分布式功能未完成)


#### 更新记录：

    2018-02-24： 初步研发，实现Ioc+Aop。

    2018-02-25： 拓展Mvc，基于MVC结合Ioc+Aop实现轻量化(类spring)开发模式

    2018-02-26： 由最初的常规java project整改为Maven Project，并整合自写ORM框架配合aop实现事物管理。

    2018-03-08： 拓展接口形式依赖注入，对interface的Ioc提供支持。

    2018-03-10： 拓展定时任务，基于切面通过注解(cron)实现任务调度。

    2018-03-21： 使用Coody Framework整合至一个外置项目中并成功运行。

    2018-03-21： 为切面的拦截条件新增类通配、方法通配，同时支持一个拦截方法通过多个注解引入不同的拦截规则。

    2018-04-22： 微调Mvc相关功能，支持request和response在controller中进行注入(线程安全)

    2018-04-22： 整改Mvc参数适配器，支持自定义参数适配。

    2018-06-02： 筹划拓展分布式体系，并引入字节码技术创建实现类，提供通讯、序列化、注册中心等接口

    2018-06-05： 项目拆分成Maven多模块化模式，为发布maven中央仓库做准备

    2018-06-28： 发布Alpha至Maven中央仓库。nexus搜索"Coody"即可

    Coody Framework实战项目：https://gitee.com/coodyer/czone/

引用地址：

```
         
			 org.coody.framework 
			 coody-core 
			 alpha-1.1.1 
		 

		 
			 org.coody.framework 
			 coody-jdbc 
			 alpha-1.1.1 
		 
		 
			 org.coody.framework 
			 coody-cache 
			 alpha-1.1.1 
		 
		 
			 org.coody.framework 
			 coody-task 
			 alpha-1.1.1 
		 
		 
			 org.coody.framework 
			 coody-web 
			 alpha-1.1.1 
		 
```


=======================================================



### 1. 项目背景：


    纵观整个国内开源圈，难以寻找一套比较成熟的Ioc框架。然实现一套Ioc框架并没有太高的技术含量和工作量。

    故此，笔者着手将业余时间的一些代码和案例汇总，研发Coody Framework。



### 2. 功能说明：


    Coody Framewrok实现了：IOC依赖注入、AOP切面、MVC、定时任务、切面缓存、ORM等功能，分布式Rcc模块也已进入研发阶段。
 

### 3. 环境说明：


    JDK1.8+

### 4. 相关文档：

coody-core   ：[Coody-Core](http://u.720life.cn/g/e0d2c85055613e6181156334353bc3d945e45a5949c6e9d0d4a5660ec4a816ec4d1b29365392fe604e4ff4d154a0a49f4ce2e663590b1607e600df3b74a0f045) 

coody-web    ：[Coody Web](http://u.720life.cn/g/e0d2c85055613e6181156334353bc3d945e45a5949c6e9d0d4a5660ec4a816ec4d1b29365392fe604e4ff4d154a0a49ff921486522d68c4ce2149c572f441668) 

coody-cache  ：[Coody Cache](http://u.720life.cn/g/e0d2c85055613e6181156334353bc3d945e45a5949c6e9d0d4a5660ec4a816ec4d1b29365392fe604e4ff4d154a0a49f657accef5e0b92073d76823e838c7eef) 

coody-jdbc   ：[Coody Jdbc](http://u.720life.cn/g/e0d2c85055613e6181156334353bc3d945e45a5949c6e9d0d4a5660ec4a816ec4d1b29365392fe604e4ff4d154a0a49f6aaedf738907184a8b32f8df97824a61) 

coody-task   ：[Coody Task](http://u.720life.cn/g/e0d2c85055613e6181156334353bc3d945e45a5949c6e9d0d4a5660ec4a816ec4d1b29365392fe604e4ff4d154a0a49f506c83b22354363859baea0be2edbfee) 

coody-rcc    ：[Coody Rcc](http://u.720life.cn/g/e0d2c85055613e6181156334353bc3d945e45a5949c6e9d0d4a5660ec4a816ec4d1b29365392fe604e4ff4d154a0a49fbc94d410d21068c8a25947414183fa2c)  
 


### 5. 发展计划：

    1、完善rcc分布式模块

    2、为Coody Framework提供完整的配置中心

    3、完成博文系统并作为成功案例

    4、提供完整的文档

    5、接入MiniCat实现类SpringBoot开发模式(可选)


### 6. 合作意向：

    首先说明一下，开发一套框架并不需要多么高深的技术。相反，开发一套框架非常简单，我们都是在追溯偷懒的艺术。
    
    通过一些特殊的机制和算法，提供一系列为开发者服务的解决方案。

    1、如果你逻辑思维活跃

    2、如果你具备java相关的技术

    3、如果你有互联网产品开发的实际经验

    4、如果你对Coody Framework 的研究有一定的兴趣

    那么，请联系我，笔者真诚的希望你能加入到Coody Framework 的开发中来，并肩作战，为国内开源技术做贡献。

### 7. 版权说明：


    在本项目源代码中，已有测试demo，包括mvc、切面等示例

    作者：Coody
    
    版权：©2014-2020 Test404 All right reserved. 版权所有

    反馈邮箱：644556636@qq.com

    交流群号:218481849

    基于Coody Framework的博文系统：https://gitee.com/coodyer/czone  (研发中)




 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)