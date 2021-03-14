## RabbitMQ
- 安装plugin rabbitmq-plugins enable rabbitmq_management
- 默认访问地址： http://localhost:15672/  guest/guest

### Rabbitmqctl
 
 ```
    rabbitmqctl add_vhost /myhost # 添加 vhost 
    rabbitmqctl add_user me me123 # 设置用户和密码
    rabbitmqctl set_permissions -p /myhost me ".*" ".*" ".*"  # vhost 设置权限
```

#### 代码示例说明

> 
 RabbitMQ中的队列消息可能会处于以下4种状态：

　　❤ alpha：消息内容（包括消息体、属性和headers）和消息索引都存储在内存中；

　　❤ beta：消息内容保存在磁盘中，消息索引保存在内存中；

　　❤ gamma：消息内容保存在磁盘中，消息索引在磁盘和内存中都有；

　　❤ delta：消息内容和索引都在磁盘中；



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6eb8c83f58b4354d828f9e84b83aedbd046e70cb75c726f0bc9300e06c79aad86835151e73b25b52f4dbbab95ab41b363596d78c04c4b5e38bdc6e012793195401)