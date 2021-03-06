Hmily
================

### 分布式事务方案之tcc开源框架。基于java语言来开发（JDK1.8），支持dubbo，springcloud等rpc框架进行分布式事务。

 # Features

 * **框架特性**

     * ##### 采用disruptor框架进行事务日志的异步读写，与RPC框架的性能毫无差别。

     * ##### 支持SpringBoot-starter 项目启动，使用简单。

     * ##### RPC框架支持 : dubbo,motan,springcloud。

     * ##### 本地事务存储支持 : redis,mongodb,zookeeper,file,mysql。

     * ##### 事务日志序列化支持 ：java，hessian，kryo，protostuff。

     * ##### 采用Aspect AOP 切面思想与Spring无缝集成，天然支持集群。

     * ##### 内置经典的分布式事务场景demo工程，并有swagger-ui可视化界面可以快速体验。


#  源码解析博客

  * ## https://yu199195.github.io/categories/hmily-tcc/


#  视频详解

  * ## 环境搭建以及运行 : http://www.iqiyi.com/w_19rwkrfu69.html#vfrm=16-1-1-1
  * ## 源码详解以及调试 : http://www.iqiyi.com/w_19rwkreutt.html


# Prerequisite

  *   #### JDK 1.8+

  *   #### Maven 3.2.x

  *   #### Git

  *   ####  RPC framework dubbo or motan or springcloud。


# Spring-Boot-Starter-Support

   * ### [Spring-Boot-Starter](http://u.720life.cn/g/54145d0471d91890860f7f8463c030460f604a45ad22717656e35b3c5e7da352c76f292c601a5234e36a5e040f1166cc7e7fdf9cd4f98529686c54685390f079)


# TCC原理介绍

  * ###  https://github.com/yu199195/hmily/wiki/Theory

#   Configuration

  * ###  https://github.com/yu199195/hmily/wiki/Configuration


# Quick Start

 * #### Clone & Build
   ```
   > git clone https://github.com/yu199195/hmily.git

   > cd hmily

   > mvn -DskipTests clean install -U
   ```

* #### execute this sql       
    https://github.com/yu199195/hmily/blob/master/hmily-tcc-demo/sql/tcc-demo.sql

* #### Find the RPC framework that works for you
    https://github.com/yu199195/hmily/tree/master/hmily-tcc-demo
* ### [Dubbo-Quick-Start](http://u.720life.cn/g/54145d0471d91890860f7f8463c030460f604a45ad22717656e35b3c5e7da3529ba27f70762998450cc8341bedb04116f8692c5b112cb2be92740fabbd78b887)

* ### [SpringCloud-Quick-Start](http://u.720life.cn/g/54145d0471d91890860f7f8463c030460f604a45ad22717656e35b3c5e7da3528444700e73400bb47f45700b5b6b374cd92c881f121175e870a9b0e66e5585a5)





# User Guide

* #### 关于jar包引用问题，现在jar包还未上传到maven的中央仓库，所以使用者需要自行获取代码，然后打包上传到自己maven私服

   ```
   > git clone https://github.com/yu199195/hmily.git

   > mvn -DskipTests clean deploy -U
   ```
* #### 关于jar包版本问题 ，现在因为没有传到中央仓库，如果引用的话，请自行设置相应的版本。


*  ## [Dubbo User Guide](http://u.720life.cn/g/54145d0471d91890860f7f8463c030460f604a45ad22717656e35b3c5e7da352601e73bde0946ab2b6a227d28832c7a41ecf30a8278fa767de4c5d11b5aff894)

*  ## [SpringCloud User Guide](http://u.720life.cn/g/54145d0471d91890860f7f8463c030460f604a45ad22717656e35b3c5e7da3528444700e73400bb47f45700b5b6b374cf06ef9a72b2bcf842c631d2aed8366b2)



# FAQ

* ### 为什么我下载的代码后，用idea打开没有相应的get set 方法呢？
   ##### 答：因为框架使用了Lombok包，它是在编译的时期，自动生成get set方法，并不影响运行，如果觉得提示错误难受，请自行下载lombok包插件，[lombok官网](http://u.720life.cn/g/38e2c0a1caffcef70ab67997ff249482191ef76f813957d36ffa94cc0fd5036e)

* ### 为什么我运行demo工程，找不到applicationContent.xml呢？
  ##### 答：请设置项目的资源文件夹。

* ### 为什么我启动tcc-admin项目的时候，会报mongo 集群连接错误呢？
  ##### 答：这是因为项目里面有mongo代码，spring boot会自动配置，该错误没有关系，只要admin项目能正常启动就行。



# Support

 * ###  如有任何问题欢迎加入QQ群进行讨论
   ![](https://yu199195.github.io/images/qq.png)


 * ###  微信公众号
   ![](https://yu199195.github.io/images/public.jpg)

 # Contribution



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e44999cb4e28c1209865b5e2209985380d72663c2d03c915b75940c8ec8f1f68ac1be39790cddb829bfd9876e2c1a8f15)