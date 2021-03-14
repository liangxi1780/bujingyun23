[![Build Status](https://travis-ci.org/smartloli/kafka-eagle.svg?branch=master)](https://travis-ci.org/smartloli/kafka-eagle)
![](https://img.shields.io/badge/language-java-orange.svg)
[![codebeat badge](https://codebeat.co/badges/bf22a7b2-76ac-4aba-b840-00328841d9e3)](https://codebeat.co/projects/github-com-smartloli-kafka-eagle-master)
[![Hex.pm](https://img.shields.io/hexpm/l/plug.svg)](https://github.com/smartloli/kafka-eagle/blob/master/LICENSE)

# Kafka Eagle

This is an monitor system and monitor your kafka clusters, and visual consumer thread,offsets,owners etc.

When you install [Kafka Eagle](http://u.720life.cn/g/9b4a1380e2aa619eac4d900347bdc8b9e25def02955405e2fc0413dcb4e55c92), you can see the current consumer group,for each group the topics that they are consuming and the offsets, lag, logsize position of the group in each topic. This is useful to understand how fast you are consuming from a message queue and how quick the message queue is increase. This will help you debuging kafka producers and consumers or just to have an idea of what is going on in your system.

The system shows the trend of consumer and producer trends on the same day, so you can see what happened that day.

Supported on kafka version: ``` 0.8.2.x ```,``` 0.9.x ```,``` 0.10.x ```,``` 0.11.x ```,``` 1.x ```,``` 2.x ``` .

Supported platform: ```Mac OS X```,```Linux```,```Windows```.

Supported JDK: ```JDK8+```

Here are a few Kafka Eagle system screenshots:

# Alert Support
In addition to supporting ```email``` alerts, Kafka Eagle also supports im alerts, such as ```DingDing``` and ```WeChat```.
![DingDing Alert](https://ke.smartloli.org/res/dingding@2x.png)
![WeChat Alert](https://ke.smartloli.org/res/wechat@2x.png)

# List of Consumer Groups & Active Group Graph
![Consumer & Active Graph](https://ke.smartloli.org/res/consumer@2x.png)

# List of Topics Detail
![Topics](https://ke.smartloli.org/res/list@2x.png)

# Consumer & Producer Rate Chart
![Rate Chart](https://ke.smartloli.org/res/consumer_producer_rate@2x.png)

# Start Kafka Eagle
![KE Script](https://ke.smartloli.org/res/ke_script@2x.png)

# Kafka Offset Types

Kafka is designed to be flexible on how the offsets are managed. Consumer can choose arbitrary storage and format to persist kafka offsets. Kafka Eagle currently support following popular storage format:
  * Zookeeper. Old version of Kafka (0.8.2 before) default storage in Zookeeper.
  * Kafka. New version of Kafka (0.10.0 in the future) default recommend storage in Kafka Topic(__consumer_offsets).
  
Kafka Eagle supports multiple offset storage paths. If you store them in Zookeeper and Kafka, you can configure them like this.
```
# Set kafka cluster alias
kafka.eagle.zk.cluster.alias=cluster1,cluster2

# Set kafka cluster zookeeper address
cluster1.zk.list=xdn1:2181,xdn2:2181,xdn3:2181
cluster2.zk.list=tdn1:2181,tdn2:2181,tdn3:2181

# Set kafka cluster offset storage path
cluster1.kafka.eagle.offset.storage=kafka
cluster2.kafka.eagle.offset.storage=zookeeper
```

# Kafka SQL

Use the SQL statement to query the topic message log, and visualize the results, you can read [Kafka SQL](http://u.720life.cn/g/6361e01e12f5efe77efbbaac8cdd3817fa432963ed5d2c3d037e57edfba65bd29e9a3ea7fea2c979fb5cce31ccd15c5c731552f2a6cf6a5cba8c8d42ea9b3105) to view the syntax.

# Quickstart

Please read [Kafka Eagle Install](http://u.720life.cn/g/6361e01e12f5efe77efbbaac8cdd3817d3e08811bcc265a823acad6343c3f5010f0e7be799060386a42dce008ed5a827707797368a8e253a38828c157a9dcfc4) for setting up and running Kafka Eagle. It is worth noting that, please use ```chrome``` to access Kafka Eagle.

# Deploy

The project is a maven project that uses the Maven command to pack the deployment as follows:
```bash
./build.sh
```
# More Information

Please see the [Kafka Eagle Manual](http://u.720life.cn/g/6361e01e12f5efe77efbbaac8cdd3817053320ec8828503b9ad5b235c49ba47a) for for more information including:
  * System environment settings and installation instructions.
  * Information about how to use script command.
  * Visual group,topic,offset metadata information etc.
  * Metadata collection and log change information.
 
# Contributing

The Kafka Eagle is released under the Apache License and we welcome any contributions within this license. Any pull request is welcome and will be reviewed and merged as quickly as possible.

Since this is an open source tool, please comply with the relevant laws and regulations, the use of civilization.

# Committers

Thanks to the following members for maintaining the project.

|Alias |Github |Email |
|:-- |:-- |:-- |
|smartloli|[smartloli](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046f64eaf7297eb827b4e818ad66241aebc)|smartloli.org@gmail.com|
|hexiang|[hexian55](http://u.720life.cn/g/54145d0471d91890860f7f8463c030468e503331b3cccf3e11bba729e91ac912)|hexiang55@gmail.com|
|cocodroid|[cocodroid](http://u.720life.cn/g/54145d0471d91890860f7f8463c030466700e1966ace0b8bbd54830216c75f3c)|sujunguang@gmail.com|
|alisa|[alisa](http://u.720life.cn/g/54145d0471d91890860f7f8463c030465a4a4576b9b7d47858ecc4b52df4f4c6)|alisazou1211@gmail.com|



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6eb45fd8d7187a17c03bf265367ff54e7f00c7fff54ed77404b9436d09bea65389fc85b816da2e4ecc6df34214b34f8d6b5dd743b7ae0a512dfa484357a127f112)