![Datax-logo](https://github.com/alibaba/DataX/blob/master/images/DataX-logo.jpg)



# DataX

DataX 是阿里巴巴集团内被广泛使用的离线数据同步工具/平台，实现包括 MySQL、Oracle、SqlServer、Postgre、HDFS、Hive、ADS、HBase、OTS、ODPS 等各种异构数据源之间高效的数据同步功能。



# Features

DataX本身作为数据同步框架，将不同数据源的同步抽象为从源头数据源读取数据的Reader插件，以及向目标端写入数据的Writer插件，理论上DataX框架可以支持任意数据源类型的数据同步工作。同时DataX插件体系作为一套生态系统, 每接入一套新数据源该新加入的数据源即可实现和现有的数据源互通。



# DataX详细介绍

##### 请参考：[DataX-Introduction](http://u.720life.cn/g/54145d0471d91890860f7f8463c030463c8aa4ced01cde82896423459c82d93f883549fab7e7aff859cae759c249ddece8f6894a0382539e55da2bbc1207843a)



# Quick Start

##### Download [DataX下载地址](http://u.720life.cn/g/377d7df4078ece2a46019f0f82be7136211ea1be97a6818f08e50c63418e6f1fb79bd21901b317345e9905e5c614aa5473e3ef7c17858fc2005f848ccfb531af4bd835dcbc783cd45e605b66f2b5ba1f)

##### 请点击：[Quick Start](http://u.720life.cn/g/54145d0471d91890860f7f8463c030463c8aa4ced01cde82896423459c82d93fdb646f0719183bc97bbd75647d021fa156f8bf0c3f922ec643f9525628959d40)
* [配置示例：从MySQL读取数据 写入ODPS](http://u.720life.cn/g/54145d0471d91890860f7f8463c030463c8aa4ced01cde82896423459c82d93fdb646f0719183bc97bbd75647d021fa156f8bf0c3f922ec643f9525628959d40)
* [配置定时任务](http://u.720life.cn/g/54145d0471d91890860f7f8463c030463c8aa4ced01cde82896423459c82d93fa2d030957e8b8ffcfe4e6949227e1c63145c4eaef3b610834a3b0669d49b6f91e6197d1261327016c37a8230762a467aae379588fb322cd0afe9193b5953d6d45ada3b3737d2b918835cfc4b1afeb68bd43faf00444d87492d8375722a4889404665dbfd31187ae804a45a6cd297f26d)
* [动态传入参数](http://u.720life.cn/g/54145d0471d91890860f7f8463c030463c8aa4ced01cde82896423459c82d93fae5176780bee6185fcdd88b0261367055bc08c693face6a81ee5e85c30a39866ef2dfa7cb4a92b34aff8f33c6b2fe8beb040e0e588dbea1592818d3b91a3c719)



# Support Data Channels

DataX目前已经有了比较全面的插件体系，主流的RDBMS数据库、NOSQL、大数据计算系统都已经接入，目前支持数据如下图，详情请点击：[DataX数据源参考指南](http://u.720life.cn/g/54145d0471d91890860f7f8463c030463c8aa4ced01cde82896423459c82d93fa0fad514539d723d5dc482dc32d63bcdeca581be91232aff94e1fe4af05a59ab)

| 类型           | 数据源        | Reader(读) | Writer(写) |
| ------------ | ---------- | :-------: | :-------: |
| RDBMS 关系型数据库 | Mysql      |     √     |     √     |
|              | Oracle     |     √     |     √     |
|              | SqlServer  |     √     |     √     |
|              | Postgresql |     √     |     √     |
|              | 达梦         |     √     |     √     |
| 阿里云数仓数据存储    | ODPS       |     √     |     √     |
|              | ADS        |           |     √     |
|              | OSS        |     √     |     √     |
|              | OCS        |     √     |     √     |
| NoSQL数据存储    | OTS        |     √     |     √     |
|              | Hbase0.94  |     √     |     √     |
|              | Hbase1.1   |     √     |     √     |
|              | MongoDB    |     √     |     √     |
| 无结构化数据存储     | TxtFile    |     √     |     √     |
|              | FTP        |     √     |     √     |
|              | HDFS       |     √     |     √     |


# 我要开发新的插件
请点击：[DataX插件开发宝典](http://u.720life.cn/g/54145d0471d91890860f7f8463c030463c8aa4ced01cde82896423459c82d93f358d28d11619a3cb6e58de9d1e407b33643c7064dc9c2e0fef34e6c12bfccbbd1207ce39f622e60802fe625f41df4b565495f2e7f3caddbb4016bfbd6ebebc819e6d54ea5f8ae571ad0b1a3ae172a80a)

# Contact us

请及时提出issue给我们。请前往：[DataxIssue](http://u.720life.cn/g/54145d0471d91890860f7f8463c030463c8aa4ced01cde82896423459c82d93f1ec651badc74aed34e2e07ee36703193)

钉钉用户请扫描以下二维码进行讨论：

![DataX-OpenSource-Dingding](https://cloud.githubusercontent.com/assets/1067175/17893431/40c5f8d2-6978-11e6-8fdd-80d4e961a72b.png)


官方旺旺群：1585662022



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ea46b06378039e1a8190f5de9eaf20740735276eb3dc2128219c21380e631c4faa43bb654efff804d1c62e79e9e54f520)