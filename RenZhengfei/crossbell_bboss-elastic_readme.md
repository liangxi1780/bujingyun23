# Elasticsearch Bboss

Bboss is a good elasticsearch Java rest client. It operates and accesses elasticsearch in a way similar to mybatis.
https://www.oschina.net/p/bboss-elastic
# Environmental requirements

JDK requirement: JDK 1.7+

Elasticsearch version requirements: 1.X,2.X,5.X,6.X,+

Spring booter 1.x,2.x,+

# How to use Elasticsearch BBoss.

First add the maven dependency of BBoss to your pom.xml:

```xml
        
             com.bbossgroups.plugins 
             bboss-elasticsearch-rest-jdbc 
             5.5.2 
         
```

If it's a spring boot project, you can replace the Maven coordinate above with the following Maven coordinate:

```xml
         
             com.bbossgroups.plugins 
             bboss-elasticsearch-spring-boot-starter 
             5.5.2 
         
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
		public void handle(ESDatas  esDatas) throws Exception {
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
[Spring boot integration ElasticSearch case sharing](http://u.720life.cn/g/a88615b97db01a1ba3d626afe31cb173ab15db8f245696cf73019520d156855e5545d7b37e4fb14ce68e0cbacc269556)

[Quickly integrate Elasticsearch Restful API case sharing](http://u.720life.cn/g/a88615b97db01a1ba3d626afe31cb173ab15db8f245696cf73019520d156855e6339fa4be4df39d718a61475f4777280)

# Elasticsearch BBoss Developer Tutorial

[High-performance elasticsearch ORM library bboss use introduction](http://u.720life.cn/g/a88615b97db01a1ba3d626afe31cb173ab15db8f245696cf73019520d156855ee74b37b3a3618414128448dee2a0aef4)

 

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

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e7746fdc97c76111c48939be1e9bcd9836146b050de8a27edad7e1108317a49727c75ea1cc277a93dae710449ecd780fa)