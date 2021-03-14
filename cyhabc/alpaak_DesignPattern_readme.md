# 设计模式代码示例

本人正在写 设计模式系列文章，此处为演示源码；

博客园地址：http://www.cnblogs.com/JsonShare/category/1016618.html

CSDN地址：https://blog.csdn.net/Json_wangqiang/column/info/31929

#### 索引目录&&传送门

总体来说设计模式分为三大类：

创建型模式（5种）： 
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[单例模式](http://u.720life.cn/g/94c1d8931f8bedcd3eeaf8cdeb6a662fba498e81aedba544e59abe5ce047c573e04a07e9a439077d5da8c4204d41a693) 
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[工厂方法模式](http://u.720life.cn/g/94c1d8931f8bedcd3eeaf8cdeb6a662fba498e81aedba544e59abe5ce047c573e1cd4a8919aa193dbdb45c84a3a5aaf9) 
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[抽象工厂模式](http://u.720life.cn/g/94c1d8931f8bedcd3eeaf8cdeb6a662fba498e81aedba544e59abe5ce047c573e1cd4a8919aa193dbdb45c84a3a5aaf9) 
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[建造者模式](http://u.720life.cn/g/94c1d8931f8bedcd3eeaf8cdeb6a662fba498e81aedba544e59abe5ce047c5734274fca296f29f3122b8b9e27c5e8e65) 
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[原型模式](http://u.720life.cn/g/94c1d8931f8bedcd3eeaf8cdeb6a662fba498e81aedba544e59abe5ce047c57394832d5e0095ff58d079222acb41ce25) 

结构型模式（7种）： 
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[适配器模式](http://u.720life.cn/g/94c1d8931f8bedcd3eeaf8cdeb6a662fba498e81aedba544e59abe5ce047c573228007ffa82a34b8f6561ca4d60d9e71) 
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[装饰者模式](http://u.720life.cn/g/94c1d8931f8bedcd3eeaf8cdeb6a662fba498e81aedba544e59abe5ce047c573832871e5c18a7cf96b79c2b37df7693b) 
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[代理模式](http://u.720life.cn/g/94c1d8931f8bedcd3eeaf8cdeb6a662fba498e81aedba544e59abe5ce047c5738072f05e3fe5b366afeb5e691a6d2510) 
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[外观模式](http://u.720life.cn/g/94c1d8931f8bedcd3eeaf8cdeb6a662fba498e81aedba544e59abe5ce047c5737f05364afd7effe0d924dae71e729271) 
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[桥接模式](http://u.720life.cn/g/94c1d8931f8bedcd3eeaf8cdeb6a662fba498e81aedba544e59abe5ce047c5731a9384a7a21eaf9676b4b276afa5e315) 
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[组合模式](http://u.720life.cn/g/94c1d8931f8bedcd3eeaf8cdeb6a662fba498e81aedba544e59abe5ce047c573238eea3c04e810575052173a6822c2ee) 
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[享元模式](http://u.720life.cn/g/94c1d8931f8bedcd3eeaf8cdeb6a662fba498e81aedba544e59abe5ce047c573d880c54b790f01d68e3a801a1f01d8ba) 

行为型模式（11种）： 
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[策略模式](http://u.720life.cn/g/94c1d8931f8bedcd3eeaf8cdeb6a662fba498e81aedba544e59abe5ce047c573354409129b2e702768f37da24257fd67) 
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[模板方法模式](http://u.720life.cn/g/94c1d8931f8bedcd3eeaf8cdeb6a662fba498e81aedba544e59abe5ce047c5739a8778c56d72c8172cabbc07adb3092f) 
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[观察者模式](http://u.720life.cn/g/94c1d8931f8bedcd3eeaf8cdeb6a662fba498e81aedba544e59abe5ce047c573215e2ed6ecd7788d5e87e10ff5fcc912) 
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[迭代器模式](http://u.720life.cn/g/94c1d8931f8bedcd3eeaf8cdeb6a662fba498e81aedba544e59abe5ce047c5730d1876b93f847cfa5df73a036901bb1b) 
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[责任链模式](http://u.720life.cn/g/94c1d8931f8bedcd3eeaf8cdeb6a662fba498e81aedba544e59abe5ce047c573514b6528e31c1d3efb7ad8ab48cfa5fe) 
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[命令模式](http://u.720life.cn/g/94c1d8931f8bedcd3eeaf8cdeb6a662fba498e81aedba544e59abe5ce047c573ee590391099d62093d35b9106fb81575) 
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[备忘录模式](http://u.720life.cn/g/94c1d8931f8bedcd3eeaf8cdeb6a662fba498e81aedba544e59abe5ce047c573fa989fcf228ec636079b713086f3cf07) 
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[状态模式](http://u.720life.cn/g/94c1d8931f8bedcd3eeaf8cdeb6a662fba498e81aedba544e59abe5ce047c573e5902a4c6866630b43945f4e7acaa4af) 
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[访问者模式](http://u.720life.cn/g/94c1d8931f8bedcd3eeaf8cdeb6a662fba498e81aedba544e59abe5ce047c57346137015037d33ff14359a6532d8422c) 
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[中介者模式](http://u.720life.cn/g/94c1d8931f8bedcd3eeaf8cdeb6a662fba498e81aedba544e59abe5ce047c573ccf11ee55ac94cabdc6a89d6ab829b31) 
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[解释器模式](http://u.720life.cn/g/94c1d8931f8bedcd3eeaf8cdeb6a662fba498e81aedba544e59abe5ce047c573d6af38b7fdfb1642d74ff8e746bdf68c) 

#### 设计模式结构图

![image](https://github.com/JsonShare/DesignPattern/raw/master/Images/summary.png)




 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e68a67a2bbe6ce9bbaebb93cee861364988e45a12f028c1e8cd99350315963c90fcfe86a62f39cce04d7264b4e76cf401)