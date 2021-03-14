
1. 在工程中引用sequence项目的sequence-client jar包
2. 在的应用数据库中创建两个sequence表，sql语句如下：
```
    CREATE TABLE `sequence0` (
        `value` bigint(20) NOT NULL,
        `name` varchar(50) NOT NULL,
        `gmt_create` datetime NOT NULL,
        PRIMARY KEY (`name`)
    ) ENGINE=InnoDB DEFAULT CHARSET=utf8;

    CREATE TABLE `sequence1` (
        `value` bigint(20) NOT NULL,
        `name` varchar(50) NOT NULL,
        `gmt_create` datetime NOT NULL,
        PRIMARY KEY (`name`)
    ) ENGINE=InnoDB DEFAULT CHARSET=utf8;
```

3. 在spring xml中配置如下，为了防止单点故障，你可以配置两个数据库源:
```
     
         
         
         
             
                 
                     
                     
                     
                     
                 
                 
                     
                     
                     
                     
                 
             
         
     
```

4.  在你的应用程序中，则可以如下使用，需要多个不同的ID你需要配置不同的bizOrderIdSequence：
```
    Long bizOrderId = bizOrderIdSequence.nextValue();
```


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e1e1c03ff3267f0e94ff1d6fa3c22021461e664655075158eab0817bca0a793ee9529a69a566cc7026b1957f917c8c9f7)