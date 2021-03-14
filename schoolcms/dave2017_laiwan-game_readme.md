# laiwan-game

## 概述：
    工作之余练手项目。可用于局制游戏服务端，其他游戏类型也可以支持，实现了集群部署应付压力。
> [网关服务节点](http://u.720life.cn/g/e0d2c85055613e6181156334353bc3d9bf7dc1a29722fef00a6953f78e528301b856efb613830e174137fc8249dcfcd6aeb840388969df87fb3651391b07df08477cf7d47de1a78cac06a71354a38a397c0fd711d9655ed29b2accb646b18072)：接受客户端请求，分发到各处理节点（大厅、房间、游戏）。    

> [大厅服务节点](http://u.720life.cn/g/e0d2c85055613e6181156334353bc3d9bf7dc1a29722fef00a6953f78e528301b856efb613830e174137fc8249dcfcd6c666c72dbbc12781912a45d06a71a530dfd85bc55a00903d35a7c170d9af501b)：用户登录、注册、充值等等。

> [房间服务节点](http://u.720life.cn/g/e0d2c85055613e6181156334353bc3d9bf7dc1a29722fef00a6953f78e528301b856efb613830e174137fc8249dcfcd68cf77265e3679da2585d6c24549658f88b7276ba18f8f9e4b197d2b4cfd0ca6b):用户创建房间，解散房间，房内聊天等等。

> [游戏服务节点](http://u.720life.cn/g/e0d2c85055613e6181156334353bc3d9bf7dc1a29722fef00a6953f78e528301b856efb613830e174137fc8249dcfcd627ab522a70e4608dab88d656869c1a0bc0528476755cfcfdde108260992f3e8a):游戏节点， 五子棋啊，斗地主啊，麻将啊，狼人杀啊等等 

> [游戏示例-《猜拳游戏》](http://u.720life.cn/g/e0d2c85055613e6181156334353bc3d9bf7dc1a29722fef00a6953f78e528301b856efb613830e174137fc8249dcfcd659921a653c6989b8c2e30fe2d50715af)

> [定时任务处理节点](http://u.720life.cn/g/e0d2c85055613e6181156334353bc3d9bf7dc1a29722fef00a6953f78e528301b856efb613830e174137fc8249dcfcd69898a0dd40289e6a2d7ffa6658c5423fa6bdfc2bacd8d8e531a56df99a5187d7): 定时任务通过回调消息来执行
        
## 使用技术：
>集群方案：vertx3+hazelcast

>缓存方案：redis没的说

>数据库：mysql,如果数据量上百千万的时候数据库瓶颈的话 [我想说TIDB了解一下？](http://u.720life.cn/g/8dd928a246aeda3f2288ae11d6f07707e3737aeeea854072674c1ec84cfb5b02)

## 流程图：
![输入图片说明](https://gitee.com/uploads/images/2018/0416/171339_dcb18b6d_485050.png "未命名文件.png")

## 架构图：
![输入图片说明](https://gitee.com/uploads/images/2018/0412/213510_3b343630_485050.png "小游戏服务器 (1).png")


## 待完成：
1.数据库缓存数据到redis
2.redis集群


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e7421e02670d634aa671358cb4669910303f440ad00863d9b9946dfd9687b4ea9c5c09dde086a613a1a764b497b6bc8d5)