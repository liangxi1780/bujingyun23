#Mybatis分页插件 - PageHelper

如果你也在用Mybatis，建议尝试该分页插件，这一定是 最方便 使用的分页插件。

分页插件支持任何复杂的单表、多表分页，部分特殊情况请看[重要提示](http://u.720life.cn/g/5c954f4cd4204fb6c09a7e58aa70844d0c5e449aa2c2e2afac3f4646cf34dfd6cd8036ca95950fa5bc1cebee35dca279f33f7faa7a6e9b04e5bbe064245a18b47cc6f4f62ca8e97fe5cbbd02f6af8ccceb22fd70a9acb100f667defb244e78e7)。

想要使用分页插件？请看[如何使用分页插件](http://u.720life.cn/g/5c954f4cd4204fb6c09a7e58aa70844d0c5e449aa2c2e2afac3f4646cf34dfd6cd8036ca95950fa5bc1cebee35dca279f33f7faa7a6e9b04e5bbe064245a18b4f6b78321a1c549ab6930b1fc1e8d1632ade4addcdbdf7ae57d191aa922dcdff6)。

##物理分页

该插件目前支持以下数据库的 物理分页 :

 1. `Oracle`
 2. `Mysql`
 3. `MariaDB`
 4. `SQLite`
 5. `Hsqldb`
 6. `PostgreSQL`
 7. `DB2`
 8. `SqlServer(2005,2008)`
 9. `Informix`
 10. `H2`
 11. `SqlServer2012`

配置`dialect`属性时，可以使用小写形式：

`oracle`,`mysql`,`mariadb`,`sqlite`,`hsqldb`,`postgresql`,`db2`,`sqlserver`,`informix`,`h2`,`sqlserver2012`

在4.0.0版本以后，`dialect`参数可以不配置，系统能自动识别这里提到的所有数据库。

对于不支持的数据库，可以实现`com.github.pagehelper.parser.Parser`接口，然后配置到`dialect`参数中(4.0.2版本增加)。

 特别注意： 使用SqlServer2012数据库时，需要手动指定`sqlserver2012`，否则会使用2005的方式进行分页。

##MyBatis工具网站:[http://mybatis.tk](http://u.720life.cn/g/5d88e5a59ccc688f2e74c4a956a26a21614412bd4b91ddfa786780e41f99f519)

##分页插件支持MyBatis3.2.0~3.3.0(包含)

##分页插件最新版本为4.1.6

###Maven坐标

```xml  
 
     com.github.pagehelper 
     pagehelper 
     4.1.6 
 
```  

###下载JAR包

分页插件pagehelper.jar： 

 - https://oss.sonatype.org/content/repositories/releases/com/github/pagehelper/pagehelper/
 
 - http://repo1.maven.org/maven2/com/github/pagehelper/pagehelper/

###由于使用了sql解析工具，你还需要下载jsqlparser.jar

####4.1.0及以后版本需要0.9.5版本

 - http://repo1.maven.org/maven2/com/github/jsqlparser/jsqlparser/0.9.5/

####4.1.0以前版本需要0.9.1版本

 - http://repo1.maven.org/maven2/com/github/jsqlparser/jsqlparser/0.9.1/

##4.1.7-SNAPSHOT

- 解决多个`with(nolock)`时出错的问题
- 新增`sqlCacheClass`参数，该参数可选，可以设置sql缓存实现类，默认为`SimpleCache`，当项目包含guava时，使用`GuavaCache`，也可以通过参数`sqlCacheClass`指定自己的实现类，有关详情看`com.github.pagehelper.cache`包。

##4.1.6更新日志

- 通过间接处理字符串解决SqlServer中不支持`with(nolock)`的问题#86，详情可以看`SqlServerParser`和`SqlServer2012Dialect`

##4.1.5更新日志

- 更新`PageProviderSqlSource`，支持3.4.0版本的`Provider`注解方式的分页#102
- 解决`SqlUtil`未初始化`PARAMS`属性导致的错误

##4.1.4更新日志

- 解决`closeConn`未设置时，默认值被覆盖变成`false`的问题#97
- `closeConn`不只对动态数据源有效，当没有设置`dialect`属性自动获取数据库类型的时候同样有效
- 解决关闭tomcat的时候提示线程安全问题#98，这个问题不会导致内存溢出，已经增加处理

##4.1.3更新日志

- 解决反射类没有完全捕获异常的问题#94
- 把SqlServer类所有private都改成了protected，方便继承修改#93

##4.1.2更新日志

- 增加可配参数`closeConn`，当使用动态数据源时，分页插件获取jdbcUrl后，控制是否关闭当前连接，默认`true`关闭
- count查询改为`count(0)`，分库分表情况下的效率可能更高

##4.1.1更新日志：

- 解决动态数据源时获取连接后未关闭的严重bug#80
- 解决动态数据源时SqlSource和parser绑定导致不能切换方言的问题

##4.1.0更新日志：

- 增加`autoRuntimeDialect`参数，允许在运行时根据多数据源自动识别对应方言的分页（暂时不支持自动选择`sqlserver2012`，只能使用`sqlserver`）。
- 去掉了4.0.3版本增加的`returnPageInfo`参数，接口返回值不支持`PageInfo`类型，可以使用下面`ISelect`中演示的方法获取
- 增加对`SqlServer2012`的支持，需要手动指定`dialect=sqlserver2012`，否则会使用2005的方式进行分页
- jsqlparser升级到0.9.4版本，使用jar包时必须用最新的0.9.4版本，使用Maven会自动依赖0.9.4
- 增加`ISelect`接口，方便调用，使用方法可以参考`src/test/java/com.github.pagehelper.test.basic.TestISelect`测试。

##项目文档[wiki](http://u.720life.cn/g/5c954f4cd4204fb6c09a7e58aa70844d0c5e449aa2c2e2afac3f4646cf34dfd6713cfe3eb3806054ee93eb2ba56e2ce9af30ef2b289f039fbb344a66ce93fbb8)：  

###[如何使用分页插件](http://u.720life.cn/g/5c954f4cd4204fb6c09a7e58aa70844d0c5e449aa2c2e2afac3f4646cf34dfd6cd8036ca95950fa5bc1cebee35dca279f33f7faa7a6e9b04e5bbe064245a18b4f6b78321a1c549ab6930b1fc1e8d1632ade4addcdbdf7ae57d191aa922dcdff6)

如果要使用分页插件，这篇文档一定要看，看完肯定没有问题。

如果和Spring集成不熟悉，可以参考下面两个MyBatis和Spring集成的框架

 只有基础的配置信息，没有任何现成的功能，作为新手入门搭建框架的基础 

- [集成Spring3.x](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046d54b23dc3d5f744c73f4566c677890018e6e8137bdee06951dc46d03a40ae7c8)

- [集成Spring4.x](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046d54b23dc3d5f744c73f4566c6778900161b5b6480f7a113f61a0c21766999133666c75872c40a60d9830adf387fad1a9)

这两个集成框架集成了MyBatis分页插件和MyBatis通用Mapper。

###[如何使用排序插件](http://u.720life.cn/g/5c954f4cd4204fb6c09a7e58aa70844d0c5e449aa2c2e2afac3f4646cf34dfd6cd8036ca95950fa5bc1cebee35dca279f33f7faa7a6e9b04e5bbe064245a18b4a1147a7cc467fd1d3cd36c3f7fa63895)

###[更新日志](http://u.720life.cn/g/5c954f4cd4204fb6c09a7e58aa70844d0c5e449aa2c2e2afac3f4646cf34dfd6cd8036ca95950fa5bc1cebee35dca279f33f7faa7a6e9b04e5bbe064245a18b49e88c8e805d18f4a9b56a791f4359c774d4e867305b0621cf61c192d15bc4c68)

包含全部的详细的更新日志。

###[重要提示](http://u.720life.cn/g/5c954f4cd4204fb6c09a7e58aa70844d0c5e449aa2c2e2afac3f4646cf34dfd6cd8036ca95950fa5bc1cebee35dca279f33f7faa7a6e9b04e5bbe064245a18b47cc6f4f62ca8e97fe5cbbd02f6af8ccceb22fd70a9acb100f667defb244e78e7)

提示很重要，建议一定看一遍！

###[提交(gitosc)BUG](http://u.720life.cn/g/5c954f4cd4204fb6c09a7e58aa70844d0c5e449aa2c2e2afac3f4646cf34dfd6e66e3b46c5d1825232955d9b2078d108c63a70e52e673fee375d7b96e5bf7e6c42dd5877bb4956e918030adc530517b482877e64a4b40087bdb9e3736e330111e62018b09b22ef937a9b026c8eae14dd)

##相关链接

对应于oschub的项目地址：http://git.oschina.net/free/Mybatis_PageHelper

对应于github的项目地址：https://github.com/pagehelper/Mybatis-PageHelper

Mybatis-Sample（分页插件测试项目）：[http://git.oschina.net/free/Mybatis-Sample](http://u.720life.cn/g/5c954f4cd4204fb6c09a7e58aa70844d0c5e449aa2c2e2afac3f4646cf34dfd61d41ac1cc27ddb714f2600b0f66f6039)

Mybatis项目：https://github.com/mybatis/mybatis-3

Mybatis文档：http://mybatis.github.io/mybatis-3/zh/index.html  

Mybatis专栏： 

- [Mybatis示例](http://u.720life.cn/g/5997fd1f539dfbe7c9c67736234755a40d6c2bdde572de36ca3d61451785e5b0b99e34d53da874ee7dc3dd662bb525934a2cbd3d0f66a3dc3cc316d0583d3659)

- [Mybatis问题集](http://u.720life.cn/g/5997fd1f539dfbe7c9c67736234755a40d6c2bdde572de36ca3d61451785e5b0644900a5e3922a8ad710ae8bbac54af4e60fac0d3842f27886c99de0b137c539)  

作者博客：  

- http://my.oschina.net/flags/blog

- http://blog.csdn.net/isea533   

作者邮箱： abel533@gmail.com  

Mybatis工具群：    


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ea7dcc0c4d965696839fcc55540907afd3e0299f541325cc3a27361a96795e28f9a8fcc4f5489c93f1e5bef01722acbc6)