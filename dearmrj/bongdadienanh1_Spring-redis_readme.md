# Spring-redis
  随着Nosql分布式数据库的不断出现，各种非关系型数据库的重要性日益涌现。redis是一个在内存中运行的键值数据库，是一个业界闻名的分布式缓存。本项目基于Spring平台，整合redis数据库，为我们的业务逻辑添加redis数据缓存的功能。主要特性如下：
  
  1.redis的连接基于Spring-data-redis模块，官网：http://projects.spring.io/spring-data-redis/
  
  2.界面的功能与项目http://git.oschina.net/shenzhanwang/SSM 一模一样，只是在业务逻辑层ActorServiceImpl中添加了缓存支持；
  
  3.一般读取方法需要添加@Cacheable，而删除需要使用@CacheEvict，添加和修改使用@CachePut，以防止失效的缓存数据在前端进行了展示；
  
  4.为了不引起歧义，缓存的名称保持与方法名相同；
  
  5.为了表明一个操作是读取缓存数据还是拉取数据库数据，方法体中有控制台输出，如果是读取缓存则不会有控制台输出:
       ![输入图片说明](http://git.oschina.net/uploads/images/2016/1203/114814_d2e20090_1110335.jpeg "在这里输入图片标题")
       
 6.当访问了一次actor列表的页面后，我们看到redis数据库中新增了记录：
     ![输入图片说明](http://git.oschina.net/uploads/images/2016/1203/114840_6b798e23_1110335.jpeg "在这里输入图片标题")
     
 7.以下是添加了缓存的页面：
  ![输入图片说明](http://git.oschina.net/uploads/images/2016/1203/114855_61a29982_1110335.jpeg "在这里输入图片标题")
### redis的事务
Redis 事务可以一次执行多个命令， 并且带有以下两个重要的保证：
- 事务是一个单独的隔离操作：事务中的所有命令都会序列化、按顺序地执行。事务在执行的过程中，不会被其他客户端发送来的命令请求所打断。
- 事务是一个原子操作：事务中的命令要么全部被执行，要么全部都不执行。

一个事务从开始到执行会经历以下三个阶段：
- 开始事务。
- 命令入队。
- 执行事务。
redis的WATCH命令可用于监控变量，事务执行时若监控的变量发生变化，则事务执行失败。这个过程类似于一种乐观锁。
### redis的应用场景
- 缓存数据库的行，减少数据库的压力
- 集中式地管理session，避免负载均衡后无法登录
- 实现分布式锁，解决并发问题


### 附录：个人作品索引目录（持续更新）

#### 基础篇:职业化，从做好OA系统开始
1. [SpringMVC,Mybatis,Spring三大框架的整合实现增删改查](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ee47c28d44de0f80ef0769f7ca53572561792735261a32bb4eb77fa95835490c5)
2. [Struts2,Hibernate,Spring三大框架的整合实现增删改查](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ee47c28d44de0f80ef0769f7ca5357256f41b457f53f752eee8a79c949e3bccb5)
3. [Spring,SpringMVC和Hibernate的整合实现增删改查](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ee47c28d44de0f80ef0769f7ca5357256673d1cf49d64c37bed5a9badf9e06386)
4. [Spring平台整合activiti工作流引擎实现OA开发](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ee47c28d44de0f80ef0769f7ca53572569186b5133b3133627b659352d032f45a)
5. [Spring发布与调用REST风格的WebService](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ee47c28d44de0f80ef0769f7ca5357256a15ad2f399b2629aad6bd6890be26509)
6. [Spring整合Apache Shiro框架，实现用户管理和权限控制](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ee47c28d44de0f80ef0769f7ca53572560e15a6a603e2a6aad04c1225dba3a82a)
7. [使用Spring security做权限控制](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ea1b55249ff5e0aa1098a1b8735fdf79a44e80cff8a13092f3253f494058601e4f800132011545e84b233147817883946)
8. [Spring整合Jasig CAS框架实现单点登录](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ee47c28d44de0f80ef0769f7ca53572565fcc6178502fb6bef5570b08591a4518)
#### 中级篇：中间件的各种姿势
9. [Spring连接mongoDB数据库实现增删改查](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ee47c28d44de0f80ef0769f7ca5357256b40ef1016535817ae51e05c5bf9677d0)
10. [Spring连接Redis实现缓存](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ee47c28d44de0f80ef0769f7ca5357256ef89d0f29a359796b0213b03dcb76ea7)
11. [Spring连接图存数据库Neo4j实现增删改查](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ee47c28d44de0f80ef0769f7ca53572563c588a99507acc91e1539a6116854402)
12. [Spring平台整合消息队列ActiveMQ实现发布订阅、生产者消费者模型（JMS）](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ee47c28d44de0f80ef0769f7ca53572561151494a8000934f90156dbe02965f42)
13. [Spring整合消息队列RabbitMQ实现四种消息模式（AMQP）](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ee47c28d44de0f80ef0769f7ca53572566af86eaf061f2c7c1a888d6b29fa38c2)
14. Spring框架的session模块实现集中式session管理（[购买](http://u.720life.cn/g/5d49be387f8da10d3acd1a25d7d4e61a71abeb56ffb940373ac7603666f329282de51d0053e3c37e1d8a3a630ec42e049fd2ab2ee92cafa6e4ec79f52ef1dfee)）
15. [Spring整合websocket实现即时通讯](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ee47c28d44de0f80ef0769f7ca5357256aa1410207072711266bc55b5923ad248)
16. 使用Spring boot整合mybatis,rabbitmq,redis,mongodb实现增删改查（[购买](http://u.720life.cn/g/5d49be387f8da10d3acd1a25d7d4e61a71abeb56ffb940373ac7603666f32928ab485fa33792d3d1c472d87bbf8ee625f2d9f10e00d612561c8656ec285e7959)）
17. [Spring MVC整合FastDFS客户端实现文件上传](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ee47c28d44de0f80ef0769f7ca5357256dc08e1d9aa30eaf02c6c12a9a1dd4b0a)
18. 23种设计模式，源码、注释、使用场景（[购买](http://u.720life.cn/g/5d49be387f8da10d3acd1a25d7d4e61a71abeb56ffb940373ac7603666f32928785fd00705a596fce355fed66748250e608087fa3abbd2cef5a1b9e202720f59)）
19. [使用ETL工具Kettle的实例](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e6aa36f44e2202351d5e31f8d62d305ec20cd2db6a5f65a3e7a66472a651d63ac)
20. Git指南和分支管理策略（[购买](http://u.720life.cn/g/5d49be387f8da10d3acd1a25d7d4e61a71abeb56ffb940373ac7603666f32928291d09086983e106f645d10f0c22f5ed3457b280964a6d60366a08a6dfca1cf9)）
#### 高级篇：架构之美
21. [zookeeper原理、架构、使用场景和可视化](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ecfadb17f1c4c1dca7f53b58a2b84c96eeb9fabde14737868f33dc431aa8b5d661a2415a183b90c01ddc7949fe7c0fdcd)
22. Spring框架整合dubbo框架实现分布式服务治理（SOA架构）（[购买](http://u.720life.cn/g/5d49be387f8da10d3acd1a25d7d4e61a71abeb56ffb940373ac7603666f329289ce01d21c15849190fc232dfc2e4246ca96fe8781277b8083023462778c14163)）
23. Spring框架整合dubbox实现微服务架构（MSA架构）
24. 使用Spring Cloud实现微服务架构（MSA架构）（[购买](http://u.720life.cn/g/5d49be387f8da10d3acd1a25d7d4e61a71abeb56ffb940373ac7603666f3292857aca2517159b98ff017169568ce13ee17bcbf44b6efa397bfde6d58d1b72630)）
25. 使用jenkins+centos+git+maven搭建持续集成环境自动化部署分布式服务（[购买](http://u.720life.cn/g/5d49be387f8da10d3acd1a25d7d4e61a71abeb56ffb940373ac7603666f3292839aff2120090bea7f64234206c2aa96874db1bdc7e97187c54e5b692e39dbe58)）
26. 使用docker+compose+jenkins+gitlab+spring cloud实现微服务的编排、持续集成和动态扩容（[购买](http://u.720life.cn/g/5d49be387f8da10d3acd1a25d7d4e61a71abeb56ffb940373ac7603666f3292876896aa8bccb57f0580657cd2f8a816ef7cb04782a7d4e92fd20d2149ede3038)）
27. 使用FastDFS搭建分布式文件系统（高可用、负载均衡）（[购买](http://u.720life.cn/g/5d49be387f8da10d3acd1a25d7d4e61a71abeb56ffb940373ac7603666f329282525f6927673cca9045de24efe461d1e7394f8c839472c88297395b0e286ef27)）
28. 搭建高可用nginx集群和Tomcat负载均衡（[购买](http://u.720life.cn/g/5d49be387f8da10d3acd1a25d7d4e61a71abeb56ffb940373ac7603666f329281962236d135cb66532ebd76426018c58adf20a3da87dfb3431cdf0c7904e3d9c)）
29. 搭建可扩展的ActiveMQ高可用集群（[购买](http://u.720life.cn/g/5d49be387f8da10d3acd1a25d7d4e61a71abeb56ffb940373ac7603666f3292897d56ed914c9fe4798cad59552d1d4462186e8f35914ede461b17496b351220c)）
30. 实现Mysql数据库的主从复制、读写分离、分表分库、负载均衡和高可用（[购买](http://u.720life.cn/g/5d49be387f8da10d3acd1a25d7d4e61a71abeb56ffb940373ac7603666f329287d607634e8ef0c40ec6450c19dfc16e1ccecd79b40b19ba0f12bc68ff1c53d64)）
31. 搭建高可用redis集群实现分布式缓存（[购买](http://u.720life.cn/g/5d49be387f8da10d3acd1a25d7d4e61a71abeb56ffb940373ac7603666f32928ad0683c59f5d7d647ff1da32b66b7b860c998c3001edc1ee02fdb57d4e610a7b)）
32. [Spring整合SolrJ实现全文检索](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ee47c28d44de0f80ef0769f7ca53572567287290147f1680b3b9f66a4e0a2585e)
#### 特别篇：分布式事务和并发控制
33. 基于可靠消息最终一致性实现分布式事务（activeMQ）（[购买](http://u.720life.cn/g/5d49be387f8da10d3acd1a25d7d4e61a71abeb56ffb940373ac7603666f3292808f8214ad98a80d77e99d44901ec0324a66c6558d5cbd5d324416e968bbd6280)）
34. 使用TCC框架实现分布式事务（dubbo版）（[购买](http://u.720life.cn/g/5d49be387f8da10d3acd1a25d7d4e61a71abeb56ffb940373ac7603666f329281ccc54ed106d1f0e0b989ce2c5254445c093a168c15cc11c03d54a7ba88800d4)）
35. 使用TCC框架实现分布式事务（Spring Cloud版）（[购买](http://u.720life.cn/g/5d49be387f8da10d3acd1a25d7d4e61a71abeb56ffb940373ac7603666f32928bfd2a75d29775053c0d250482902f8d0d91ec4dd84508fdbb42b44b0cac72fd8)）
36. 决战高并发：数据库锁机制和事务隔离级别的实现（[购买](http://u.720life.cn/g/5d49be387f8da10d3acd1a25d7d4e61a71abeb56ffb940373ac7603666f329289a3eb2d3955a0894b56c19a70b5a04cc24c544a7aab70092ed6894754de7d6ac)）
37. 决战高并发：使用redis实现分布式锁（[购买](http://u.720life.cn/g/5d49be387f8da10d3acd1a25d7d4e61a71abeb56ffb940373ac7603666f329283c4bf9783f303cbcb5e03a8eb4ab909d5cfa5a9b9a7a026de76ea52d36d76d01)）
38. 决战高并发：使用zookeeper实现分布式锁（[购买](http://u.720life.cn/g/5d49be387f8da10d3acd1a25d7d4e61a71abeb56ffb940373ac7603666f329287ea2462a75a085055cd9f548a07318834ee102c19b49f3fd5725b9fb7f04eb37)）
39. 决战高并发：Java多线程编程实例（[购买](http://u.720life.cn/g/5d49be387f8da10d3acd1a25d7d4e61a71abeb56ffb940373ac7603666f32928bd3d13d30dd5b93973ae35cf8e047840d9ff6e4de3d337b24a8c7cebf347e870)）
40. 决战高并发：使用netty实现高性能NIO通信（[购买](http://u.720life.cn/g/5d49be387f8da10d3acd1a25d7d4e61a71abeb56ffb940373ac7603666f32928398d5f7216ffa09412508d13ab016f40fa621065987f36249f214abf9cb9b4cf)）

### 网店入口
[我的网店](http://u.720life.cn/g/5d49be387f8da10d3acd1a25d7d4e61a6d6eeda40130b321e210ff1eb569a01d7271e5ee320e6b6586ea20e98a37eff1f4b89b32fad09062753e706f6bef1fb2)
   


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ee4c394881c02eac76bbd9731783ffb4312d8d162bcf3577a3865132b34d424b20c3b63aba0f960b933e3c9d17528366a6209a3253729d625896697a6d1e56b82)