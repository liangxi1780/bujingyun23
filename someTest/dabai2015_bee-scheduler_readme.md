# Bee-Scheduler
  
## 特性
- 基于Quartz开发，支持集群和单机两种运行模式（集群模式基于Quartz内置特性实现，原理是db锁做任务状态同步）
- 通过任务组件的方式，将调度逻辑与任务逻辑完全隔离，代码零侵入，灵活性极高
- 支持多种调度触发器（simple、calendar、daily、cron）
- 任务管理（编辑、暂停、恢复调度、立即运行、复制任务、删除等等）
- 支持联动任务，直接页面操作来配置出任何你想要的联动规则
- 详细的任务历史记录（执行时间、执行节点、耗时、日志、状态、触发方式等等。。。）
- 支持临时任务
  
> 该项目目前处于初期，核心功能已经完成，其他更多特性敬请期待。。。请看todo list
  
## 运行前准备
- JAVA 1.8+
- Mysql
  
## 开始
创建一个数据库用于存储任务数据（库名随意、UTF-8字符集），比如下文中的bee-scheduler就是库名  
至此，所有准备工作就已经完成！  
  
>“不用建表吗（黑人问号脸.jpg）？？？”  
>“不用！数据表会在系统首次启动的时候自动生成”
  
## 下载最新的可运行包
[https://gitee.com/kangroo/bee-scheduler/releases](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e2600a0f29d01b9790f08149b0786d802a9ab51e044220626f05356312f5f0f27)
  
## 单机运行模式:
```shell
java -jar admin-node-xxx.jar --server.port=8080 --dburl="127.0.0.1:3306/bee-scheduler?user=root&password=root&characterEncoding=UTF-8&useSSL=false"
```
可以使用 ```--thread-pool-size=30``` 来设置调度线程池大小  
启动完成后浏览器访问：http://ip:port  ，请使用IE9+、Chrome、Safari、Firefox等现代浏览器  
  
## 集群运行模式：
### 1、运行一个管理节点（使用--cluster开启集群）：
```shell
java -jar admin-node-xxx.jar --server.port=8080 --dburl="127.0.0.1:3306/bee-scheduler?user=root&password=root&characterEncoding=UTF-8&useSSL=false" --cluster
```
可以使用 ```--thread-pool-size=30``` 来设置调度线程池大小  
启动完成后浏览器访问管理节点：http://ip:port **（注意：管理节点自身也是一个普通的调度节点）**，请使用IE9+、Chrome、Safari、Firefox等现代浏览器 
### 2、使用runnable-node扩展节点
```shell
java -jar runnable-node-xxx.jar --dburl="127.0.0.1:3306/bee-scheduler?user=root&password=root&characterEncoding=UTF-8&useSSL=false"
```
可以使用 ```--thread-pool-size=30``` 来设置调度线程池大小  
启动完成后，会自动加入集群（基于db做注册），访问管理节点能看到集群信息

## 管理界面截图
![BeeScheduler](readme/1.png "BeeScheduler")
![BeeScheduler](readme/2.png "BeeScheduler")
![BeeScheduler](readme/3.png "BeeScheduler")
![BeeScheduler](readme/4.png "BeeScheduler")
![BeeScheduler](readme/5.png "BeeScheduler")
![BeeScheduler](readme/6.png "BeeScheduler")
  
## Todo List
- 添加报警机制，任务执行失败时邮件报警
- 完善Dashboard，完善各种统计、监控信息
- 支持Oracle数据库
- 增加更多任务组件
- 增加权限管理
- 实时日志
- 更多....
  
## 开源协议
[MIT](http://u.720life.cn/g/ba059582536a397f7c573b87c8bea647045b0ef049248233b6f76e909e70200fe7048b25e29c8bab79aeff32ea74556a)


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e68989fe51c0f5fc2f0f8b67abf1d24b72004e67b42fbdedc6899b6974d6184b06f1233b23cf78366b0635abb0aa95797)