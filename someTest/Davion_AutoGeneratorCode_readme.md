# AGCode

 
     
 

AGCode是一个极易操作的文件/代码生成引擎，能够帮你将基础代码/文件全部自动生成，让你从繁杂的基础代码编写中彻底解放。
支持数据库所有表的批量生成，使用自定义模板，可以生成任何你需要的文件内容（如数据库设计文档等）。  
框架的开发注重操作的简便性，极易上手，已集成所有依赖包，只需导入一个jar，编写简单的配置即可使用。  


[![java](https://img.shields.io/badge/language-java-orange.svg)]()
[![jdk](https://img.shields.io/badge/jdk-1.6-green.svg)]()
[![License](http://img.shields.io/:license-apache-blue.svg)](http://www.apache.org/licenses/LICENSE-2.0.html)

* 作者：YouYuan  
* 邮箱：xiyousuiyuan#163.com  
* QQ：1265161633  

## 功能介绍  

- 提升工作效率，极大减少人工编码量。
- 生成项目开发中所有的基础代码，例如JavaBean、MyBatis映射、Dao、Service、Controller、Jsp、Html等。
- 自动生成数据库设计文档
- 框架内部提供一套基于Spring+SpringMVC+Mybatis的代码模板，生成的代码默认实现了增删改查功能，可根据Table配置实现乐观锁与逻辑删除。
- 支持自定义模板，生成任何你需要的文件内容。
- 可根据配置自动完成逻辑删除、乐观锁、区间查询、模糊查询、正则校验等功能。
- 可根据配置将字段的key-value映射进行自动转换，例如`1:男,2:女`，程序可智能解析构建转换列表。
- 全库批量生成，瞬间完成所有基础代码的编写工作。

> 默认模板只是展示AGCode的基础功能，建议参照默认模板根据自己的项目结构编写一套专属模板。

## 说明文档
[AGCode v2.2文档](http://u.720life.cn/g/1d1469e815a24931d66d81316410363118b4091c5e53fa9843bca036534a446b "AGCode v2.2说明文档") | [AGCode v2.1文档](http://u.720life.cn/g/1d1469e815a24931d66d8131641036319968a6eef2b03797e1547dc15d034de8 "AGCode v2.1说明文档") | [查看Wiki文档](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6edc97c60d7a883adec1617274d8c0ce0580f63835d99416dce0339a7a71a73755facdac8bcb67a02bad186b42a8c53346 "Wiki文档")

## 快速开始
可下载build文件夹中的jar包，参照示例即可快速上手使用。
> 请动动小手帮忙点击右上角Star \~^_^\~  谢谢！ ![Star](img/star.jpg)

### 效果展示
![使用效果](img/usingEffect.jpg)

### 示例代码
```  java
GeneratorConfig generatorConfig = new GeneratorConfig();//文件生成信息配置
generatorConfig.setAuthor("YouYuan");//作者，用于生成注释
generatorConfig.setPackageName("com.yuan");//包名
generatorConfig.setOutputPath("F:/Temp/AutoGeneratorCode/Test2.0/Jar");//设置文件输出路径

DatabaseConfig databaseConfig = new DatabaseConfig();//数据库信息配置
String dbName = "generator";//数据库名
databaseConfig.setDbUrl("jdbc:mysql://localhost:3306/" + dbName + "?useUnicode=true&characterEncoding=UTF-8&allowMultiQueries=true");//数据库连接地址
databaseConfig.setDbName(dbName);//设置数据库名
databaseConfig.setUsername("youyuan");//连接数据库的用户名，此处最好使用具有root权限的用户
databaseConfig.setPassword("123");//数据库用户密码
databaseConfig.setTablePrefix("t_");//数据库表名前缀，用于生成类时自动去除此前缀

GeneratorCode generatorCode = new GeneratorCode(databaseConfig, generatorConfig);//根据配置创建文件生成核心对象
generatorCode.batchGenerator();//全库批量生成
```

## 兼容性
|环境|支持版本|  
|------|------|
|JDK|1.6及以上版本|  
| 数据库 | MySQL 5.x、Oracle |


## 最近更新 2020-04-26
- 版本号：2.4
- 更新内容：
    - 调用generatorCode.dbDesignDoc(),自动生成数据库设计文档
    - 完善数据类型映射

## 开发计划

1. 根据配置的属性值转换列表自动生成常量列表与数据字典
2. 基于web服务器提供在线配置数据库信息生成代码的功能



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e19c66088a8fb48fe7cc57ae69a4941d2d2c547245e724b4ab4dce9f5db7c8a458c0d04ded0a10dcea80110d7e3edbd30)