ParameterSerializer
===================

[![Build Status](https://travis-ci.org/TubeTK/TubeTK-ParameterSerializer.png?branch=master)](https://travis-ci.org/TubeTK/TubeTK-ParameterSerializer)

Serialization is an important technique when exploring an analysis parameter
solution space and performing reproducible research.

This is a set of classes to perform [serialization](http://u.720life.cn/g/aace67412d3c40f689b2c469b4f53b5920a49fe95d7e84973aab269e0e5a482e28568221d8460e11f451ac0e61f9abdc)
and deserialization of the parameters of [ITK](http://u.720life.cn/g/021cf6f1df1eebc3c0d780a4db921c1a) classes, i.e.,
classes that inherit from ```itk::LightObject```. Serialization does not require
code instrumentation of the target classes.  The parameters of the target class
are serialized with an archiver; the only currently implemented archiver writes
and reads [JSON](http://u.720life.cn/g/b7bdd7e4ed4956995e1854c9fc9e8a2c48a0cd637782363e33594f9d3cfb188a) files with the [JsonCpp](http://u.720life.cn/g/ec35fa9da993b074237ae61031f5e881a5d7c990348b880109de652ea76f7654)
library.

The project is currently used by [TubeTK](http://u.720life.cn/g/d095732c3486eaf60e25a1ced2408cce537401034df206b2a4fc4e3f575f9f51) and the
[SlicerExecutionModel](http://u.720life.cn/g/54145d0471d91890860f7f8463c030466fc22c38f90a6b8bf8e8607ee3e37b94a2547e06c9f77d0a2989f280fae25341).

The development of this project is supported by TubeTK.



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ee5e2d6d225394536a994de75c79ebcdb05597b89a5993b6d1a833f0de36530a8d47b38de439f89f8b68ee2a350a405a38bd5176058f339eb5f8f913f4f0a1488)