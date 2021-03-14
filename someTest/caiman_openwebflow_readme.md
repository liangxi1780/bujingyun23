What's OpenWebFlow
===========
 

OpenWebFlow是基于Activiti（官方网站 ，代码托管在 ）扩展的工作流引擎，它扩展的功能包括：

* 完全接管了Activiti对活动（activity）权限的管理。Activiti允许在设计model的时候指定每个活动的执行权限，但是，业务系统可能需要根据实际情况动态设置这些任务的执行权限（如：动态的Group）。OpenWebFlow完全实现了与流程定义时期的解耦，即用户对活动的访问控制信息单独管理（而不是在流程定义中预先写死），这样有利于动态调整权限，详见[自定义活动权限管理](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304683dae74f47010bdd590f5a01dda26427ff7b60d31ff5445759ed5a211f669cc77b651fc90bd27085a17cf41b2988d1c93b1d48f28b05668287d4b0113fc51e81)；
* 完全接管了Activiti对用户表（IDENTITY_XXX表）的管理。在标准的工作流定义中，每个节点可以指定其候选人和候选用户组，但是比较惨的是，Activiti绑架了用户信息表的设计！这个是真正致命的，因为几乎每个业务系统都会属于自己的用户信息结构（包括User/Group/Membership），但不一定它存储在Activiti喜欢的那个库中，表的结构也不一定一样，有的时候，某些信息（如：动态的Group）压根儿就不采用表来存储。OpenWebFlow剥离了用户信息表的统一管理，客户程序可以忘掉Activiti的用户表、群组表、成员关系表，详见[自定义用户成员关系管理](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304683dae74f47010bdd590f5a01dda26427ff7b60d31ff5445759ed5a211f669cc70007add2bf3b733bd99de82380a074851addff3081bf053d71598b84059312d4e9b8b903b4ea299197448dd11ebfed2e)；
* 允许运行时定义activity！__彻底满足“中国特色”，并提供了安全的（同时也是优雅的）催办、代办、加签（包括前加签/后加签）、自由跳转（包括前进/后）、分裂节点等功能__；

如何贡献？
===========

欢迎各位同仁共同贡献新的特性，以及提交bugfix。具体操作方式是：
* fork本项目；
* 提交自己的修改（包含tests）至forked版本；
* 提交pull requests；
* pr得以审核并合并；

支持与致谢
===========

* 开发者使用帮助：https://github.com/bluejoe2008/openwebflow/wiki

* [使用手册与设计说明书（PDF格式）](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304683dae74f47010bdd590f5a01dda264275aaddbbba2ccf2e8b10c4cf87e26d3b59e3eec665ff5657b44ce4f86dc02adcf9183d6112d90aa6ac71fda034f07bd86fa0f60eecc01c087bcbfe336c031fa67cfcb3c492e4c92d4902e1aad6c96774f1d8db68b2a987c5dfa18888844e1811ff973561a6ca5700389d878dfb2e167134300cdb75894ac7ea6638f42b943a83cdf1b1a17df11a8932846336637aa401a10c4236c6217bc05ac8c8abd97e6461f5437f7c86b17f391aa04320734ddd96ac1270bd3fd50517ec84589482412c328)

感谢咖啡兔 ，里面有很多的关于Activiti应用方案的讨论。



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ec8b7db947e380018cb1e17e3e0c91781c441fe1f89bd3f8509840e55e7eb8d05c079d5afa4debdd2d7a383ab4545da00)