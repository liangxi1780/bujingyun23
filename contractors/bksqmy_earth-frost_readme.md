# earth-frost

earth-frost是一个轻量级分布式任务调度框架。


## 介绍
- 调度模块和执行模块分离
- 使用redis作为数据库
- 基于订阅模式实现服务注册和发现
- 演示地址： http://www.justlive.vip (请勿恶意攻击)

## 环境
- Angular: v1.x
- JDK: 1.8+
- Maven: 3+
- Redis: 2.8+
- Spring boot: 2.x
- Thymeleaf: 3

## 功能
1.0.0
- 简单易上手，支持web界面进行任务的CRUD
- 支持动态修改任务的开始，停止
- 调度中心支持集群部署，将任务的调度进行封装，支持分配各种不同的任务
- 执行器支持分布式，支持集群部署，可进行相应分组，在调度中心界面查看
- 支持伸缩扩展，调度中心和执行器都是基于redis订阅模式进行服务注册发现和任务调度，服务上下线发现及时
- 支持失败重试
- 任务监控和报警
- 动态编译任务，支持web界面编辑任务源码，创建任务
- 支持父子任务
- 运行报表 

1.1.0
- 支持钉钉预警通知
- 调度记录增加执行时间
- 任务超时报警机制
- 支持分片任务
- 支持SimpleTrigger任务
- 支持非spring项目开发执行器
- misfire

## 开发
	
	frost-api
		对外实体和接口
	frost-core
		定义调度、执行、注册发现等核心功能的接口和实现
	frost-center
		调度中心服务，包含安全认证和UI展示，依赖core实现调度逻辑
	frost-executor
		执行器服务，依赖core实现任务执行逻辑，包含开发脚本任务的部分实例以及配置样例	
	frost-client
		客户端api，第三方项目可依赖client实现与调度中心交互
	
## 快速入门

### 启动Redis数据库
请下载并安装2.8+版本的Redis，单机或集群模式皆可。

调度中心和执行器均支持集群模式部署，集群模式下各节点需配置相同的Redis服务

### 导入源码
解压源码，按maven格式将源码导入IDE，源码结构如上述 [开发] 章节。

### 配置部署调度中心
#### 1.配置内容说明

```
# 登录账号
spring.boot.auth.enabled=true
spring.security.user.name=frost
spring.security.user.password=frost

# 报警通知发送邮件
spring.mail.host=smtp.mail.com
spring.mail.username=
spring.mail.password=

# 邮件通知
frost.notifier.mail.enabled=true
frost.notifier.mail.from=${spring.mail.username}
frost.notifier.mail.to=
frost.notifier.mail.subject=#{job.name} (#{job.id}) throws an exception
frost.notifier.mail.text=#{job.name} (#{job.id}) \n #{event.message}

# 钉钉通知
frost.notifier.dingtalk.enabled=false
frost.notifier.dingtalk.subject=There is something wrong with #{job.name} (#{job.id})
frost.notifier.dingtalk.text=#{job.name} (#{job.id}) \n #{event.message}
frost.notifier.dingtalk.accessToken=
frost.notifier.dingtalk.linkUrl=localhost:20000/center

# redis配置
# 0:单机模式， 1：集群模式，2：云托管模式，3：哨兵模式，4：主从模式
redisson.mode=0

# 公共配置
redisson.password=
redisson.slaveConnectionPoolSize=50
redisson.masterConnectionPoolSize=50
redisson.timeout=3000

# 单机模式
redisson.address=redis://localhost:6379

# 集群模式
redisson.nodeAddresses=redis://localhost:6379,redis://localhost:6380,redis://localhost:6381
redisson.scanInterval=2000

# 云托管模式
redisson.nodeAddresses=redis://localhost:6379,redis://localhost:6380,redis://localhost:6381
redisson.scanInterval=2000
redisson.dnsMonitoringInterval=5000

# 哨兵模式
redisson.sentinelAddresses=redis://localhost:6379,redis://localhost:6380,redis://localhost:6381
redisson.scanInterval=2000
redisson.masterName=mymaster

# 主从模式
redisson.masterAddress=redis://127.0.0.1:6379
redisson.slaveAddresses=redis://localhost:6380,redis://localhost:6381
redisson.dnsMonitoringInterval=5000
```

#### 2.部署项目
正确进行上述配置，可将项目编译打包 mvn package(jar或war，相关打包操作参照Spring boot)，调度中心访问地址：http://localhost:20000/center，访问可进入登录界面
![登录页面](https://gitee.com/justlive1/earth-frost/raw/master/images/login.jpeg)
登录成功后进入报表页面
![报表页面](https://gitee.com/justlive1/earth-frost/raw/master/images/statictis.jpeg)

#### 3.集群模式
支持集群模式部署，提供调度系统可用性。

集群模式需要注意：保持 登录账号保持一致，保持使用redis配置相同。建议使用Nginx为调度中心做负载均衡

### 配置部署执行器

提供的frost-executor项目可直接使用，也可集成到现有业务项目中使用

#### 1.依赖jar
在执行器项目中依赖如下jar包

```
 
	 vip.justlive 
	 frost-core 
 
```

#### 2.配置说明

```
# 每个job支持并行处理数
frost.job.parallel=2

# 执行器名称
frost.job.executor.name=${spring.application.name}
# 执行器Key
frost.job.executor.key=executor-demo
frost.job.executor.ip=
frost.job.executor.port=${server.port}
# 是否支持执行脚本任务
frost.job.executor.scriptJobEnabled=true
# 错过执行的阈值(毫秒)
frost.job.executor.misfireThreshold=5000

# redis配置
# 0:单机模式， 1：集群模式，2：云托管模式，3：哨兵模式，4：主从模式
redisson.mode=0

# 公共配置
redisson.password=
redisson.slaveConnectionPoolSize=50
redisson.masterConnectionPoolSize=50
redisson.timeout=3000

# 单机模式
redisson.address=redis://localhost:6379

# 集群模式
redisson.nodeAddresses=redis://localhost:6379,redis://localhost:6380,redis://localhost:6381
redisson.scanInterval=2000

# 云托管模式
redisson.nodeAddresses=redis://localhost:6379,redis://localhost:6380,redis://localhost:6381
redisson.scanInterval=2000
redisson.dnsMonitoringInterval=5000

# 哨兵模式
redisson.sentinelAddresses=redis://localhost:6379,redis://localhost:6380,redis://localhost:6381
redisson.scanInterval=2000
redisson.masterName=mymaster

# 主从模式
redisson.masterAddress=redis://127.0.0.1:6379
redisson.slaveAddresses=redis://localhost:6380,redis://localhost:6381
redisson.dnsMonitoringInterval=5000
```

#### 3.部署执行器
执行 `JobConfig.initExecutor()` 进行初始化执行器，项目打包按照集成项目打包方式即可，部署后打开调度中心页面查看执行器页面
![执行器列表](https://gitee.com/justlive1/earth-frost/raw/master/images/executor.jpeg)
列表中出现部署的执行器则说明部署成功

### 开发一个简单的任务
该案例使用脚本任务模式，比使用实例模式只需要部署调度中心和执行器即可，脚本任务可在调度中心在线维护

#### 1.新增任务
登录调度中心，在任务管理界面点击新增任务，任务类型选择脚本模式，输入相应参数，点击保存。
![任务列表](https://gitee.com/justlive1/earth-frost/raw/master/images/job.jpeg)
![添加脚本任务](https://gitee.com/justlive1/earth-frost/raw/master/images/addScriptJob.jpeg)

#### 2.脚本模式开发
在任务管理列表的操作栏，点击刚新建任务的脚本按钮，进入脚本脚本编辑页面。系统已经初始化了示例脚本任务，可按需进行修改。
![修改脚本](https://gitee.com/justlive1/earth-frost/raw/master/images/script.jpeg)

#### 3.触发执行
点击任务右侧“触发一次”按钮可触发一次任务(通常是配置cron定时触发)

#### 4.查看结果
进入调度记录页面可查看调度和执行结果
![调度记录](https://gitee.com/justlive1/earth-frost/raw/master/images/record.jpeg)

### 任务配置属性说明

```
任务类型：
	脚本模式：传统的任务模式，需要在执行器开发对应的Bean，此模式的任务只能调度分配到拥有该类的执行器上
	脚本模式：任务以Java源码的形式保存在数据库中，调度中心可将任务分配到任何开启支持脚本模式的执行器上，可使用@Resource/@Autowired注入执行器里中的其他服务
任务名称：任务的名称，描述任务以便于管理
执行器：指定运行在哪个执行器分组
执行器逻辑：指定任务运行的bean
任务模式：
	cron任务：支持cron表达式的定时任务
	简单任务：选择日期时间定时执行（当时间早于当前时间则立即执行）
	延时任务：启动任务后，固定延时执行任务
cron：触发任务的表达式（cron任务模式）
执行时间：选择执行的时间，精确到分（为什么不支持到秒？1.没有必要，2.h5的datetime-local仅支持到分，懒得用日期插件了）（简单任务模式）
延时：启动后延时时间，执行间隔时间，单位秒（延时任务模式）
子任务：可在任务列表中选择已创建的任务，当本任务执行成功时，将会触发子任务的一次主动调度
参数：运行任务的参数，字符串格式，执行逻辑可通过JobContext::getParam获取参数
失败处理：
	失败通知（默认）：调度或执行失败后，触发通知，默认提供了邮件，可继承AbstractEventNotifier进行扩展
	失败重试：调度或执行失败后，会主动再次调度或执行
通知邮件：调度中心配置了全局的默认推送邮件地址，每个任务可自定义添加通知邮件列表
超时预警：可填写任务的预期处理时间，超过时间还未执行完任务则进行预警
分片运行：勾选后任务分片运行，可填写分片总数，注意：分片任务需要任务逻辑支持分片方式，否则会重复执行
自动运行：勾选后创建任务即是运行状态
```

### 开发实例模式任务
任务需要在frost-executor项目中编码并部署

#### 1.在执行器项目中开发执行逻辑

```
- 继承 BaseJob 抽象类，默认实现了init、destory、exception方法
- 实现 BaseJob 的 execute 方法，任务处理的主要逻辑
- 异常处理（可选）重写 BaseJob 接口 exception 方法，自定义异常处理，返回true时执行全局异常处理逻辑，返回false不执行全局异常处理逻辑
- 实例化job（使用new或者ioc容器，推荐使用@vip.justlive.oxygen.core.ioc.Bean实例化）
- 注册到执行器，添加注解 @Job(value = "执行逻辑id", desc = "执行逻辑描述")

```

#### 2.在调度中心，新建任务
参考上述任务配置属性说明，任务类型选择实例模式，执行器选择执行器配置中frost.job.executor.key的值，执行逻辑选择@Job注解定义的值
![添加任务](https://gitee.com/justlive1/earth-frost/raw/master/images/addJob.jpeg)
![添加cron任务](https://gitee.com/justlive1/earth-frost/raw/master/images/addCronJob.jpeg)
![添加延时任务](https://gitee.com/justlive1/earth-frost/raw/master/images/addDelayJob.jpeg)

### 开发脚本模式任务

#### 1.在调度中心，新建脚本任务
参考实例模式的新建任务，任务模式选择脚本模式

注意：需要有执行器frost.job.executor.scriptJobEnabled=true开启支持脚本任务执行
![添加脚本任务](https://gitee.com/justlive1/earth-frost/raw/master/images/addScriptJob.jpeg)

#### 2.在调度中心，开发任务代码
点击指定任务的脚本按钮，前往在线编辑任务界面，支持对任务代码进行开发（可在IDE中编辑完毕，复制粘贴到编辑中），支持使用静态工具类获取执行器中其他Bean

注意：分布式执行器要获取执行器中的Bean要确认是否所有执行器都存在该Bean，可配合指定执行器的分组来限定执行脚本任务的执行器
![修改脚本](https://gitee.com/justlive1/earth-frost/raw/master/images/script.jpeg)

### 开发分片任务

#### 1.在执行器项目中开发执行逻辑

分片任务通过将一个任务同时分发给所有执行器(或指定分片数量)，协同进行任务处理，当进行大数据量操作时可显著提高处理速度。

```
@Bean
@Job(value = "shardingJob", desc = "分片job例子")
public class ShardingJob extends BaseJob {

  @Override
  public void execute(JobContext ctx) {
	// 获取分片信息
    JobSharding sharding = ctx.getSharding();
	// 分片序号
    int index = sharding.getIndex();
    // 分片总数
    int total = sharding.getTotal();
    
    ... 业务逻辑
  }
}
```

#### 2.在调度中心，新建任务

参考上述实例任务配置任务，勾选分片运行，可使用默认执行器个数用于支持动态扩容或指定分片总数
![添加任务](https://gitee.com/justlive1/earth-frost/raw/master/images/addShardingJob.jpeg)

### 任务管理

#### 1.执行器列表
点击执行器管理导航进入执行器列表，展示在线的执行器
![执行器列表](https://gitee.com/justlive1/earth-frost/raw/master/images/executor.jpeg)

列表字段说明

- 执行器分组： 通过配置文件中的frost.job.executor.key进行分组， 注意：分组相同且@Job的value相同的IJob逻辑应该完全相同 
- 名称：执行器应用的名称，便于区分和管理
- 信息：展开分组时展示该执行器下注册的任务列表，合并分组时展示分组下在线执行器数量


#### 2.任务管理

2.1 新建任务

参考开发实例模式或脚本模式任务章节

2.2 执行一次任务

点击操作栏“执行一次”按钮可触发执行一次任务
![执行任务](https://gitee.com/justlive1/earth-frost/raw/master/images/triggerJob.jpeg)

2.3 暂停任务

点击操作栏“暂停”按钮可暂停正常任务，后续调度将不再执行
![暂停任务](https://gitee.com/justlive1/earth-frost/raw/master/images/pauseJob.jpeg)

2.4 恢复任务

点击操作栏“恢复”按钮可恢复暂停任务
![恢复任务](https://gitee.com/justlive1/earth-frost/raw/master/images/resumeJob.jpeg)

2.5 编辑任务

点击操作栏“编辑”按钮可编辑任务属性，参照任务配置属性进行修改

2.6 在线编辑脚本

点击操作栏“脚本”按钮跳转到在线编辑脚本页面，可进行脚本任务源码修改
![脚本任务](https://gitee.com/justlive1/earth-frost/raw/master/images/toScriptJob.jpeg)
![修改脚本](https://gitee.com/justlive1/earth-frost/raw/master/images/script.jpeg)

2.7 跳转任务日志

点击操作栏“日志”按钮跳转到调度记录页面，只展示该任务的记录
![跳转任务日志](https://gitee.com/justlive1/earth-frost/raw/master/images/toRecord.jpeg)

2.8 删除任务

点击操作栏“删除”按钮删除任务
![删除任务](https://gitee.com/justlive1/earth-frost/raw/master/images/removeJob.jpeg)


#### 3.使用client

3.1 依赖frost-client

```
 
     vip.justlive 
     frost-client 
 
```

3.2 配置frost连接地址

```
# 调度中心地址
frost.client.baseUrl=http://localhost:20000/center
# 用户名
frost.client.username=frost
# 密码
frost.client.password=frost
```

3.3 实例化client

```
FacadeProxy proxy = FacadeProxy.newProxy("classpath:frost.properties", "classpath:frost-override.properties");
JobApiFacade jobApiFacade = proxy.getJobApiFacade();
```

3.4 调用JobApiFacade进行操作

…

## 联系信息

E-mail: qq11419041@163.com

QQ群: 950216299


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ed6a7d4396db05753f912a1ee658dcd167cffa216d79170fb0027580b31ac130f5ae5d39465ae280feeb614ced5004354)