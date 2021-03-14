##  dec-rds-loader
    dec-rds-loader-hbase: 加载数据到HBase
    dec-rds-loader-tsdb : 加载数据到OpenTSDB
    
## 部署节点
    实时处理节点：spark002
    项目存放位置：calabar 用户目录下的 dc_project，例如：/home/calabar/dc_project/
    
## 执行脚本
    启动：PROJECT_HOME/bin/start-on-yarn.sh
    停止：PROJECT_HOME/bin/stop.sh
    
# Notice
    若集群 HDFS  配置发生改变，需要将集群中的 hdfs-site.xml 和 core-site.xml 拷贝到 PROJECT_HOME/conf/ 下
    若集群 HBase 配置发送改变，需要将集群中的 hbase-site.xml 拷贝到 dec-rds-loader-hbase/conf/ 下



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e8770191ff77e585f31b29b1a186ecf3d4391e1469d19beb17acd5d641af9511c27c3c5e2da1e5c1fa07b5ec258f3441ed1adf03f8f40893d3b52bceea326d37e)