Introduction
==========

Snaker-Struts2项目主要是基于struts2、spring3、mybatis3、snaker框架整合的一个最基本的流程管理模块，方便大家轻松地完成流程引擎的整合

###整合步骤

####1).依赖包整合

```java
    cglib-nodep-2.2.jar
	commons-beanutils-1.8.3.jar
	commons-lang-2.5.jar
	jackson-core-asl-1.9.4.jar
	jackson-mapper-asl-1.9.4.jar
	slf4j-api-1.7.2.jar
    joda-time-2.3.jar
	snaker-core-*.*.*.jar
    snaker-hibernate-*.*.*.jar
    snaker-spring-*.*.*.jar
    commons-dbutils-1.5.jar
    juel-impl-2.1.2.jar[可选-使用Juel表达式引擎时需要,Spring框架项目,建议使用SpelExpression]
    slf4j-log4j12-1.7.2.jar[可选-使用log4j日志时需要]
```

maven项目可直接添加依赖

```xml
	 
		 com.github.snakerflow 
		 snaker-core 
		 ${snaker.version} 
	 
	 
		 com.github.snakerflow 
		 snaker-spring 
		 ${snaker.version} 
	 
	 
		 com.github.snakerflow 
		 snaker-mybatis 
		 ${snaker.version} 
	 
```

####2).流程引擎配置

增加snaker的spring配置文件

```xml
     
     

    	 SnakerEngine配置  
    	 
    		 
    		 
    		 
    		 
    		 
    	 

		 
			 
		 

    	 
    		 
    		 
    	 
    	 
    		 
    	 
    	 
    		 
    	 
    	 
    		 
    	 
    	 
    		 
    	 

    	 
    	 
    	 
    	 
     
```

配置事务[注意：事务配置会影响流程引擎的数据处理]

```xml
     
	 
		 
	 

	 
		 
			 
			 
			 
			 
			 
			 
			 
			 
			 
			 
			 
			 
			 
			 
			 

 			 
			 
			 
			 
			 
			 
		 
	 

	 
		 
	 
	 
```

####3).辅助工具类
```java
	//流程引擎api的简易封装
	com.snakerflow.examples.struts2.engine.SnakerEngineFacets.java
    //页面状态图使用json数据展现，通过此类构造json数据
    com.snakerflow.examples.struts2.engine.SnakerHelper.java
```

####4).流程定义整合

前端页面整合，可以将应用中的jsp页面copy，替换自己项目的样式即可
```java
    processList.jsp//流程定义查询列表页面
    processEdit.jsp//流程定义编辑页面,一般可编辑状态、类别、重新上传流程定义文件
    processDesigner.jsp//流程定义的web设计器,需要依赖设计器的js、css等
    processDeploy.jsp//流程定义部署页面,只提供一个文件上传控件,上传流程定义的xml文件
    processView.jsp//流程定义查看页面,用于查看流程状态图及历史任务记录
    actor.jsp//动态添加参与者页面
    diagram.jsp//流程定义的状态图
```

后台服务整合
```java
    com.snakerflow.examples.struts2.web.snaker.ProcessAction.java
```

Web设计器整合
```java
    styles\js\snaker 文件夹
    styles\js\jquery-ui-1.8.4.custom
    styles\js\raphael-min.js
```

####5).待办、协办、抄送、历史任务整合

前端页面整合
```java
	activeTask.jsp//待办任务页面(主办、协办、抄送)
    activeTaskMore.jsp//待办任务列表页面
    activeCCMore.jsp//抄送列表页面
    historyTask.jsp//历史任务列表页面
```

后台服务整合
```java
	com.snakerflow.examples.struts2.web.snaker.TaskAction.java
```

####6).流程实例整合

前端页面整合
```java
	order.jsp//流程实例列表页面
```

后台服务整合
```java
	com.snakerflow.examples.struts2.web.snaker.FlowAction.java
```

####7).委托代理功能整合

前端页面整合
```java
	surrogateList.jsp//委托代理列表页面
    surrogateEdit.jsp//新增委托代理页面
    surrogateView.jsp//查看委托代理页面
```

后台服务整合
```java
	com.snakerflow.examples.struts2.web.snaker.SurrogateAction.java
```


Contact
-----
* Snaker群号：293568574
* snakerflow:  

Wiki
----
* Snaker: 

License
-----
Apache License Version 2.0  





 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e5211a68cdbfd025310c21a8fe11c23d82f19114c46acf270f6c4ef02cde4aac88e44da8809b203b81a61ae64a13b5f0b74be3798595718bfc6151291dabd9ad6)