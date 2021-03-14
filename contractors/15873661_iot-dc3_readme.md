:boom: 非常欢迎广大兴趣爱好者的加入，第一时间 [联系作者](#6-联系作者)，`show me you code`，让我们肩并肩 :alien:！
>
:rocket: 说明：项目目前处于代码整合阶段（其他功能初版已完成，正在进行协议的整合），敬请关注，你的 `Star` :star: [ [GitHub](http://u.720life.cn/g/54145d0471d91890860f7f8463c030466805347467b944927fc1ea4dcb2eaf65b32cdae8a800c7628ebfc5b63534a973) , [Gitee](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6eaf3bd1f19e2736b3ab08694e5d73c641) ]，是我们动力的源泉，谢谢你们 :tada:！

 
      
       
        
	   
	   
	   
	   	
	  DC3是基于Spring Cloud的开源可分布式物联网(IOT)平台,用于快速开发、部署物联设备接入项目,是一整套物联系统解决方案。 IOT DC3 is an open source, distributed Internet of Things (IOT) platform based on Spring Cloud. It is used for rapid development of IOT projects and management of IOT devices. It is a set of solutions for IOT system. 
 

------

### 1 什么是DC3 IOT平台？

 ![iot-dc3-architecture](dc3/images/iot-dc3-architecture1.jpg)

#### DC3设计模块

 * [x] 设备微服务层:用于提供标准或者私有协议连接物理设备的`SDK`;
 * [x] 核心微服务层:用于提供微服务注册中心、设备指令接口、设备注册与关联配对、数据管理中心,是所有微服务交互的核心部分;
 * [ ] 支持微服务层:用于提供任务调度、报警与消息通知、日志管理;
 * [x] 开放微服务层:用于提供数据开放等服务...

#### DC3设计

 * [x] 可伸缩:水平可伸缩的平台,构建使用领先的`Spring Cloud`开源技术;
 * [x] 容错:没有单点故障弱,集群中的每个节点是相同的;
 * [x] 健壮和高效:单一服务器节点可以处理甚至数百成千上万的设备根据用例;
 * [x] 可定制:添加新的设备协议,并注册到服务中心;
 * [x] 跨平台:使用`Java`环境可异地、分布式多平台部署;
 * [ ] 完善性:设备快速接入、注册、权限校验;
 * [ ] 安全:数据加密传输;
 * [x] Docker:容器化。

### 2 DC3 IOT平台架构？

DC3 平台是基于`Spring Cloud`架构开发的,是一系列松耦合、开源的微服务集合。
微服务集合由4个微服务层和两个增强的基础系统服务组成,提供从物理域数据采集到信息域数据处理等一系列的服务。

![iot-dc3-architecture](dc3/images/iot-dc3-architecture2.jpg)

[`Spring Cloud Netflix`](http://u.720life.cn/g/484d775526c71402f16d1f30e64380d7cc584a736ba73bded688b81b39b4e399c4c596ee95dc2f10ea312b5e412f5ce5)、[`Spring Cloud Gateway`](http://u.720life.cn/g/484d775526c71402f16d1f30e64380d7cc584a736ba73bded688b81b39b4e399f37583cfa23809ac935a8528de463069)、[`Spring Cloud Security`](http://u.720life.cn/g/484d775526c71402f16d1f30e64380d7cc584a736ba73bded688b81b39b4e399347bd84aac3af20a9d8ad4f1e3774f3f)、[`Spring Cloud OpenFeign`](http://u.720life.cn/g/484d775526c71402f16d1f30e64380d7cc584a736ba73bded688b81b39b4e399a126417f688f25c5ffc9051277f96860) 等微服务模块。

### 3 项目文档

详细说明内容请阅读 [`WiKi`](http://u.720life.cn/g/54145d0471d91890860f7f8463c030466805347467b944927fc1ea4dcb2eaf6515c130109382677214aec48625b0eda1) 文档。

**其中包括：安装配置文档、部署文档、项目结构说明、平台介绍等内容。**

### 4 Demo [一个简单的平台应用]

**注：DC3 Web UI 是基于DC3开发的前端应用界面，仅供开发环境&demo演示环境的配置使用，该UI不属于DC3项目的一部分**

 
  
 

一键启动Demo，按照以下三行命令进行操作即可（另外也可以参考详细的 [安装部署](http://u.720life.cn/g/54145d0471d91890860f7f8463c030466805347467b944927fc1ea4dcb2eaf65c070fd0c0840659359c1e4d43267fe3d45a8f47c4f94ba4d44c9e17acfd715188398e268fd491d671751432677ed1877) 文档），首次启动需要下载镜像会比较慢（可在`docker`中配置国内加速源:`http://f1361db2.m.daocloud.io`,如何配置加速源，可参考[如何配置镜像加速？](http://u.720life.cn/g/54145d0471d91890860f7f8463c030466805347467b944927fc1ea4dcb2eaf655b71a859351a812bfe8382fb64a0ecfe47b832d5257db71d2b7e1ef409d79147)），执行完访问 [https://localhost](http://u.720life.cn/g/5da3423f7096f513efa8032aff66538cb25be58c0b4b290e068a7adca3e68234) `是https哈`，切换到 '数据' 菜单即可查看 Virtual 驱动定时采集的模拟数据 。

> 必须保证提前安装了 `docker`和`docker-compose`

```bash
# git clone
git clone https://github.com/pnoker/iot-dc3.git

# cd
cd iot-dc3/dc3

# docker compose up
docker-compose -f docker-compose-demo.yml up -d
```

### 5 联系作者

:whale2: 邮箱:pnokers@icloud.com

:speech_balloon: 微信:peter-no

*平时工作较忙，回复不及时，请谅解*

**:mega: 非常欢迎**
 - 提交`issue`，请标明遇到的问题、开发环境和如何复现；
 - 提交`pull request`改进 `iot-dc3` 的代码；
 - 提出新想法和设计方案；
 - 参与平台贡献,通过以下二维码加入微信交流群。

 
  
 

:lollipop: 感谢:`lombok`、`netty`、`spring boot`、`spring cloud`、[`s7connector`](http://u.720life.cn/g/54145d0471d91890860f7f8463c030469ca0d34378415d442dfe8567d85e74fd4ca25010f687769a196a88b95fff1db4) 等提供的工具以及源码。

### 6 大家关心的问题

- 版权？

> Apache License Version 2.0

- 合作？

> pnokers@icloud.com

- 项目目前开发到什么阶段了？

> 完全情况：70% \
> 其中: \
> 网关服务 需要完善开发，驱动协议需要丰富（包括Mqtt,Opcua,Opcda）\
> 管理配置服务 需要优化（接口部分做小改动）\
> 数据存储&开放服务 需要添加流式计算模块（后期支持）\
> 驱动快速开发SDK模块 需要拓展功能（后期支持边缘计算）

- 项目目前支持的协议有哪些？

> 已完成的协议驱动：rtmp、plcs7、socket（client模式、server模式）、opcda \
> 计划开发协议驱动: mqtt、opcua、modbus-tcp

- 并发能力如何？

> 16G,i5机器可目前测试可承受5万并发（测试工具jMeter），目前Mongo数据库当并发很大时有较大的延时，后期采用Cassandra替代Mongo。

- Demo的镜像pull超时或报错？

> 可以配置加速源，请参考 [如何配置镜像加速？](http://u.720life.cn/g/54145d0471d91890860f7f8463c030466805347467b944927fc1ea4dcb2eaf655b71a859351a812bfe8382fb64a0ecfe47b832d5257db71d2b7e1ef409d79147) 进行配置。


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e430123ab4d9314c63168274bd218dfd79e294517708d7ed5653ab9299206cc70b103a6b771c635097a11b73e86f4e0e7)