#Castle-Platform

本人承诺该项目完全开源，不会有任何的收费计划。

> 关于我，欢迎关注   
  博客：[ken的博客](http://u.720life.cn/g/e99042548806045f747a41cd07e645dd1ea71630edce5f3b03dfc9dbd0347586)  
  点击链接加入群【castle平台交流】：http://jq.qq.com/?_wv=1027&k=40qMCqb

Castle Platform的目标是打造一个高性能、高扩展性的java开发平台，完成通用的管理功能。采用了后台管理集中部署，会员业务系统可分离部署等特点，可独立区分后台管理系统、前端展示系统、用户中心系统。开发者可以在此基础上进行扩展，进而使用一个核心就可以开发出各种互联网产品。 

####示例
- 初始学习与建立工程：[castle-example](http://u.720life.cn/g/54145d0471d91890860f7f8463c030461ba971993f55286ae6f6b54317b4a8a58e4c96d3d2ac67364cd137248d81da87)
- 简单的前端实例：[当凌科技官网](http://u.720life.cn/g/e971ffc9d57a7ce2e0f3a1aaca0640a565da893ea9fb073e3211c1515f2c51c5)
- 分布式实例：[移动城堡](http://u.720life.cn/g/ee9a89bd72d5ca188c6fb4cd365e9b48d2e395460fb4ae346ab7ebbbfcecf76f)
- 一站式实例：[床垫材料前台](http://u.720life.cn/g/d172a9bef549e636b3baa0713a9ada42ee55d0f8d092cb4e37184253425f99f4) | [床垫材料后台管理](http://u.720life.cn/g/d172a9bef549e636b3baa0713a9ada4209d45269706d77b6900d10ca59b4282f)
- 国际化实例：[金惠丰英文](http://u.720life.cn/g/4b89dc748f59dc8c446938273a1a0716ed41a9de0714a932abb2f173c7ed0df5) | [金惠丰中文](http://u.720life.cn/g/91b2943825b578c3a6a77102536b4d8420a828352fb07b5a3ab305eee5e1fbfb)

###特性
- 基于目前最新最热门的java技术
- 采用Java8的语法
- 采用servlet3.1规范的集成机制
- 模块可扩展。直接添加或移除对应模块的jar即可。
- 采用spring javaconfig。 达到零spring配置文件。
- 支持多种数据操作混用
- 采用querydsl通用查询
- 包含通用的后台管理
- 可以采用单一服务集成，也可选择地使用第三方服务管理框架（支持dubbo或thrift）。
- 支持javaconfig和kryo序列化的dubbo
- 支持国际化

###原理说明
采用Dubbo等第三方RMI框架，把业务处理放置于多个Provider， Web服务作为Consumer，对Provider进行调用，从而达到分布式部署。 
![Alt framework](http://ken.whenling.com/img/castle/frame.jpg)

###集成的第三方框架
- spring-mvc（MVC框架）
- spring-security（安全框架）
- spring-data（通用数据处理）
- querydsl（通用查询框架）
- jackson（json处理框架）
- infinispan（分布式缓存）
- jpa（关系数据库）
- redis（键值数据库）
- mongodb（文档数据库）
- neo4j（图形数据库）
- groovy-template（碎片化模板）
- thymeleaf（前端模板）
- extjs6（js组件框架）
- dubbo（分布式服务框架）
- thrift（异构系统服务调用框架）

###项目依赖关系
![Alt framework](http://ken.whenling.com/img/castle/framework.jpg)

###使用方法
[http://ken.whenling.com/2016/04/24/castle/](http://u.720life.cn/g/e99042548806045f747a41cd07e645dd726cf90c5f2d92ddeada1de03349f4279956ef7273f931552bddc424d5f87d13)

###维护计划
- bootstrap管理后台
- 通用权限管理
- 手机app集成
- spring webservice
- 文件集中式存储
- 分布式计算

## License
[Apache License Version 2.0](http://u.720life.cn/g/54145d0471d91890860f7f8463c030461ba971993f55286ae6f6b54317b4a8a55d82b0f4db7c5234ca2879dfa35cfde317df5be9d8a81a5711e372995d4ac0e8)



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e09846c70bc5b5754b07e206aefece4005c1efeca18f9def2b904093d9c9445f57eb74031bea96de91acf9400ec815cfd)