# Mybatis 代码生成小工具

![](https://pandao.github.io/editor.md/images/logos/editormd-logo-180x180.png)

![](https://img.shields.io/github/tag/pandao/editor.md.svg)

+ ①`可视化`数据库连接配置 
+ ②自动生成service及dao层代码
> ps:支持Mapper和sqlSession两种配置风格 
+ ③代码结构简单、零依赖、可简单个性化定制 

### Usage:
```java
    git clone https://git.oschina.net/darkidiot/CodeHelper.git
    java -jar ./CodeHelper/dist/CodeHelper.jar
```
# How to Customize Your own CodeHelper?

## Code Review:
### Java:

```java
    private String getMyBatisCode(Table table, String pack, String author) throws Exception {
		String xml = Util.read(getDaoTemplateLocation());
		String daoTemplate = Util.matchs(xml, " ([\\w\\W]+?) ", 1).get(0);
        ... ... ...
        return daoTemplate.toString();
	}
```
### xml:
```xml
 
     
		#columns.mapping#
	 
    ... ... ...
	 
		#table.name#
	 
    
	 
		#id#,  
	 
    ... ... ...
	 
		SELECT
		 
		FROM
		 
		WHERE #id# = #{id}
	 
	... ... ...
	 
	    INSERT INTO 
	      ( )
	    VALUES( )
	 
	... ... ...
	 
	    UPDATE  
	     
	    	#commaIfEntrys#
	     
	    WHERE #id# = #idVal#
	 
	... ... ...
	 
		DELETE FROM  
		WHERE #id# = #{id}
	 	
 
```
#### You can modify above code for generate any code on the basis of your mind.
# End


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6eb8e012748b4ebaca389f9c1dcc354ca48e05cd20ff98b1717c6f24952a74907affb9875514aa362523cc54d43ad1e7e0)