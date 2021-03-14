#MyBatis通用Mapper3

##极其方便的使用MyBatis单表的增删改查

##支持单表操作，不支持通用的多表联合查询

##优点?

通用Mapper都可以极大的方便开发人员。可以随意的按照自己的需要选择通用方法，还可以很方便的开发自己的通用方法。

##MyBatis工具网站:[http://mybatis.tk](http://u.720life.cn/g/5d88e5a59ccc688f2e74c4a956a26a21614412bd4b91ddfa786780e41f99f519)

##项目文档

###在你打算使用通用Mapper前，一定要看看下面的文档，许多人在初次使用时遇到的问题，99%都在文档中有说明！！

1. [Mapper3变化](http://u.720life.cn/g/5c954f4cd4204fb6c09a7e58aa70844d9dd92fe5a8305dae04a7e26aadecd403f827e047e6d734c548f072fb345d5db58f4e38ed2caa52874cebae35d20b2cd7ad9f8b3b6174971419889eb7298b954e)

2. [如何集成通用Mapper](http://u.720life.cn/g/5c954f4cd4204fb6c09a7e58aa70844d9dd92fe5a8305dae04a7e26aadecd403f827e047e6d734c548f072fb345d5db5188662b30f0a9c654025bb4c0b8bc12a0bd4d0ceb47ec3a124213a49998105e7)

3. [如何使用通用Mapper](http://u.720life.cn/g/5c954f4cd4204fb6c09a7e58aa70844d9dd92fe5a8305dae04a7e26aadecd403f827e047e6d734c548f072fb345d5db594fac672191cd2c052b8b77a074114f05497b7e115db7fceb344c7a28ddffe4e)

4. [高级应用](http://u.720life.cn/g/5c954f4cd4204fb6c09a7e58aa70844d9dd92fe5a8305dae04a7e26aadecd403f827e047e6d734c548f072fb345d5db5fdb7fe1c3020dce90bd578fe22dd74761b70c0f82f76854625b715ba8a216669)

5. [Mapper3通用接口大全](http://u.720life.cn/g/5c954f4cd4204fb6c09a7e58aa70844d9dd92fe5a8305dae04a7e26aadecd403f827e047e6d734c548f072fb345d5db5247f24286bff4644a10cd8804ad3d5b06544bce7d2c9f10f8193287d55b3e32e)

6. [快速开发自己的通用接口](http://u.720life.cn/g/5c954f4cd4204fb6c09a7e58aa70844d9dd92fe5a8305dae04a7e26aadecd403f827e047e6d734c548f072fb345d5db58951418244edb1a4e342f26cc9c9fa984c12b20536a2e7c6a63075b20f6511c8)

7. [如何使用Mapper专用的MyBatis Generator插件](http://u.720life.cn/g/5c954f4cd4204fb6c09a7e58aa70844d9dd92fe5a8305dae04a7e26aadecd403f827e047e6d734c548f072fb345d5db5e37901a4dd27daeb77e7c53397027cac0e771984fcc5da274f5dff1bda713ad7)

8. [在Spring4中使用通用Mapper](http://u.720life.cn/g/5c954f4cd4204fb6c09a7e58aa70844d9dd92fe5a8305dae04a7e26aadecd4035b3450e6f64c21ad9b3bd9e9ddd4e210fa51140a876666d891bab29c76f36ad928d918face138a08a71a9dd2c32fffef)

9. [Mapper3常见问题和用法](http://u.720life.cn/g/5c954f4cd4204fb6c09a7e58aa70844d9dd92fe5a8305dae04a7e26aadecd403f827e047e6d734c548f072fb345d5db5173d382f2b9d28457d559e23d853b0f7f8be8b0222fa14b51b518debad619839)

##通用Mapper - 简单用法示例

全部针对单表操作，每个实体类都需要继承通用Mapper接口来获得通用方法。

示例代码：

    CountryMapper mapper = sqlSession.getMapper(CountryMapper.class);
    //查询全部
    List  countryList = mapper.select(new Country());
    //总数
    Assert.assertEquals(183, countryList.size());

    //通用Example查询
    Example example = new Example(Country.class);
    example.createCriteria().andGreaterThan("id", 100);
    countryList = mapper.selectByExample(example);
    Assert.assertEquals(83, countryList.size());

    //MyBatis-Generator生成的Example查询
    CountryExample example2 = new CountryExample();
    example2.createCriteria().andIdGreaterThan(100);
    countryList = mapper.selectByExample(example2);
    Assert.assertEquals(83, countryList.size());

CountryMapper代码如下：

    public interface CountryMapper extends Mapper  {
    }

这里不说更具体的内容，如果您有兴趣，可以查看下面的 项目文档 

##实体类注解

从上面效果来看也能感觉出这是一种类似hibernate的用法，因此也需要实体和表对应起来，因此使用了JPA注解。更详细的内容可以看下面的 项目文档 。

Country代码：

    public class Country {
        @Id
        private Integer id;
        @Column
        private String countryname;
        private String countrycode;
        //省略setter和getter方法
    }
    
[使用Mapper专用的MyBatis Generator插件](http://u.720life.cn/g/5c954f4cd4204fb6c09a7e58aa70844d9dd92fe5a8305dae04a7e26aadecd403f827e047e6d734c548f072fb345d5db5e37901a4dd27daeb77e7c53397027cac0e771984fcc5da274f5dff1bda713ad7) 可以方便的生成这些（带注解的）实体类。

##通用Mapper支持Mybatis-3.2.4及以上版本 

##使用Maven

###重要提示,3.1.0及以后版本的groupId修改为tk.mybatis，artifactId为mapper

```xml
 
     tk.mybatis 
     mapper 
     3.1.2 
 
```

##引入Jar包，下载地址：

https://oss.sonatype.org/content/repositories/releases/tk/mybatis/mapper

http://repo1.maven.org/maven2/tk/mybatis/mapper

由于通用Mapper依赖JPA，所以还需要下载persistence-api-1.0.jar：

http://repo1.maven.org/maven2/javax/persistence/persistence-api/1.0/

##[更新日志](http://u.720life.cn/g/5c954f4cd4204fb6c09a7e58aa70844d9dd92fe5a8305dae04a7e26aadecd403f827e047e6d734c548f072fb345d5db5e81d35833eeb1ba9c7774ca7e6976383)

##Maven坐标以及下载地址

###测试版本3.1.3-SNAPSHOT- 2015-08-02

* 新增`MapperOnceInterceptor`拦截器，该拦截器执行后会自动卸载，以后不会再进入该方法，只需要将`MapperInterceptor`替换为`MapperOnceInterceptor`即可
* 大家可以尝试`MapperOnceInterceptor`拦截器，发现问题可以提issue
* 由于Spring中的`MapperHelper`的配置方式容易出现错误，因此从3.1.3以后废弃这种配置方法
* `Example`增加`andEqualTo(实体对象)`方法，可以将一个实体放进去，会自动根据属性和值拼出column=value的条件  Bob - 0haizhu0@gmail.com 提供 
* MyBatis在处理` `和`@CacheNamespace`的时候不统一，只有一个能生效，这导致xml中配置二级缓存对通用Mapper注解形式的方法无效，该问题已解决
* 二级缓存配置方法，如果接口有对应的xml，在xml中配置二级缓存。如果只有接口没有xml，用注解配置二级缓存即可
* 需要注意的是，二级缓存在xml配置时，只对通用Mapper方法有效，自己用`@Select`等注解定义的这种仍然无效，这种情况只能在xml中定义

###最新版本3.1.2 - 2015-07-14

* 解决别名时的一种特殊情况，例如`@Column(name="`desc`")`的时候，就不需要自动添加别名
* 反射获取所有列名的时候，不在自动转换为大写形式，对数据库区分大小写的情况有用

###3.1.1 - 2015-07-01

* 解决`ConditionMapper`中`selectByCondition`和`updateByCondition`方法错误

###3.1.0 - 2015-06-10

* 基础包名从`com.github.abel533`改为`tk.mybatis.mapper`
* Maven的groupId改为`tk.mybatis`,artifactId为`mapper`
* 增加和Example功能类似的Condition查询，仅仅名字不同
* 更多详细变化请看[Mapper3通用接口大全](http://u.720life.cn/g/5c954f4cd4204fb6c09a7e58aa70844d9dd92fe5a8305dae04a7e26aadecd403f827e047e6d734c548f072fb345d5db5247f24286bff4644a10cd8804ad3d5b06544bce7d2c9f10f8193287d55b3e32e)
* 关于3.0.x版本请看[Mapper3.0.x](http://u.720life.cn/g/5c954f4cd4204fb6c09a7e58aa70844d9dd92fe5a8305dae04a7e26aadecd403e02a4db478df0b68112a3ed7581ab82f511699ba5021aeb75e4c8c8732fc9b9e)

###3.0.0 - 2015-06-04

* 将`EntityMapper`和`SqlMapper`移出，现在是独立项目[EntityMapper](http://u.720life.cn/g/5c954f4cd4204fb6c09a7e58aa70844d8034bcb906f4d323ab5e10a1d69dbf27c55a64a8338cd2cdedb2fe71bbf065ba)
* 将`Mapper `全部接口方法拆分为独立接口，方便选择集成
* 增加`MySqlMapper `包含批量插入和单个插入，批量插入可以回写全部id
* 增加`RowBoundsMapper `包含两个分页查询，可以配合[PageHelper](http://u.720life.cn/g/5c954f4cd4204fb6c09a7e58aa70844d0c5e449aa2c2e2afac3f4646cf34dfd65ceb51a277771277d2a7f535bcbaead3)实现物理分页
* 详细变化请看[Mapper3变化](http://u.720life.cn/g/5c954f4cd4204fb6c09a7e58aa70844d9dd92fe5a8305dae04a7e26aadecd403f827e047e6d734c548f072fb345d5db58f4e38ed2caa52874cebae35d20b2cd7ad9f8b3b6174971419889eb7298b954e)
* Mapper2资深用户请看[Mapper3高级应用](http://u.720life.cn/g/5c954f4cd4204fb6c09a7e58aa70844d9dd92fe5a8305dae04a7e26aadecd403f827e047e6d734c548f072fb345d5db5fdb7fe1c3020dce90bd578fe22dd74761b70c0f82f76854625b715ba8a216669)
* [Mapper3通用接口大全](http://u.720life.cn/g/5c954f4cd4204fb6c09a7e58aa70844d9dd92fe5a8305dae04a7e26aadecd403f827e047e6d734c548f072fb345d5db5247f24286bff4644a10cd8804ad3d5b06544bce7d2c9f10f8193287d55b3e32e)
* [快速开发自己的通用接口](http://u.720life.cn/g/5c954f4cd4204fb6c09a7e58aa70844d9dd92fe5a8305dae04a7e26aadecd403f827e047e6d734c548f072fb345d5db58951418244edb1a4e342f26cc9c9fa984c12b20536a2e7c6a63075b20f6511c8)

##作者信息

作者博客：http://blog.csdn.net/isea533

作者邮箱： abel533@gmail.com

Mybatis工具群：    

推荐使用Mybatis分页插件:[PageHelper分页插件](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046e46d295ad2841af2558737b9b48e7f525f5d9e37bc321a699ae434b02ff50941)


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ea959c538980ba0ab5cdea0de9299102a24597c79b6e4033cef9d7ad27ea5e7851c4e6b4479598ce0f68faecd6ae4fe20)