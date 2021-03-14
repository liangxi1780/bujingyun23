#demoncat-pm 

项目管理系统

## 功能

1、文档管理

2、服务器监控

3、服务监控

4、服务日志

5、服务部署

6、代码生成

## 部署

1、需要连接外网，来请求监控的服务、下载maven依赖

2、服务部署功能使用本地磁盘，所以要么共享磁盘目录，要么单实例部署服务；部署目录默认为"/data/deploy"

3、服务部署功能依赖git和maven，须在服务器上安装和配置

4、Maven本地仓库的目录必须是权限为777的"/data/maven"

5、创建ES应用日志索引，参考【服务日志】

6、在被监控的服务器上定时执行monitor.sh，参考【服务器监控】

## 服务器监控

在被监控的服务器上，通过crontab定时执行 /doc/shell/monitor.sh，来请求本项目中的监控端点

1、修改monitor.sh中的server config，指向demoncat-pm服务

2、添加cron定时来执行monitor.sh

3、通过管理后台设置报警邮箱；也可以直接设置数据字典 "200100100"

### 公网服务器监控

如果要开放外网服务器监控，通过 OpenServerActuator控制，即定时执行 /doc/shell/open-monitor.sh

为了防止恶意监控请求，服务端可以对公网IP地址做配置限制。

	# 允许监控的公网IP，多个用,分隔
	demoncat.server.monitor.publics=


## 服务监控

1、服务监控

2、日志监控

3、MongoDB视图，Redis视图，Zookeeper视图

### 客户端

1、依赖demoncat-util-web-cloud

2、参考demoncat-util-web-cloud.README.MD进行配置

3、服务启动时，向注册中心注册，由监控系统自动拉取

### 注意事项

1、JSON转换问题

使用Jackson解析响应时，health返回 {"status":"UP"}

使用Fastjson解析响应时，health返回{"details":{},"status":{"code":"UP","description":""}}

为了保证响应结果统一，包括eureka server和 app 都统一使用Fastjson来进行响应解析。
	
2、并发通知问题

因为每个节点都会监控所有WEB服务，并在发生事件时发出提醒，但无法对提醒消息做唯一鉴定，所以集群部署时会重复发送提醒消息。

解决方案：使用分布式锁，在10分钟内对同一个服务同一个事件，只进行一次提醒。

方案缺陷：可以解决重复发送，但也会造成漏发现象。不过正常情况下，不可能会对同一服务同一事件做频繁提醒。

终极方案：不进行集群部署。对于这类管理监控系统，只是运维、架构、技术管理使用，不需要使用集群部署。

## 服务日志

服务日志，通过Logstash保存到ElasticSearch中，所以需要先安装EL，并创建ES索引。

### 查询索引

	curl -XGET 'http://localhost:9200/_search?q=app:demoncat-pm&pretty'
	
### 删除索引

	curl -XDELETE 'http://localhost:9200/applog'
	
### 创建索引

	curl -XPUT 'http://localhost:9200/applog'

### 查看索引Mapping

	curl -XGET 'http://localhost:9200/applog/_mapping?pretty'

### 创建索引Mapping：定义索引字段类型

	doc/shell/elk.sh
	
### 设置索引：默认查询10000以上数据时报错

	curl -XPUT http://localhost:9200/applog/_settings -d '{ "index" : { "max_result_window" : 1000000000}}'
	
## 服务部署

* Eureka服务特殊处理：title = title@srv1 | title@srv2

* 本项目部署的服务器上，须安装maven和git，maven本地仓库指定为/data/maven

* appName：有模块=模块名，无模块=项目名

1、部署文件目录 /data/deploy/

	注：使用本地磁盘，所以要么共享磁盘目录，要么单实例部署服务
	
2、远程临时目录 /webapps/tmp/

3、远程项目目录 /webapps/{appName}		

4、远程运行日志 /logs/webapps/{appName}/*

	#--------------------------demoncat-deploy
	
	# 部署根目录
	demoncat.deploy.path=/data/deploy/
	# 本地Maven仓库地址
	demoncat.deploy.maven=/data/maven/
	# git协议
	demoncat.deploy.git-protocol=http://
	# git地址
	demoncat.deploy.git-url=git.ys360.net/centec/
	# git用户
	demoncat.deploy.gitUsername=yanxiaolei
	# git密码
	demoncat.deploy.git-password=
	
## 代码生成

1、项目管理 > 文件管理 > 数据库 > 创建数据库，设置连接信息

2、建表

3、生成代码，会读取数据库

## 建表示例

### 普通数据：baseType = ""

	CREATE TABLE `doc_api` (
	  `id` bigint(20) NOT NULL AUTO_INCREMENT COMMENT 'ID',
	  `name` varchar(30) NOT NULL COMMENT '接口名称',
	  `create_user` bigint(20) NOT NULL COMMENT '创建人',
	  `create_time` datetime NOT NULL COMMENT '创建时间',
	  `update_user` bigint(20) NOT NULL COMMENT '更新人',
	  `update_time` datetime NOT NULL COMMENT '更新时间',
	  `sort` bigint(15) NOT NULL COMMENT '排序',
	  PRIMARY KEY (`id`),
	) ENGINE=InnoDB AUTO_INCREMENT=814 DEFAULT CHARSET=utf8 COMMENT='接口文档';

### 树型数据：baseType = Tree，维护树型（id,name,parent_id）

	CREATE TABLE `auth_action` (
	  `id` varchar(20) COLLATE utf8_bin NOT NULL COMMENT '权限编码',
	  `name` varchar(25) COLLATE utf8_bin NOT NULL DEFAULT '' COMMENT '名称',
	  `type` char(1) COLLATE utf8_bin NOT NULL DEFAULT '0' COMMENT '资源类型',
	  `url` varchar(50) COLLATE utf8_bin NOT NULL DEFAULT '' COMMENT '访问的URL',
	  `sort` bigint(15) NOT NULL DEFAULT '0' COMMENT '排序',
	  `parent_id` varchar(20) COLLATE utf8_bin NOT NULL COMMENT '父ID',
	  `node_level` tinyint(3) NOT NULL DEFAULT '0' COMMENT '节点等级',
	  PRIMARY KEY (`id`),
	  KEY `idx_parent` (`parent_id`) USING BTREE
	) ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_bin COMMENT='服务端资源';

### 树型数据：baseType = Tree，CAS修改子节点数（version,sub_count）

	CREATE TABLE `area` (
	  `id` varchar(6) NOT NULL COMMENT 'ID',
	  `name` varchar(20) NOT NULL COMMENT '名称',
	  `parent_id` varchar(6) NOT NULL COMMENT '父ID',
	  `sub_count` int(3) NOT NULL COMMENT '子节点数',
	  `version` bigint(15) NOT NULL DEFAULT '1' COMMENT '版本号',
	  PRIMARY KEY (`id`),
	  KEY `idx_pid` (`parent_id`) USING BTREE
	) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COMMENT='省市县地图';

### 报表数据：baseType = Report

	CREATE TABLE `bus_report` (
	  `id` bigint(20) NOT NULL AUTO_INCREMENT COMMENT 'ID',
	  `type` varchar(6) NOT NULL COMMENT '统计分类/数据类型',
	  `item` varchar(32) NOT NULL DEFAULT '' COMMENT '统计项/数据ID',
	  `title` varchar(100) NOT NULL DEFAULT '' COMMENT '统计标题/数据名称',
	  `count` bigint(20) NOT NULL COMMENT '统计数量/整数值',
	  `sum` decimal(20,4) NOT NULL COMMENT '统计金额/浮点值',
	  `date` varchar(20) NOT NULL COMMENT '统计时间',
	  `year` int(4) NOT NULL COMMENT '统计时间-年',
	  `month` int(2) NOT NULL COMMENT '统计时间-月',
	  `day` int(2) NOT NULL COMMENT '统计时间-日',
	  `hour` int(2) NOT NULL COMMENT '统计时间-时',
	  `create_time` datetime NOT NULL COMMENT '创建时间',
	  PRIMARY KEY (`id`)
	) ENGINE=InnoDB AUTO_INCREMENT=468 DEFAULT CHARSET=utf8mb4 COMMENT='报表统计';




 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ebd96fb856ba3086420b28065fbdb17ff146bac58841b106af7d3ad9508f2556f45e7ba2a4da885b052ea37bb68a8f162)