elasticsearch整合分词、创建索引、搜索例子,elasticsearch版本为1.0,索引数据从数据表中动态读取生成,有关键字高亮效果，查询分页

**1** 在dababase目录中导致相关的数据库文件，修改DBCOperation java文件数据库连接地址,修改elasticsearch.properties文件中相关链接

**2** 运行CreatIndexMysql文件，里面有main方法查询数据库生成相关的索引文件

**3** 部署工程在tomcat中访问即可看到效果,项目中有很多的工具类，比如类似百度的关键字Suggest提示，拼音搜索等。可以在此项目基础上去扩展这些功能

备注：elasticsearch-rtf集成版下载地址 https://github.com/medcl/elasticsearch-rtf]

效果图
1.![输入图片说明](http://git.oschina.net/uploads/images/2015/1022/115706_5ee97a30_22473.png "在这里输入图片标题")

2.创建好的索引
![输入图片说明](http://git.oschina.net/uploads/images/2015/1022/114219_1e0794b8_22473.png "在这里输入图片标题")

3.![输入图片说明](http://git.oschina.net/uploads/images/2015/1022/115354_f2b52f6d_22473.png "在这里输入图片标题")

4.查询结果
![输入图片说明](http://git.oschina.net/uploads/images/2015/1022/144252_69cfbde5_22473.png "在这里输入图片标题")
![输入图片说明](http://git.oschina.net/uploads/images/2015/1022/144317_68b7e7cc_22473.png "在这里输入图片标题")

有什么问题可以QQ联系我：573824145

目前正在开发基于 spring-data-elasticsearch-1.2和elasticsearch1.7的项目，项目中基于elasticsearch的相关功能会更加的完善,欢迎有兴趣的朋友一起加入




 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6eac00852fbbef851c3db51cc2d962f98f16f43ad5aa715797f3574531e671ac9c1145ca199631a4b804b4bc5d56cff008302bc56309bde3051d898db09cdb329d)