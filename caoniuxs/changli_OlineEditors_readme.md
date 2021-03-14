
##建立指导

首先，您需要安装oracle-java8-installer

```
sudo add-apt-repository ppa:webupd8team/java
sudo apt-get update
sudo apt-get install oracle-java8-installer
```

编辑settings.properties配置文件。使用安装的ONLYOFFICE文档服务器指定本地服务器的名称

```
nano src / main / resources / settings.properties
```

编辑以下行：

```
files.docservice.url.converter = HTTPS：//documentserver/ConvertService.ashx
files.docservice.url.tempstorage = HTTPS：//documentserver/ResourceService.ashx
files.docservice.url.api = HTTPS：//documentserver/web-apps/apps/api/documents/api.js
files.docservice.url.preloader = HTTPS：//documentserver/web-apps/apps/api/documents/cache-scripts.html
```

安装Maven：

```
apt-get install maven
```

并建立：
mvn包

之后，所有bin文件都将传递给./target文件夹

##从docker构建

编辑settings.properties配置文件。使用安装的ONLYOFFICE文档服务器指定本地服务器的名称

```
nano src / main / resources / settings.properties
```

编辑以下行。您需要将documentserver更改为您的文档服务器：

```
files.docservice.url.converter = HTTPS：//documentserver/ConvertService.ashx
files.docservice.url.tempstorage = HTTPS：//documentserver/ResourceService.ashx
files.docservice.url.api = HTTPS：//documentserver/web-apps/apps/api/documents/api.js
files.docservice.url.preloader = HTTPS：//documentserver/web-apps/apps/api/documents/cache-scripts.html
```

在java示例目录中运行next命令：`docker build。 -t java-example docker run -it -v $ PWD / target：/ java / target java-example`之后，所有bin文件都将传递给./target文件夹




 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ebc0deef37c90b37a21981703611e7c519143bce8acee17e7d0d5044e26e4eca44ce273b85fe70c9e8991978c5d3c26c5)