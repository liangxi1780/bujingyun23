# Spring-activiti
  在常用的ERP系统、OA系统的开发中，工作流引擎是一个必不可少的工具。本项目旨在基于Spring这一平台，整合业界流行的工作流引擎Activiti，并建立了两个完整的工作流进行演示：请假OA和采购流程。

其中包含的内容如下：

1.不采用activiti自带的用户、角色功能，因为过于简单，转而自行实现一个用户、角色、权限的三级结构，用户到角色，角色到权限均为多对多映射，持久层框架使用mybatis的collection和association标签嵌套实现；

2.使用默认的用户登录后（用户名xiaomi，密码1234），可看到已部署好的两个流程，请假OA和采购流程，其中，请假OA包含了用户任务、排他网关、起始结束事件，较为简单；采购流程除此之外，还使用了异常结束事件、子流程和边界事件的使用；

3.两个流程均包含了待办任务签收、运行流程进度追踪、已运行完流程历史记录查看的功能，运行流程进度在流程图中以红色标注；

4.使用时，将流程数据和业务数据相分离，使用业务号（businessKey）建立关联流程数据和业务数据的桥梁，使其相互可以访问,业务数据的主键即为业务号；

5.本系统所有表单均使用普通表单，而不是activiti的动态表单和外置表单，这样做是为了分表存放业务数据和流程数据;

6.系统前端采用基于Bootstrap的模板devoops建立。https://github.com/shenzhanwang/devoops

7.起始页面入口：http://localhost:8080/Spring-activiti/login
使用前，编译(可直接在myeclipse完成)：
```
mvn clean install
```
8.效果图：

![输入图片说明](https://images.gitee.com/uploads/images/2018/1211/082825_ac69fdda_1110335.gif "SSM.gif")
![输入图片说明](https://images.gitee.com/uploads/images/2018/1211/091443_9ebd78b8_1110335.gif "user.gif")
![输入图片说明](http://git.oschina.net/uploads/images/2016/1116/081734_f50ccb20_1110335.jpeg "在这里输入图片标题")
![输入图片说明](http://git.oschina.net/uploads/images/2016/1116/081747_e412ab52_1110335.jpeg "在这里输入图片标题")
![输入图片说明](http://git.oschina.net/uploads/images/2016/1116/081802_2f2bf64c_1110335.jpeg "在这里输入图片标题")
![输入图片说明](http://git.oschina.net/uploads/images/2016/1116/081810_cbd63187_1110335.jpeg "在这里输入图片标题")
![输入图片说明](http://git.oschina.net/uploads/images/2016/1116/081820_97a18226_1110335.jpeg "在这里输入图片标题")
![输入图片说明](http://git.oschina.net/uploads/images/2016/1116/081830_8767776b_1110335.jpeg "在这里输入图片标题")

### 附录：个人作品索引目录（持续更新）

#### 基础篇:职业化，从做好OA系统开始
1. [SpringMVC,Mybatis,Spring三大框架的整合实现增删改查](https://gitee.com/shenzhanwang/SSM)![输入图片说明](https://img.shields.io/badge/-%E7%B2%BE%E5%93%81-orange.svg "在这里输入图片标题")
2. [Struts2,Hibernate,Spring三大框架的整合实现增删改查](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ee47c28d44de0f80ef0769f7ca5357256f41b457f53f752eee8a79c949e3bccb5)
3. [Spring,SpringMVC和Hibernate的整合实现增删改查](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ee47c28d44de0f80ef0769f7ca5357256673d1cf49d64c37bed5a9badf9e06386)
4. [Spring平台整合activiti工作流引擎实现OA开发](https://gitee.com/shenzhanwang/Spring-activiti)![输入图片说明](https://img.shields.io/badge/-%E7%B2%BE%E5%93%81-orange.svg "在这里输入图片标题")
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
15. [Spring整合websocket实现即时通讯](https://gitee.com/shenzhanwang/Spring-websocket)![输入图片说明](https://img.shields.io/badge/-%E7%B2%BE%E5%93%81-orange.svg "在这里输入图片标题")
16. 使用Spring boot整合mybatis,rabbitmq,redis,mongodb实现增删改查（[购买](http://u.720life.cn/g/5d49be387f8da10d3acd1a25d7d4e61a71abeb56ffb940373ac7603666f32928ab485fa33792d3d1c472d87bbf8ee625f2d9f10e00d612561c8656ec285e7959)）
17. [Spring MVC整合FastDFS客户端实现文件上传](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ee47c28d44de0f80ef0769f7ca5357256dc08e1d9aa30eaf02c6c12a9a1dd4b0a)
18. 23种设计模式，源码、注释、使用场景（[购买](http://u.720life.cn/g/5d49be387f8da10d3acd1a25d7d4e61a71abeb56ffb940373ac7603666f32928785fd00705a596fce355fed66748250e608087fa3abbd2cef5a1b9e202720f59)）
19. [使用ETL工具Kettle的实例](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e6aa36f44e2202351d5e31f8d62d305ec20cd2db6a5f65a3e7a66472a651d63ac)
20. Git指南和分支管理策略（[购买](http://u.720life.cn/g/5d49be387f8da10d3acd1a25d7d4e61a71abeb56ffb940373ac7603666f32928291d09086983e106f645d10f0c22f5ed3457b280964a6d60366a08a6dfca1cf9)）
21. 使用数据仓库进行OLAP数据分析（Mysql+Kettle+Zeppelin）（[购买](https://www.fageka.com/store/item/s/id/malQqky4959.html)）![输入图片说明](https://img.shields.io/badge/-%E7%B2%BE%E5%93%81-orange.svg "在这里输入图片标题")
#### 高级篇：架构之美
22. [zookeeper原理、架构、使用场景和可视化](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ecfadb17f1c4c1dca7f53b58a2b84c96eeb9fabde14737868f33dc431aa8b5d661a2415a183b90c01ddc7949fe7c0fdcd)
23. Spring框架整合dubbo框架实现分布式服务治理（SOA架构）（[购买](https://www.fageka.com/store/item/s/id/tTEHOF42241.html)）![输入图片说明](https://img.shields.io/badge/-%E7%B2%BE%E5%93%81-orange.svg "在这里输入图片标题")
24. 使用Spring Cloud实现微服务架构（MSA架构）（[购买](https://www.fageka.com/store/item/s/id/5T5cEY80304.html)）![输入图片说明](https://img.shields.io/badge/-%E7%B2%BE%E5%93%81-orange.svg "在这里输入图片标题")
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
36. 决战高并发：数据库锁机制和事务隔离级别的实现（[购买](https://www.fageka.com/store/item/s/id/Xvk7DZI2400.html)）![输入图片说明](https://img.shields.io/badge/-%E7%B2%BE%E5%93%81-orange.svg "在这里输入图片标题")
37. 决战高并发：使用redis实现分布式锁（[购买](https://www.fageka.com/store/item/s/id/uFQStQ61656.html)）![输入图片说明](https://img.shields.io/badge/-%E7%B2%BE%E5%93%81-orange.svg "在这里输入图片标题")
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

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e7b0cd3a5efe07678b706197d75f01cac347f7ae9017ca2bdd908cdb2feaf5142c51f76f947738b2bafce2017ef40535e)