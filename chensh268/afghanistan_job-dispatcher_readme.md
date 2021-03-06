# job-dispatcher

#### 介绍
一个工作流调度引擎

基本模型:基于事件或者定时生成一个job,每个job由若干个task组成，task之间存在串行或并行的依赖关系

task的具体实现引由客户端（用户自己编程实现），调度引擎只负责按照拓扑顺序发出HTTP信号调用任务

由客户端发出HTTP通知引擎任务任务的完成状态，调度引擎据此继续发出后续调度信号

使用场景:任务编排，事件驱动或时间驱动的任务调度，如企业级ETL调度等

特点:调度引擎只做调度和任务编排，具体任务实现和执行等调度引擎均不参与，因此具有极大的适用性，并且天生具备异构系统支持和性能隔离的特点。

#### 软件架构
软件架构说明

1.时间调度引擎:基于Quartz，按时触发对应的Job

2.Job引擎:可注册JobBuilder（包含子任务的依赖关系），Job引擎收到触发信号后，根据builder生成JobBox实例（包含批次时间和任务执行状态）
          按照时间顺序JobBox被Put到队列中，队首的JobBox会被消费，即按照拓扑关系依次发出信号，直到所有子任务执行完毕。

![输入图片说明](https://images.gitee.com/uploads/images/2019/0109/101119_f27af5bf_1466151.png "调度引擎任务队列.png")

                                                       调度引擎任务队列样例

![通过单点的任务依赖关系形成的Job拓扑图](https://images.gitee.com/uploads/images/2019/0108/220256_bb1bc412_1466151.png "任务拓扑图样例.png")

                                                       任务拓扑图样例


#### 安装教程

1.修改对应的jdbc数据源配置和pom里面的jdbc驱动依赖 

2.基于Springboot,用maven打包成Jar后启动即可

#### 使用说明

1. JDK1.8环境，通过默认端口浏览器访问就可以看到主页

2. 通过quartz/registerjob接口，传入Json格式的Job配置文件注册任务即可,具体如下
    1.任务端向引擎注册一个定时Job
    http://ip:port/quartz/register?json={} 

    //通过下列的json配置样例

    {

	"jobBoxBuilder": {

		"jobCode": "job1",

		"taskBuilderMap": [ //Job内的task组成列表

			{
				"taskCode": "task1",
				"adapterPara": "http://172.11.33.44/trigger?taskCode=task1", //启动task1
				"upstreamTaskCodes": ["task2"] //依赖task2，task2完成后task1才可执行
			},

			{
				"taskCode": "task2",
				"adapterPara": "http://172.11.33.44/trigger?taskCode=task2" //任务启动task2
				//"upstreamTaskCodes":["task3","task4"]	//不依赖任何任务可以不填该字段
			}

		]

	},

	"jobCronExpression": "0 0/1 11 * * ?", //每天九点每隔一分钟执行一次

	"filterCalendarName": "xxxx" //日历过滤策略，可以不填

    }


    2.任务端向引擎通知任务执行情况

    UNSTART("未开始", 0),TRIGGERED("正在触发", 1),STARTED("正在执行", 2),NEED_RESTART("需重新执行", 3),
    PAUSED("已暂停", 4),FINISHED("已完毕", 5);

    http://ip:port/task/call?jobcode=job1&taskcode=task2&status=0

    3.查看job的等待队列的情况，查看正在执行的job的情况(均可以通过页面)

    

#### 参与贡献

1. Fork 本仓库
2. 新建 Feat_xxx 分支
3. 提交代码
4. 新建 Pull Request


#### 码云特技

1. 使用 Readme\_XXX.md 来支持不同的语言，例如 Readme\_en.md, Readme\_zh.md
2. 码云官方博客 [blog.gitee.com](http://u.720life.cn/g/4d9d51ba66eeb41dfb9759648c593bf554785fd0e6ab49d2f13e98afcb69bbc7)
3. 你可以 [https://gitee.com/explore](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ed27d15edf43aa40a6d37a2a10b263e5a) 这个地址来了解码云上的优秀开源项目
4. [GVP](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6eb5ad9b84ebe402667383e4a11c785b2d) 全称是码云最有价值开源项目，是码云综合评定出的优秀开源项目
5. 码云官方提供的使用手册 [https://gitee.com/help](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ebbaab544314b1a4bd89bdd984a12bd00)
6. 码云封面人物是一档用来展示码云会员风采的栏目 [https://gitee.com/gitee-stars/](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e43c4696b881f436e3c9d0b3d64c264cb)


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ea6b8d1500e010e81c7dbfac363199f2f6524a5129055e9a94d06a61fc379a389f0867a909b3219e811235ea0ef14b799d21ab6c270c523c54eb5761f950d1c56)