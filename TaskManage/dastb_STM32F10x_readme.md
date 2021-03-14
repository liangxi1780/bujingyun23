# STM32F407ZET6

#### 介绍
STM32F103的开发基础，C++

#### 软件架构
软件由4个主要目录构成
```
├─Drivers
├─startup
├─System
└─User
其中Drivers是外设驱动所在，包括I2C、USART等单片机资源，也包括如LCD12864等外部设备
startup目录是单片机的启动文件所在，项目中必须包含仅一个启动文件，启动文件必须与单片机对应
System目录是单片机系统必须的及广泛使用的基础组件，如系统时钟和复位RCC、独立实时时钟RTC，基础定义、常用函数和头文件包含等sys
User是用户功能实现的集中体现
```
#### 安装教程

可查看Document里的文档说明

#### 使用说明

UV5以上Keil项目，以下的可能不支持

#### 参与贡献



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e9497cc625b4ede3a887ea43e5e2cae3b37dfb68d7fcd987e731e514a1c4cd52a703591c91bc5a0bdf3a306a6251989ac)