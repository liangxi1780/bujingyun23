spring-boot-starter-druid

配置示例
```
#DRUID
druid:
    url: jdbc:mysql://localhost:3306/springboottest
    driver-class: com.mysql.jdbc.Driver
    username: root
    password: OZo+t9QET+ctzd5Esn9q0GJP5hXtWWIKEsX8c4/w6z4C4AnxrwpvySNgBS89XdazOavjXXZp0oeZtQ3P9lLGEA==
    initial-size: 1
    min-idle: 1
    max-active: 20
    test-on-borrow: true
    max-wait: 60000
    time-between-eviction-runs-millis: 60000
    min-evictable-idle-time-millis: 300000
    validation-query: SELECT 1 FROM DUAL
    test-While-Idle: true
    test-on-return: false
    pool-prepared-statements: false
    max-pool-prepared-statement-per-connection-size: 20
    filters: stat,wall,log4j,config
    connection-properties: druid.stat.mergeSql=true;druid.stat.slowSqlMillis=5000;config.decrypt=true
    monitor:
          enabled: enabled # 配置此属性Monitor才生效
          druid-stat-view: /druid/*
          druid-web-stat-filter: /*
          allow: 219.230.50.107,127.0.0.1
          deny: 219.230.50.108
          login-username: admin
          login-password: 123456
          exclusions: '*.js,*.gif,*.jpg,*.png,*.css,*.ico,/druid/*'
          reset-enable: false
```

查看[Druid配置](https://github.com/alibaba/druid/wiki/DruidDataSource配置属性列表)

`druid.monitor.enabled=enabled` 时Monitor才生效

配置就不讲了,不懂的自己`Google`去


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ea376b8dcbce22fa810b86146fca6b7460d5cd0911abd75f1dc116387923abb55814a8faf1f2f0a6be4f3e010883a1e2b58889884d36ab34734f8d9b38d276861)