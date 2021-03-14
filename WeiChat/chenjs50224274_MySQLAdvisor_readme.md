### 一、简介

MySQLAdvisor是原SQLAdvisor项目转移到此，原先由美团点评公司技术工程部DBA团队（北京）开发维护的一个分析SQL给出索引优化建议的工具，现在由社区进行维护、迭代更新。它基于MySQL原生态词法解析，结合分析SQL中的where条件、聚合条件、多表Join关系 给出索引优化建议。**目前SQLAdvisor在美团点评内部广泛应用，公司内部对SQLAdvisor的开发全面转到github上，开源和内部使用保持一致**。

**主要功能：输出SQL索引优化建议**

### 二、MySQLAdvisor详细说明

1. [MySQLAdvisor快速入门教程](./doc/QUICK_START.md)
2. [MySQLAdvisor架构和实践](./doc/THEORY_PRACTICES.md)
3. [MySQLAdvisor release notes](./doc/RELEASE_NOTES.md)
4. [MySQLAdvisor开发规范](./doc/DEVELOPMENT_NORM.md)
5. [FAQ](./doc/FAQ.md)

### 三、Changelog

增加了可以按照分号分隔分析多条sql的功能;

修复了部分bug;

### 四、MySQLAdvisor的需求及Bug反馈方式

如果用户在实际的应用场景中对MySQLAdvisor有新的功能需求，或者在使用MySQLAdvisor的过程中发现了bug，在github上进行交流或是PullRequest，也可以在讨论组/群进行反馈，我们会及时维护。

**QQ群号：947480182**

![QQ](./doc/img/qq.png)



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e093b8419594023376995052459cdd1d23a103ded5d3ddf7f3454865613fc3e3067651df67ab18c617fc6ffcfad91dd02c181dead682b54960559118339f9584a)