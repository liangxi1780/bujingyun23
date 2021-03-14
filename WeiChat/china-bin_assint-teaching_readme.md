Java在线编译+智能对话机器人+搜题

#### 技术栈
Spring Boot、MyBatis-Plus、、thymeleaf 

![license](https://img.shields.io/badge/license-MIT-yellow.svg)

### 注意事项
[similarity](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046ed811768b8084e5990bd0a2b786a5a0012e25b258b16c203ea24c57ebf7026ad)
由于其并没有将其jar包上传至Maven官网库。

所以这里我将jar包放在 doc文件夹下的similarity-1.1.3-jar-with-dependencies.jar

并且如下命令将jar安装至本地maven仓库中：
```java
mvn install:install-file -Dfile=doc/similarity-1.1.3-jar-with-dependencies.jar -DgroupId=io.github.shibing624 -DartifactId=similarity -Dversion=1.1.3 -Dpackaging=jar 

```
pom.xml中添加如下dpednecy:
```xml
 
	 io.github.shibing624 
	 similarity 
	 1.1.3 
 
```
打包命令
```java
mvn package -Dmaven.test.skip=true
```


线上服务器后台启动运行命令
```java
nohup java -jar assint-teaching-0.0.1-SNAPSHOT.jar --spring.profiles.active=prod &
```

在线演示地址:  http://47.115.31.52:8080/front/question


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6eb03bda6f050149f6b51cc634e47af979872f80852b7d2ecc1c7a63ffbcebcdd259981866885880bbbd713bac04e4932d64db4f3b92d6e59c322461b10c01ff0b)