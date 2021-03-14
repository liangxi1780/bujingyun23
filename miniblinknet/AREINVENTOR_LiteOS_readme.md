[![Build Status](https://travis-ci.org/LiteOS/LiteOS.svg?branch=develop)](https://travis-ci.org/LiteOS/LiteOS)

## 迁移公告

欢迎大家访问LiteOS。为了提供更好的服务，本项目于2019年11月从GitHub迁出，后续代码更新、维护将在码云（https://gitee.com/LiteOS ）上进行。

Huawei LiteOS一直致力于打造易用、安全、高性能的物联网系统，项目迁入码云(Gitee)后，LiteOS开源团队将开展社区项目更新，包括丰富的组件包、新平台的支持、配套工程工具。敬请关注，期待大家的参与。

## Huawei LiteOS简介

Huawei LiteOS是华为面向物联网领域开发的一个基于实时内核的轻量级操作系统。本项目属于华为物联网操作系统[Huawei LiteOS](http://u.720life.cn/g/f5fbf1788b17d825362c29f15299ab417d1f99562fabcd0242767e7ab9658e2def1619d3aa142b73b9dcc0418f33fbc7a9f1c2481abe78a5e62974b0f22e2d3a)源码，现有基础内核支持任务管理、内存管理、时间管理、通信机制、中断管理、队列管理、事件管理、定时器等操作系统基础组件，更好地支持低功耗场景，支持tickless机制，支持定时器对齐。

同时提供端云协同能力，集成了LwM2M、CoAP、mbedtls、LwIP全套IoT互联协议栈，且在LwM2M的基础上，提供了AgentTiny模块，用户只需关注自身的应用，而不必关注LwM2M实现细节，直接使用AgentTiny封装的接口即可简单快速实现与云平台安全可靠的连接。

Huawei LiteOS自开源社区发布以来，围绕NB-IoT物联网市场从技术、生态、解决方案、商用支持等多维度使能合作伙伴，构建开源的物联网生态,目前已经聚合了30+ MCU和解决方案合作伙伴，共同推出一批开源开发套件和行业解决方案，帮助众多行业客户快速的推出物联网终端和服务，客户涵盖抄表、停车、路灯、环保、共享单车、物流等众多行业，为开发者提供 “一站式” 完整软件平台，有效降低开发门槛、缩短开发周期。

## LiteOS 代码导读

- [LiteOS内核源代码目录说明](./doc/LiteOS_Code_Info.md)

该文档描述的是LiteOS内核源代码的详细信息。通过此文档读者可以了解LiteOS的源代码结构，以及LiteOS的main()函数的功能。


## LiteOS 开发指南

[LiteOS开发指南](./doc/Huawei_LiteOS_Developer_Guide_zh.md)  

[LiteOS移植指南](http://u.720life.cn/g/0a3663cdd74b97c9f24249c9d9b8bbee939a0a63f36ea6e327bb95ee2c1f224f81fd612a60dba67323ccb21d3535c020)  

该文档详细讲解了LiteOS各模块开发及其实现原理。用户可以根据该文档学习各模块的使用。


## LiteOS 接入云平台开发指南

* [LiteOS接入华为云平台](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046d86630bbf8979b9e1e49f245f86fb5d88cda45394672adebf81b92f0306320c1)
  * [LiteOS SDK端云互通组件开发指南](./doc/Huawei_LiteOS_SDK_Developer_Guide.md)

LiteOS SDK是Huawei LiteOS软件开发工具包（Software Development Kit），通过LiteOS SDK端云互通组件，简单快速地实现与华为 OceanConnect IoT平台安全可靠连接，可以大大减少开发周期，快速构建IoT产品。

LiteOS SDK是Huawei LiteOS软件开发工具包（Software Development Kit），通过LiteOS SDK端云互通组件，简单快速地实现与华为 OceanConnect IoT平台安全可靠连接，可以大大减少开发周期，快速构建IoT产品。
* [LiteOS SDK端云互通组件Coap开发指南](./doc/Huawei_LiteOS_SDK_Coap_LwM2M_Developer_Guide_zh.md)
* [LiteOS SDK端云互通组件MQTT开发指南](./doc/Huawei_LiteOS_SDK_MQTT_Developer_Guide.md)
  

* [LiteOS接入3rd云平台](http://u.720life.cn/g/54145d0471d91890860f7f8463c030468480a9eaa3992495072b7a7fa6d4b07f94c567a68c1653d4bfc30fcef3234e0ea89fbc2af205faf1f1f95a52fdc22ee3)


## LiteOS 支持的硬件

* LiteOS开源项目目前支持ARM Cortex-M0，Cortex-M3，Cortex-M4，Cortex-M7等芯片架构

* [LiteOS支持的开发板列表](./doc/LiteOS_Supported_board_list.md)
Huawei LiteOS 联合业界主流MCU厂家，通过开发者活动，目前已经适配了30+ 通用 MCU开发套件，5套NB-IoT集成开发套件


## 开源协议

* 遵循BSD-3开源许可协议
* [Huawei LiteOS 知识产权政策](http://u.720life.cn/g/3f6bc38e6938b6711866a3ba7ee64d8049932609e312b8c2367aec0c220bb6966661449a38bc55d58c42ecbee2d018a440da712c689ab0002bba81d9620c0f62ca0d282ca023becc2583b40baa8e3fbe)

## LiteOS Git入门必读

- [LiteOS Commit Message规则](./doc/LiteOS_Commit_Message.md)

该文档描述如何提交commit到LiteOS仓库，这是LiteOS开发必须遵守的commit规则，否则提交的commit会被驳回。请点链接了解详细信息。

- [Huawei LiteOS代码贡献流程](./doc/LiteOS_Contribute_Guide_GitGUI.md)

该文档描述开发者如何创建自己的仓库，开发然后贡献代码到LiteOS仓库。请点链接了解详细信息。


## 加入我们
* 欢迎提交issue对关心的问题发起讨论，欢迎提交PR参与特性建设
* 如您有合作意向，希望加入Huawei LiteOS生态合作伙伴，请发邮件至liteos@huawei.com，或访问[LiteOS官网](http://u.720life.cn/g/13662debdef98dcf1cdfd780c9d3140c108b8e11df2a469b0704813f442eaf8e)，进一步了解详细信息




 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e565ec351664e490074a31d47495548da4c7122528088f8590fc8a3d3cf2c746c1d4d297d61b68d1d634ecca58246e4a0)