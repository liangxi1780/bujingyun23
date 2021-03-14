#EDAS
例子编写是参考EDAS_DEVELOPER_GUIDE.pdf文档配置的。原文档为2个项目，为了能更好体现接口的耦合度， 
我拆分成三个项目分别是：Edas_service_provider 、Edas_hsf_web、Edad_api。
1）Edas_service_provider是服务的提供者。目录如下图。SampleServiceImpl是具体的实现类。这个项目需要把Edad_api项目作为依赖加入进来。

访问地址：
http://localhost:8010/hsf.htm?params=custom1


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6eba313cc4b5024fefa29906411af92684c9e54aa261b71d853688c889b4634d5f1973246a06778971d9790abf4868a6eb)