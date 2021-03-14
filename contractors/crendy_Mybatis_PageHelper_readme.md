#Mybatis分页插件 - PageHelper说明  
   

#重大项目改动

为了便于本项目的统一管理和发布，本项目会和github上面同步，项目会改为Maven管理的结构。有关的基本测试内容都在本项目中，Mybatis-Sample项目只会保留Web方面的测试。  

由于测试类过多，会对测试类进行更合理的分组。并且会逐步增加mysql和oracle的测试。

#最新测试版3.3.0-SNAPSHOT

听取[@hlevel][1]的建议和[@da老虎](http://u.720life.cn/g/b56a32676c52deea69b3fa6af7eae60287ebe983c448364bcba109be0707f25b)的建议，对分页插件性能做了优化。  

##3.3.0-SNAPSHOT版本的改进内容

 1. 对`MappedStatement`对象进行缓存，包括count查询的`MappedStatement`以及分页查询的`MappedStatement`，分页查询改为预编译查询。

 2. 对count查询进行优化处理，目前的处理策略只是简单的把sql中的所有`order by`语句删除了，当然不是直接处理字符串去删除，使用了一个sql解析的类库，由于sql的有无限的变化，因而不保证这个sql解析的类库能够完全处理所有的情况，无法处理的情况仍然会保留order by进行查询。  

 3. 增强的PageInfo类，PageInfo类包含了分页几乎所有需要用到的属性值。方便通过一个PageInfo类来达到分页目的，减少对分页逻辑的过多投入。  

 4. 分页合理化，自动处理pageNum的异常情况。例如当pageNum pages(总页数)时，自动将pageNum=pages，查询最后一页。  

 5. 特殊的pageSize值，当pageSize 
如果你使用的maven，你可以添加如下依赖：  
```xml  
 
     com.github.pagehelper 
     pagehelper 
     3.3.0-SNAPSHOT 
 
 
 
     com.foundationdb 
     fdb-sql-parser 
     1.3.0 
 
```  


---------------------
 

#最新稳定版为3.2.3 版  

如果你也在用Mybatis，建议尝试该分页插件，这个一定是 最方便 使用的分页插件。  

该插件目前支持`Oracle`,`Mysql`,`Hsqldb`三种数据库分页。  


##使用方法  

将本插件中的`com.github.pagehelper`包下面的两个类`Page.java`和`PageHelper.java`放到项目中，如果需要使用`PageInfo.java`，也可以放到项目中。    

如果你想使用本项目的jar包而不是直接引入类，你可以在这里下载各个版本的jar包（点击Download下的jar即可下载）：  

http://search.maven.org/#search%7Cgav%7C1%7Cg%3A%22com.github.pagehelper%22%20AND%20a%3A%22pagehelper%22  

或者如果你使用Maven，你可以添加如下依赖：  

```xml
 
     com.github.pagehelper 
     pagehelper 
     3.2.3 
 
```

然后在Mybatis的配置xml中配置拦截器插件:    
```xml
 
 
     
	 
         
         
         
         
         
         
         
         
         
         
         
         
         pages会查询最后一页 -->
         pages会返回空数据 -->
         
	 
 
```   
这里的`com.github.pagehelper.PageHelper`使用完整的类路径。  

其他三个参数说明：

1. 增加`dialect`属性，使用时必须指定该属性，可选值为`oracle`,`mysql`,`hsqldb`, 没有默认值，必须指定该属性 。  

2. 增加`offsetAsPageNum`属性，默认值为`false`，使用默认值时不需要增加该配置，需要设为`true`时，需要配置该参数。当该参数设置为`true`时，使用`RowBounds`分页时，会将`offset`参数当成`pageNum`使用，可以用页码和页面大小两个参数进行分页。  

3. 增加`rowBoundsWithCount`属性，默认值为`false`，使用默认值时不需要增加该配置，需要设为`true`时，需要配置该参数。当该参数设置为`true`时，使用`RowBounds`分页会进行count查询。  

4. 增加`pageSizeZero`属性，默认值为`false`，使用默认值时不需要增加该配置，需要设为`true`时，需要配置该参数。当该参数设置为`true`时，如果`pageSize=0`或者`RowBounds.limit = 0`就会查询出全部的结果（相当于没有执行分页查询，但是返回结果仍然是`Page`类型）。  

5. 增加`reasonable`属性，默认值为`false`，使用默认值时不需要增加该配置，需要设为`true`时，需要配置该参数。具体作用请看上面配置文件中的注释内容。  

##分页示例：
```java
@Test
public void testPageHelperByStartPage() throws Exception {
    String logip = "";
    String username = "super";
    String loginDate = "";
    String exitDate = null;
    String logerr = null;
    //不进行count查询，第三个参数设为false
    PageHelper.startPage(1, 10, false);
    //返回结果是Page      
    //该对象除了包含返回结果外，还包含了分页信息，可以直接按List使用
    List  logs = sysLoginLogMapper
            .findSysLoginLog(logip, username, loginDate, exitDate, logerr);
    Assert.assertEquals(10, logs.size());

    //当第三个参数没有或者为true的时候，进行count查询
    PageHelper.startPage(2, 10);
    //返回结果是Page      
    //该对象除了包含返回结果外，还包含了分页信息，可以直接按List使用
    Page  page = (Page ) sysLoginLogMapper
            .findSysLoginLog(logip, username, loginDate, exitDate, logerr);
    Assert.assertEquals(10, page.getResult().size());
    //进行count查询，返回结果total>0
    Assert.assertTrue(page.getTotal() > 0);
}
```  
因为新增了一个Mybatis-Sample项目，所以这里的示例只是简短的一部分，需要更丰富的示例，请查看[Mybatis-Sample][3]项目  


 
##Mybatis-Sample项目 

这个项目是一个分页插件的测试项目，使用Maven构建，该项目目前提供了4种基本使用方式的测试用例，需要测试Mybatis分页插件的可以clone该项目。该项目使用了maven配置的该分页插件。

项目地址：[http://git.oschina.net/free/Mybatis-Sample][4]

 

##对于两种分页方式如何选择   

1. 如果你不想在Mapper方法上增加一个带`RowBounds`参数的方法，并且你喜欢用Mapper接口形式调用，你可以使用`PageHelper.startPage`，并且该方法可以控制是否执行count方法。  

2. 实际上在Mapper接口中添加一个带`RowBounds`参数的方法很容易，使用和不带`RowBounds`参数一样的xml就可以。  

3. 如果你喜欢使用`sqlSession.selectList`这种命名空间方式的调用，使用`RowBounds`会更方便。


  
##相关链接

Mybatis-Sample（分页插件测试项目）：[http://git.oschina.net/free/Mybatis-Sample][5]

Mybatis项目：https://github.com/mybatis/mybatis-3

Mybatis文档：http://mybatis.github.io/mybatis-3/zh/index.html  

Mybatis专栏： 

- [Mybatis示例][6]

- [Mybatis问题集][7]  

作者博客：  

- [http://my.oschina.net/flags/blog][8]

- [http://blog.csdn.net/isea533][9]  

  
##更新日志   

###v3.2.3  

1. 解决`mysql`带有`for update`时分页错误的问题。  

2. 当`pageSize`（或`RowBounds`的`limit`）` 进行封装，方便EL使用。

3. 将`SystemMetaObject`类的`fromObject`方法内置到分页插件中，方便低版本的Mybatis使用该插件。   

###v3.2.1

1. 新增`offsetAsPageNum`参数，用来控制`RowBounds`中的`offset`是否作为`pageNum`使用，`pageNum`和`startPage`中的含义相同，`pageNum`是页码。该参数默认为`false`，使用默认值时，不需要配置该参数。

2. 新增`rowBoundsWithCount`参数，用来控制使用`RowBounds`时是否执行`count`查询。该参数默认为`false`，使用默认值时，不需要配置该参数。

###v3.2.0

1. 增加了对`Hsqldb`的支持，主要目的是为了方便测试使用`Hsqldb`  

2. 增加了该项目的一个测试项目[Mybatis-Sample][10]，测试项目数据库使用`Hsqldb`  

3. 增加MIT协议

###v3.1.2

1. 解决count sql在`oracle`中的错误

###v3.1.1 
 
1. 统一返回值为`Page `（可以直接按`List`使用）,方便在页面使用EL表达式，如`${page.pageNum}`,`${page.total}`     
   
###v3.1.0
  
1. 解决了`RowBounds`分页的严重BUG，原先会在物理分页基础上进行内存分页导致严重错误，已修复  

2. 增加对MySql的支持，该支持由[鲁家宁][11]增加。  
  
###v3.0 
 
1. 现在支持两种形式的分页，使用`PageHelper.startPage`方法或者使用`RowBounds`参数   

2. `PageHelper.startPage`方法修改，原先的`startPage(int pageNum, int pageSize)`默认求count，新增的`startPage(int pageNum, int pageSize, boolean count)`设置`count=false`可以不执行count查询  

3. 移除`endPage`方法，现在本地变量`localPage`改为取出后清空本地变量。  

4. 修改`Page `类，继承`ArrayList `  

5. 关于两种形式的调用，请看示例代码   
    
###v2.1    

1. 解决并发异常  

2. 分页sql改为直接拼sql    

###v2.0  

1. 支持Mybatis缓存，count和分页同时支持（二者同步）  

2. 修改拦截器签名，拦截`Executor`

3. 将`Page `类移到外面，方便调用

###v1.0  

1. 支持` `等标签的分页查询  

2. 提供便捷的使用方式  


  [1]: http://my.oschina.net/hlevel
  [2]: http://git.oschina.net/free/Mybatis-Sample
  [3]: http://git.oschina.net/free/Mybatis-Sample
  [4]: http://git.oschina.net/free/Mybatis-Sample
  [5]: http://git.oschina.net/free/Mybatis-Sample
  [6]: http://blog.csdn.net/column/details/mybatis-sample.html
  [7]: http://blog.csdn.net/column/details/mybatisqa.html
  [8]: http://my.oschina.net/flags/blog
  [9]: http://blog.csdn.net/isea533
  [10]: http://git.oschina.net/free/Mybatis-Sample
  [11]: http://my.oschina.net/lujianing


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e0014fe4da9f618f515393ee82d0338df456a0e3ba86880889d49cfb74e373a2f8d8d30202f51a5a8806a0632c81ae569fd657933172f663eeafe9461aa36dc54)