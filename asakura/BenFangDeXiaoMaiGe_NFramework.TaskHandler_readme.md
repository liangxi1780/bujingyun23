# NFramework.TaskHandler
基于消息队列的任务处理框架（待完成）

## 背景

ERP：
* 大数据量
* 批量操作
* 特定组织之间无关联，操作无影响
* 同一组织机构操作需顺序执行，以保证结果的正确性

基于此背景开发此任务处理框架（或者叫消息处理框架）

## 框架时序图

![框架时序图](/resource/nframeworksequencediagram.png)

## 架构图

![框架架构图](/resource/arch.png)

## 框架特点
* 可水平扩展
* 单队列无并发
* 开发方便，不需要线程知识也能开发多线程处理程序
* 无特定依赖（目前只强依赖log4net，后面解耦）
* 提供Redis队列实现
* 路由机制（可自定义路由规则）


## ToDO
* log4net解耦
* TaskQueueCount、TaskQueueType以及RedisAppName 整合为Setting，每个单独任务 有单独的Setting
* 文档整理


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e04bbee15cc4f1a61bd8d5323f3cc64f4b95bd521273fec21544efb5eba7aed2ba81717c8c37bacf08b2f05b19d84f8d29cdf2fa13c385db114bee8c03f2cec24ee47fd74623a1115faef89cc907a5f11)