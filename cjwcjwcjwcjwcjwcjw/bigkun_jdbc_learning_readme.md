1. JDBC基础
2. Connection pool
3. ORM:
    1. Mybatis
    2. JPA
    3. JOOQ
4. DB 单元测试

> 大部分代码示例使用H2数据库，部分使用MySQL数据库。SQL语句完全兼容MySQL。

## 1. JDBC基础 
[JDBC Overview](http://u.720life.cn/g/8288b31f1cb278a1bdb8ffc52c99a13b3ab83ef41a964c2dcd49e5a637b2cf83f7b2cfa08939456e8453ff0b4a3cce5c6f04265aa81bde050d597360fb13e182)

JDBC API是一个用于Java与各种数据库连接的行业标准。JDBC为访问基于SQL语句的数据库提供了简单易用的API。

简单的3步：
1. 与数据库或任何一种表格化数据源建立连接
2. 发送SQL语句
3. 处理返回结果

**JDBC架构**

![](https://www.oracle.com/ocom/groups/public/@otn/documents/digitalasset/145869.gif)

JDBC API 定义了访问数据库的抽象模型：
1. Connection
2. Statement
3. ResultSet
> 以上三个是核心，当然还有很多其它的接口。

JDBC API声明了基于这个模型的各种interface, 而具体实现交由各家数据库提供商进行实现，也就是Driver.

比如MySQL:
* 驱动为: com.mysql.cj.jdbc.Driver
* Connection实现: com.mysql.cj.jdbc.ConnectionImpl
* Statement实现: com.mysql.cj.jdbc.StatementImpl
* ResultSet实现: com.mysql.cj.jdbc.result.ResultSetImpl 

JDBC并不关心数据库特性，比如连接建立细节、网络协议细节，而只是将这些过程及数据模型进行抽象。提供一套统一的适用于任何表格化数据源的API，这就是JDBC API。

JDBC API定义在：
* package java.sql : Core API, Java SE

* package javax.sql: Optional API, Java EE:

The javax.sql package provides for the following:

1. The DataSource interface as an alternative to the DriverManager for establishing a connection with a data source
2. Connection pooling and Statement pooling
3. Distributed transactions
4. Rowsets

### 驱动加载
SPI,利用ServiceLoader机制加载Classpath下所有实现java.sql.Driver的类。由此实现自动加载JDBC驱动的功能。

查看serviceloader Module学习spi。

### 分布式事务
* [xa-jta](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6edfd8d7162be0499c4e54933e9c0a75aeb9796d96d1fc8aea8009e225c0be3bc4e6b3da6ddfc89523b5af07e72043cbb7276c781b179452797876b2acbe20f40c)
分布式事务是数据库操作的中重要的技术点，JDBC以XA模型做出抽象定义。另外提供了面向J2EE的JTA接口。

javax.sql中只定义了XAConnection和XADataSource,也就是与驱动和物理连接相关的定义。
jdk中javax.transaction仅对XAResource和Xid做了声明，更丰富的定义需要引入额外的依赖包jta.jar.

JTA依赖:
````
 
     javax.transaction 
     jta 
     1.1 
 
````

在这里面定义了 Transaction、TransactionManager和UserTransaction三个核心概念。


## 2. Connection Pool 连接池
缓存是提高系统性能的不二法宝，连接池也是如此，连接池就是通过缓存物理连接，到达提供系统性能的目的。

1. [agroal](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6edfd8d7162be0499c4e54933e9c0a75aeb9796d96d1fc8aea8009e225c0be3bc45536f3b5260407cef855724a775165f5cc9c5489a1ed4807b79332c619001a73)
1. [druid](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6edfd8d7162be0499c4e54933e9c0a75aeb9796d96d1fc8aea8009e225c0be3bc45536f3b5260407cef855724a775165f51722348c1ab55dd43dde37644f4a97c7)
1. [tomcat-jdbc](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6edfd8d7162be0499c4e54933e9c0a75aeb9796d96d1fc8aea8009e225c0be3bc45536f3b5260407cef855724a775165f56dcd05becd3d40747d1cfedfe15f71bf)
1. [HikariCP](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6edfd8d7162be0499c4e54933e9c0a75aeb9796d96d1fc8aea8009e225c0be3bc45536f3b5260407cef855724a775165f5f89cc3717d861a290414a04839dd14d9)
1. [MiniConnectionPoolManager](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6edfd8d7162be0499c4e54933e9c0a75aeb9796d96d1fc8aea8009e225c0be3bc45536f3b5260407cef855724a775165f51232d898ec9cd87d517437a309a8ed477165d960c57e253976d7f35e62e31e9e)手写实现

## 3. ORM



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6edfd8d7162be0499c4e54933e9c0a75ae3184ac44bf44cd62690abda55070863d2ab65515b8256f1eebdec4388c549812)