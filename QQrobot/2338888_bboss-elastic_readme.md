# Elasticsearch Bboss

Bboss is a good elasticsearch Java rest client. It operates and accesses elasticsearch in a way similar to mybatis.

 

# Environmental requirements

JDK requirement: JDK 1.7+

Elasticsearch version requirements: 1.X,2.X,5.X,6.X,7.x,+

Spring booter 1.x,2.x,+

# Build from source code
First Get source code from https://github.com/bbossgroups/bboss-elasticsearch

Then change to cmd window under directory bboss-elasticsearch and run gradle build command：

```
gradle install
```

Gradle environmenet install and config document: https://esdoc.bbossgroups.com/#/bboss-build

# How to use Elasticsearch BBoss.

First add the maven dependency of BBoss to your pom.xml:

```xml
        
             com.bbossgroups.plugins 
             bboss-elasticsearch-rest-jdbc 
             5.8.0 
         
```

If it's a spring boot project, you can replace the Maven coordinate above with the following Maven coordinate:

```xml
         
             com.bbossgroups.plugins 
             bboss-elasticsearch-spring-boot-starter 
             5.8.0 
         
```



Next, add the Elasticsearch addresses to the application.properties file under the project resource directory, and create a new one if the file does not exist:

```properties
elasticsearch.rest.hostNames=10.21.20.168:9200

#Cluster addresses are separated by commas

#elasticsearch.rest.hostNames=10.180.211.27:9200,10.180.211.28:9200,10.180.211.29:9200
```
And last  create a jsp file named testElasticsearch.jsp :

```jsp
 
 
 
 
 
 
 
 
 
  esDatas = clientUtil.searchAll("twitter", Map.class);

	//Get All documents of indice twitter,Set fetchsize to 10000, Using ScrollHandler to process each batch of datas.
	clientUtil.searchAll("twitter",10000,new ScrollHandler () {
		public void handle(ESDatas  esDatas, HandlerInfo handlerInfo) throws Exception {
			List  dataList = esDatas.getDatas();
			System.out.println("TotalSize:"+esDatas.getTotalSize());
			if(dataList != null) {
				System.out.println("dataList.size:" + dataList.size());
			}
			else
			{
				System.out.println("dataList.size:0");
			}
			//do something other such as do a db query.
			//SQLExecutor.queryList(Map.class,"select * from td_sm_user");
		}
	},Map.class);
    //Use slice parallel scoll query all documents of indice  twitter by 2 thread tasks. DEFAULT_FETCHSIZE is 5000
	//You can also use ScrollHandler to process each batch of datas on your own.
	esDatas = clientUtil.searchAllParallel("twitter", Map.class,2);
	out.println("searchAllParallel:ok");
%>

```

Put the file into the web project that has been connected to pinpoint, run the program, log on pinpoint to see the execution effect of bboss plugin.

# Elasticsearch Java Demos
The following Demo and related documentation is compatible with Elasticsearch 1.x,2.X,5.X,6.X,+ versions
## Elasticsearch demo for Java project:
https://github.com/bbossgroups/elasticsearch-example
## Elasticsearch demo for spring booter 1.x,2.x
https://github.com/bbossgroups/es_bboss_web

https://github.com/bbossgroups/elasticsearch-springboot-example

# Fast integration bboss documentation
[Spring boot integration ElasticSearch case sharing](http://u.720life.cn/g/bdfed60ac96df14f4323fd5d12d9f4146649f61567e95d27e943f77f4bad4502881dc6921f0c2359fde991541aa050cb4770d1687c2ede7cf41ec52fe594995f)

[Quickly integrate Elasticsearch Restful API case sharing](http://u.720life.cn/g/bdfed60ac96df14f4323fd5d12d9f4146649f61567e95d27e943f77f4bad45020d4e7999c18bd2fdeddee74b7684d18c964d12455e9bb1de8a02d314a4a802a9)

[Quick Start](http://u.720life.cn/g/bdfed60ac96df14f4323fd5d12d9f4146649f61567e95d27e943f77f4bad45027f67f1fb32eb5d0880c0866251651376)

# Elasticsearch BBoss Developer Tutorial

[High-performance elasticsearch ORM library bboss use introduction](http://u.720life.cn/g/bdfed60ac96df14f4323fd5d12d9f4146649f61567e95d27e943f77f4bad450241a4d29b717e9a4a5abf5ce648270fa9)

 

## Elasticsearch技术交流群:166471282 

## Elasticsearch微信公众号:bbossgroup   
![GitHub Logo](https://static.oschina.net/uploads/space/2017/0617/094201_QhWs_94045.jpg)

## License

The BBoss Framework is released under version 2.0 of the [Apache License][].

[Apache License]: http://www.apache.org/licenses/LICENSE-2.0


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e5da47d87e4c61242346f838afaafee27e8e572d07215f09ea651c169f8b1bc3f007fd27332dc760f7986af8b66e3b3b2)