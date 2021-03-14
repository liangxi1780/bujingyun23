# fastmybatis

fastmybatis是一个mybatis开发框架，目的为简化mybatis的开发，让开发更高效。

- 零配置快速上手
- 无需编写xml文件即可完成CRUD操作
- 支持mysql，sqlserver，oracle，postgresql,sqlite
- 支持自定义sql，sql语句可以写在配置文件中，同样支持mybatis标签
- 支持与spring-boot集成
- 轻量级，无侵入性，可与传统mybatis用法共存

[fastmybatis与MyBatis generator对比](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e4b08ba06f843570db01a97d3c5a4364791ab7bd9e097bcad597ea0ecb9c16066d00014eca95c4e943ccb4038dbf5d80d6834316ae687862dd668301c2e66932207eaa2b3d56835214f14160f644d38bbbd397411deb8ce5d15f7d67a921cd4e602c1cb4132b48aaf75ce6daf5518b71a)

# 快速开始（springboot）

- 新建一个springboot项目
- pom.xml添加fastmybatis-spring-boot-starter

```
 
     net.oschina.durcframework 
     fastmybatis-spring-boot-starter 
     1.0.2 
 
```
- 假设数据库有张`t_user`表，添加对应的实体类`TUser.java`和Mapper`TUserMapper.java`
- 在`application.propertis`中配置数据库连接
- 编写测试用例

```
@Autowired
TUserMapper mapper;
    
// 根据主键查询
@Test
public void testGetById() {
    TUser user = mapper.getById(3);
    System.out.println(user);
}
```

# Mapper方法列表

```
/**
 * 根据对象查询,可以传主键值,也可以传整个对象
 * 
 * @param id
 * @return 返回实体对象，没有返回null
 */
Entity getById(ID id);

/**
 * 根据条件查找单条记录
 * @param query 查询条件
 * @return 返回实体对象，没有返回null
 */
Entity getByQuery(@Param("query")Query query);

/**
 * 根据字段查询一条记录
 * @param column 数据库字段名
 * @param value 字段值
 * @return 返回实体对象，没有返回null
 */
Entity getByColumn(@Param("column")String column,@Param("value")Object value);

/**
 * 查询总记录数
 * 
 * @param query 查询条件
 * @return 返回总记录数
 */
long getCount(@Param("query")Query query);  

/**
 * 根据字段查询集合
 * @param column 数据库字段名
 * @param value 字段值
 * @return 返回实体对象集合，没有返回空集合
 */
List  listByColumn(@Param("column")String column,@Param("value")Object value);

/**
 * 条件查询
 * 
 * @param query 查询条件
 * @return 返回实体对象集合，没有返回空集合
 */
List  list(@Param("query")Query query);

/**
 * 查询指定字段结果
 * @param columns 返回的字段
 * @param query 查询条件
 * @return 返回结果集
 */
List > listMap(@Param("columns")List  columns, @Param("query")Query query);

/**
 * 新增,新增所有字段
 * 
 * @param entity
 * @return 受影响行数
 */
int save(Entity entity);

/**
 * 新增（忽略null数据）
 * @param entity
 * @return 受影响行数
 */
int saveIgnoreNull(Entity entity);

/**
 * 批量添加,只支持mysql,sqlserver2008及以上数据库. 
 *  若要兼容其它版本数据库,请使用saveMulti()方法 
 * @param entitys
 * @return
 */
int saveBatch(@Param("entitys")List  entitys);

/**
 * 批量添加,兼容更多的数据库版本. 
 * 此方式采用union all的方式批量insert,如果是mysql或sqlserver2008及以上推荐saveBatch()方法.
 * @param entitys
 * @return
 */
int saveMulti(@Param("entitys")List  entitys);

/**
 * 修改,修改所有字段
 * 
 * @param entity
 * @return 受影响行数
 */
int update(Entity entity);

/**
 * 根据主键更新不为null的字段
 * 
 * @param entity
 * @return 受影响行数
 */
int updateIgnoreNull(Entity entity);

/**
 * 根据条件批量更新
 * 
 * @param entity 待更新的数据，可以是实体类，也可以是Map{@literal }
 * @param query 更新条件
 * @return 受影响行数
 */
int updateByQuery(@Param("entity") Object entity, @Param("query") Query query);

/**
 * 删除
 * 
 * @param entity
 * @return 受影响行数
 */
int delete(Entity entity);

/**
 * 根据id删除
 * 
 * @param id 主键id
 * @return 受影响行数
 */
int deleteById(ID id);

/**
 * 根据条件删除
 * 
 * @param query
 * @return 受影响行数
 */
int deleteByQuery(@Param("query")Query query);
```

# Query查询对象

```
查询姓名为张三，并且年龄为22岁的用户：
Query query = new Query().eq("username","张三").eq("age",22);
List  users = mapper.list(query);

查询年龄为10,20,30的用户：
Query query = new Query().in("age",Arrays.asList(10,20,30));
List  users = mapper.list(query);

查询注册日期大于2017-11-11的用户：
Date regDate = ...
Query query = new Query().gt("reg_date",regDate);
List  users = mapper.list(query);

查询性别为男的，年龄大于等于20岁的用户，按年龄降序：
Query query = new Query().eq("gender",1).ge("age",20).orderby("age",Sort.DESC);
List  users = mapper.list(query);

分页查询：
Query query = new Query().eq("age",10).page(1,10); // 第一页，每页10条数据
List  users = mapper.list(query);

查询总记录数：
Query query = new Query().eq("age",10).page(1,10); // 第一页，每页10条数据
long total = mapper.getCount(query); // 该条件下总记录数
```

- 完整的测试用例，[点击前往](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e4b08ba06f843570db01a97d3c5a4364791ab7bd9e097bcad597ea0ecb9c16066f0a9da6eee3d38c07181ea1c1954d890dab69b241988461cb7daece8bb54286514cc1209394ac2e572e2a849d60dc81ff03a121962c22e336c94c3cf2f124d191968e7c7e35d5fe702b43405f8be451c)

# 工程介绍

- [fastmybatis-core](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e4b08ba06f843570db01a97d3c5a43647753b5fb75a80bd499e4fb0f56ce741368e0f2a6f0d7fd9d9ce9236fb01570f87c27cc24b5aa166031add66a003cc2c6c)：框架源代码
- [fastmybatis-demo](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e4b08ba06f843570db01a97d3c5a43647753b5fb75a80bd499e4fb0f56ce741368e0f2a6f0d7fd9d9ce9236fb01570f87f3b9fbef8244d859c2493617e4e3e23e)：对应demo
- [fastmybatis-generator](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e4b08ba06f843570db01a97d3c5a43647753b5fb75a80bd499e4fb0f56ce741368e0f2a6f0d7fd9d9ce9236fb01570f87535e3e91ca62c8e57a7b2ccc6151c590)：代码生成工具，方便生成实体类和Mapper（可生成lombok风格实体类）
- [fastmybatis-spring-boot-autoconfigure](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e4b08ba06f843570db01a97d3c5a43647753b5fb75a80bd499e4fb0f56ce741368e0f2a6f0d7fd9d9ce9236fb01570f87c5dae2705cb3e2498f115d45302202dec3868a955ef32dbc3e9d26e991584717)和[fastmybatis-spring-boot-starter]https://gitee.com/durcframework/fastmybatis/tree/master/fastmybatis-spring-boot-starter

# 实战项目

[easydoc](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e4b08ba06f843570db01a97d3c5a436473f9b0526a207f3b3df1a4e489d68d5ba) : 一个文档管理项目，采用markdown方式写作。

# 意见交流

Q群328419269


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6eebe700435cbdcba18baddee4abcc716a99ec754d7e9a374f80c606e2be539d6ea239ad5df0dc840ae8f33fe4e2fd17f2)