   
2018年9月22日，在2018杭州云栖大会上，召开《码出高效：Java 开发手册》新书发布会，并宣布将图书所有收益均捐赠于技术公益项目“83行代码计划”。

阿里巴巴正式在2018杭州云栖大会《开发者生态峰会》上，由阿里巴巴高年级同学中间件负责人林昊、阿里巴巴研究员刘湘雯、阿里巴研究员刘国华，OpenJDK社区Committer杨晓峰，全栈视障工程师蔡勇斌，电子工业出版社博文视点出版公司总经理郭立以及两位图书作者杨冠宝（孤尽）和高海慧（鸣莎）重磅大咖联合发布新书[《码出高效：Java开发手册》（跳转至天猫书店）](http://u.720life.cn/g/568275b94ff6aa052a7eaf5bfdb5b9186a504668b665fbc6b4fa6403efe5355d3c11940309cc6f1ccd09e179fadf41da1468953ff6c93ca2083e26eb271107fbd541e44137e91ee54816299a985e1b70a655e93f199bd1625711c474701d4cb37429ffcef4b533b2cc80cde6d13e8ca2941deb522688b096be3625fb6bb8395c)，并宣布将图书所有收益均捐赠于技术公益项目“83行代码计划”，第一个“83行代码计划”行动，将围绕着帮助盲人工程师，开发更多无障碍化产品，让盲人上网更便捷。未来，我们会坚持用技术为公益行业赋能，也希望更多人成为技术受益者 公有云>设置->测试服务->阿里巴巴Java代码规约）。

# P3C

[![License](https://img.shields.io/badge/license-Apache%202-4EB1BA.svg)](https://www.apache.org/licenses/LICENSE-2.0.html)

##  Preface 
> We are pleased to present Alibaba Java Coding Guidelines which consolidates the best programming practices over the years from Alibaba Group's technical teams. A vast number of Java programming teams impose demanding requirements on code quality across projects as we encourage reuse and better understanding of each other's programs. We have seen many programming problems in the past. For example, defective database table structures and index designs may cause software architecture flaws and performance risks. Another example is confusing code structures being difficult to maintain. Furthermore, vulnerable code without authentication is prone to hackers’ attacks. To address these kinds of problems, we developed this document for Java developers at Alibaba.
 
For more information please refer the *Alibaba Java Coding Guidelines*:
- 中文版: *[阿里巴巴Java开发手册](http://u.720life.cn/g/54145d0471d91890860f7f8463c030467aa285c9bae0117ec341161b2cbcd5c0d7617690a34d82254981ec177765ed0d7bc6c67bd18285b314a2e70c072ba11aa370e95bde9b1ea8d7bb15743004bd1f3ae2ab7ddf4285f860ac0e9064995141494776682e4b08885afbdc0321dca07a801e747d21e93157ae4894bcd37217087e873e550c3d92e3b0e5cc9d43929af8620513178c61b6a4ed46dfead7a004f8fecd6bbb514e58f2a8095c815d0570ce)*
- English Version: *[Alibaba Java Coding Guidelines](http://u.720life.cn/g/eff6dbe5c0981d8621a9099c954de83f34954e903914b258e652cc3fe8396c8fed565b2329bbf1d7e731ee165a6e02b41c0f611e87c702842b0f11bc58a69231)*
- 《阿里巴巴Java开发手册》书籍版天猫官方店: *[阿里巴巴Java开发手册最新版](http://u.720life.cn/g/568275b94ff6aa052a7eaf5bfdb5b9186a504668b665fbc6b4fa6403efe5355ddf28461f18450f46412fed2a18bb00520ec14ea3ce4153d311fa5bb749d3aa1834d23c23d7f7f06341f7faee01024d67f66904702c83d2fe24fe3ce95c5a2242e45e6c0a835f6be1be47f63988b878d1)*
- 《码出高效》书籍版天猫官方店: *[码出高效：Java开发手册](http://u.720life.cn/g/568275b94ff6aa052a7eaf5bfdb5b9186a504668b665fbc6b4fa6403efe5355db5287e74661700f249d03b7507a49dfac132ce4c707be500bf32f9ad1dc8ed4895598bddd51abe3b9b6e54d5065d16b01d40e1275cde9412eb0cb07c58f0d73a9bbffcf26d4cbdb712191f0f10ab7b1b)*

##  Introduction 
The project consists of 3 parts:  
- [PMD implementations](p3c-pmd)  
- [IntelliJ IDEA plugin](idea-plugin)  
- [Eclipse plugin](eclipse-plugin)   

##  Rules 
 Forty-nine rules are realized based on PMD, please refer the P3C-PMD documentation for more detailed information. Four rules are implemented within IDE plugins (IDEA and Eclipse) as follows:   

- ``[Mandatory]`` Using a deprecated class or method is prohibited.  
   Note: For example, decode(String source, String encode) should be used instead of the deprecated method decode(String encodeStr). Once an interface has been deprecated, the interface provider has the obligation to provide a new one. At the same time, client programmers have the obligation to check out what its new implementation is.
   
- ``[Mandatory]`` An overridden method from an interface or abstract class must be marked with @Override annotation.
   Counter example: For getObject() and get0bject(), the first one has a letter 'O', and the second one has a number '0'. To accurately determine whether the overriding is successful, an @Override annotation is necessary. Meanwhile, once the method signature in the abstract class is changed, the implementation class will report a compile-time error immediately.
   
- ``[Mandatory]`` A static field or method should be directly referred by its class name instead of its corresponding object name.

- ``[Mandatory]`` The usage of hashCode and equals should follow:
    1. Override hashCode if equals is overridden.
    2. These two methods must be overridden for Set since they are used to ensure that no duplicate object will be inserted in Set.
    3. These two methods must be overridden if self-defined object is used as the key of Map.
   Note: String can be used as the key of Map since these two methods have been rewritten.

## Join us
If you have any questions or comments, please contact junlie by email at caikang.ck@alibaba-inc.com, and please join us to make project P3C perfect for more programmers.

Please follow our WeChat official account as ali_yunxiao below:

![](https://gw.alicdn.com/tfscom/TB1TrNcXjv85uJjSZFNXXcJApXa.png)



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e14ee28bf7160dec863fefc1c9f4ee152465d7035eb5d882e7f485086a12a419a883486e61efff485398e1cba766ea7ec)