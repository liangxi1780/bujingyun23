#mybatis-generator-core
####注意:此工程是由官方版本根据自己需求的改造版本
##使用说明：
1,先进行xml文件的配置。
    修改/mybatis-generator-core/src/test/resources/generatorConfigMyBatis4.xml
    修改的内容： 
    1,数据库信息，（jdbcConnection标签进行配置） 
    2,生成的javaModel类的包名与工程的位置（javaModelGenerator标签进行配置） 
    3,生成的mapperxml文件的包名，工程的位置（sqlMapGenerator标签进行配置） 
    4,生成的mapper接口的包名，工程的位置，父接口的指定（javaClientGenerator标签进行配置） 
    5,可选配置，针对每个表进行特殊的配置(table标签) 
2,进行/mybatis-generator-core/src/test/java/org/mybatis/generator/MyBatisGeneratorTest.java
类中的testGenerateMyBatis4方法，



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e81c54d0a829bd4d5a957af351aedfbbaa196f2cb7cc219d24065525a4c171b3829b72956aa5cd0fe2acf1ce66227109a53cedf607368dc3e309efeb70c7964d3)