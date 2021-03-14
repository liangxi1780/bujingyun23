LTS 轻量级分布式任务调度框架(Light Task Scheduler)
-----------------

###框架概况：
 LTS是一个轻量级分布式任务调度框架。有三种角色, JobClient, JobTracker, TaskTracker。各个节点都是无状态的，可以部署多个，来实现负载均衡，实现更大的负载量, 并且框架具有很好的容错能力。
 采用多种注册中心（Zookeeper，redis等）进行节点信息暴露，master选举。(Mongo or Mysql)存储任务队列和任务执行日志, netty做底层通信。
* JobClient : 主要负责提交任务, 和 接收任务执行反馈结果。
* JobTracker : 负责接收并分配任务，任务调度。
* TaskTracker: 负责执行任务，执行完反馈给JobTracker。

支持任务类型:
* 实时任务 
* 也支持定时任务 (如：3天之后执行)
* CronExpression (如:0 0/1 * * * ?) 

感兴趣，请加QQ群：109500214 一起探讨、完善。越多人支持，就越有动力去更新，喜欢记得右上角star哈。

github地址:[https://github.com/qq254963746/light-task-scheduler](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304682054d47c40a083152222076775a6486f3f51a9196b32a043958b7f2dc1c6b22f095ae14f69072c5c29a286bbe75c515) 

###架构图
![Aaron Swartz](http://git.oschina.net/hugui/light-task-scheduler/raw/master/docs/LTS_architecture.png?dir=0&filepath=docs%2FLTS_architecture.png&oid=1e5daa62b8d032daaa47eab4a84ab1d4c8962c33&sha=774aa73d186470aedbb8f4da3c04a86a6022be05)
####节点组:
* 1. 一个节点组等同于一个集群，同一个节点组中的各个节点是对等的，外界无论连接节点组中的任务一个节点都是可以的。
* 2. 每个节点组中都有一个master节点(master宕机，会自动选举出新的master节点)，框架会提供接口API来监听master节点的变化，用户可以自己使用master节点做自己想做的事情。
* 3. JobClient和TaskTracker都可以存在多个节点组。譬如 JobClient 可以存在多个节点组。 譬如：JobClient 节点组为 ‘lts_WEB’ 中的一个节点提交提交一个 只有节点组为’lts_TRADE’的 TaskTracker 才能执行的任务。
* 4. (每个集群中)JobTacker只有一个节点组。
* 5. 多个JobClient节点组和多个TaskTracker节点组再加上一个JobTacker节点组, 组成一个大的集群。

###工作流程:
* 1. JobClient 提交一个 任务 给 JobTracker, 这里我提供了两种客户端API, 一种是如果JobTracker 不存在或者提交失败，直接返回提交失败。另一种客户端是重试客户端, 如果提交失败，先存储到本地FailStore(可以使用NFS来达到同个节点组共享leveldb文件的目的,多线程访问,已经做了文件锁处理)，返回给客户端提交成功的信息，待JobTracker可用的时候，再将任务提交。
* 2. JobTracker收到JobClient提交来的任务,将任务存入任务队列。JobTracker等待TaskTracker的Pull请求，然后将任务Push给TaskTracker去执行。
* 3. TaskTracker收到JobTracker分发来的任务之后，然后从线程池中拿到一个线程去执行。执行完毕之后，再反馈任务执行结果给JobTracker（成功or 失败[失败有失败错误信息]），如果发现JobTacker不可用，那么存储本地FailStore，等待TaskTracker可用的时候再反馈。反馈结果的同时，询问JobTacker有没有新的任务要执行。
* 4. JobTacker收到TaskTracker节点的任务结果信息。根据任务信息决定要不要反馈给客户端。不需要反馈的直接删除,需要反馈的,直接反馈,反馈失败进入FeedbackQueue, 等待重新反馈。
* 5. JobClient收到任务执行结果，进行自己想要的逻辑处理。
* 详细请查看 [流程图](http://u.720life.cn/g/5c954f4cd4204fb6c09a7e58aa70844d81403b1c5f70a78250bd35f262daeb494b4ea156c37d65bf8f706d256c95746de2391b2df880c5bb044570f7cb328d09727bc5a552e3d981ebae45fbd10b3e672fbb51e4feb8fada4806128a8f72efa2ec2f20ec7f7b2c7430299246d20355d2d89bdfa1426a665d3182e22b3c939d956cddcaec1502908525910266640c66c31e763958a5379632a6a33b89a16b08d347030001b779c8f06eee8a5755e18e4af870009e6febba1b9bbe7c401f7715012f1e3bbced82c415739642b2e4c6cc692e638bc6b7e70ee196a9d232b2b4c5bc)

###特性
* 负载均衡:
     * JobClient和TaskTracker可是根据自己设置的负载均衡策略来请求JobTracker节点组中的一个节点。当连接上后将一直保持连接这个节点,保持连接通道，直到这个节点不可用,减少每次都重新连接一个节点带来的性能开销。

* 健壮性:
     * 当节点组中的一个节点当机之后，自动转到其他节点工作。当整个节点组当机之后，将会采用存储文件的方式，待节点组可用的时候进行重发。
     * 当执行任务的TaskTracker节点当机之后，JobTracker会将这个TaskTracker上的未完成的任务(死任务)，重新分配给节点组中其他节点执行。

* 伸缩性：
     * 因为各个节点都是无状态的，可以动态增加机器部署实例, 节点关注者会自动发现。
* 扩展性:
     * 采用和dubbo一样的SPI扩展方式，可以实现任务队列扩展，日志记录器扩展等

###日志记录
对于任务的分发，执行，还有用户通过 (BizLogger)  【LtsLoggerFactory.getBizLogger()】 输入的业务日志，LTS都有记录，用户可以在LTS Admin 后台界面查看某个任务的所有日志，可以实时查看这个任务的执行情况。 

###开发计划：
* WEB后台管理：性能统计分析，预警等
* 实现LTS的分布式队列存储

###LTS Admin
后台首页  [http://localhost:8080/main.html](http://u.720life.cn/g/e71094f6077cb9592da5b56893f0ad14e0b26ab64ac0d6cf8b153161ef06428f)

![Aaron Swartz](http://git.oschina.net/hugui/light-task-scheduler/raw/master/docs/LTS_Admin.png?dir=0&filepath=docs%2FLTS_Admin.png&oid=a53f98823a0451a80a34467c7dfa2a01d568a9e2&sha=774aa73d186470aedbb8f4da3c04a86a6022be05)
###调用示例
下面提供的是最简单的配置方式。更多配置请查看 [lts-example](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304682054d47c40a083152222076775a6486f3f51a9196b32a043958b7f2dc1c6b22ccae1a6b54aec0809586a48ca1b9d52d8dc813095190dcd832142705f83dfca88478fe375ed7d253f988bac58fa9888e1912642a67cd7aa21ca463c16e991b81) 模块下的 API 调用方式例子.

####JobTracker 端
```java
    final JobTracker jobTracker = new JobTracker();
    // 节点信息配置
    jobTracker.setRegistryAddress("zookeeper://127.0.0.1:2181");
    // 1. 任务队列用mongo
    jobTracker.addConfig("job.queue", "mongo");
    // mongo 配置
    jobTracker.addConfig("mongo.addresses", "127.0.0.1:27017"); 
    jobTracker.addConfig("mongo.database", "lts");
    jobTracker.setOldDataHandler(new OldDataDeletePolicy());
    // 启动节点
    jobTracker.start();
```

#### TaskTracker端
```java
    TaskTracker taskTracker = new TaskTracker();
    taskTracker.setJobRunnerClass(TestJobRunner.class);
    taskTracker.setRegistryAddress("zookeeper://127.0.0.1:2181");
    taskTracker.setNodeGroup("test_trade_TaskTracker");
    taskTracker.setWorkThreads(20);
    taskTracker.start();
    // 任务执行类
    public class TestJobRunner implements JobRunner {
        @Override
        public void run(Job job) throws Throwable {
            System.out.println("我要执行"+ job);
            System.out.println(job.getParam("shopId"));
            // TODO 用户自己的业务逻辑, 应该保证幂等
            try {
                Thread.sleep(5*1000L);
            } catch (InterruptedException e) {
                e.printStackTrace();
            }
        }
    }
```

#### JobClient端
```java
    JobClient jobClient = new RetryJobClient();
    // final JobClient jobClient = new JobClient();
    jobClient.setNodeGroup("test_jobClient");
    jobClient.setRegistryAddress("zookeeper://127.0.0.1:2181");
    jobClient.start();
    
    // 提交任务
    Job job = new Job();
    job.setTaskId("3213213123");
    job.setParam("shopId", "11111");
    job.setTaskTrackerNodeGroup("test_trade_TaskTracker");
    // job.setCronExpression("0 0/1 * * * ?");  // 支持 cronExpression表达式
    // job.setTriggerTime(new Date()); // 支持指定时间执行
    Response response = jobClient.submitJob(job);
```

##更新
1.5.4:
* 1. 增加 lts-spring 工程对spring的支持 (见lts-example 中spring文件夹下的例子)
* 2. 对于TaskTracker 同时支持 JobRunner 中 注解注入bean 和xml注入的方式


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e47df3a750cb2c430e5b6287cdc9f250edbe9cdfd7063ca9ced30fc7d7516cad47ac0b3d60e13a2e892c565d32e1dd0114a08044c88d30d5d7bbf5f5dc621595a)