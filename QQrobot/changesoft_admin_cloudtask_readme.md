# CloudTask

![Logo](https://avatars0.githubusercontent.com/u/28881302?s=150&v=4)

### What is CloudTask?

`Cloudtask` is a lightweight distributed task scheduling management platform that is small and easy to used. we can upload, pause, start tasks, clone a task, modify the task's execution command, view the task's schedule info status and execution log, developers can write any task program in the programming language they are most familiar with. It can be a console program or a shell script and uploaded to the platform.

### CloudTask Design

The `Cloudtask` backend is a stateless service. It uses the `Zookeeper` to realize the discovery and coordination between the nodes of the cluster, and the nodes register to the registration center in a heartbeat manner, The center server manages all the clusters in a unified manner, tasks scheduling is distributed in clusters and has good scalability, the tasks allocation information is divided into clusters and the allocation data is stored in the `Zookeeper` node to maintain the consistency of the allocated data.

##### More info at [cloudtask.github.io](http://u.720life.cn/g/65e55f62fe2ba0b788b4e2d2a6fa10b00cdd33b03daf59466abacc41e621e98f2541cb77d21c07dc291ce4d307bbf464)

### Architecture

![Architecture](./docs/_media/cloudtask.png)

### Features   
* Distributed: Use `Zookeeper` to implement registration center, distribution of nodes and tasks.
* Cross-platform: Supports deployment on `Windows` and `Linux` platforms.
* Task Timer: In strict accordance with the task scheduling cycle execution, the same task at the same time point will only be scheduled to trigger an execution to maintain consistency of state.
* Tasks Control: You can manually start and stop a task at any time.
* Parallel Scheduling: Each node in the cluster schedules local tasks in parallel.
* Elasticity Cluster: Nodes are gathered in a ring structure, adding and exiting the cluster is more flexible. The local part task is reassigned based on the node.
* Cluster Failover: When a node failure occurs, only the tasks of the failed node are migrated to prevent the cluster task from adjusting jitter.
* Operation Maintenance: Manage all tasks and cluster information centrally through front-end sites, including User authorization management.
* Event Notify: If the task fails to execute or the cluster node is offline, the system will notify the operator with the event email.
* Collecting Message: The node will feedback the tasks execution result to the center server, and the log display will be more intuitive.
* Stability Cluster: In the case of no server fluctuations, the task will not be allocation. 

### Components

* [CloudTask InitConfig](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e07e227087fd23d377dbc3fc340c69c4eb43e53021073bb1ae21fd15e41a98905)
* [CloudTask Web](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e07e227087fd23d377dbc3fc340c69c4e0c0e4a4cecaef1c798d5456906739236)
* [CloudTask Center](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e07e227087fd23d377dbc3fc340c69c4e0dbfba8ed9b73d8f0f2d4c364580c41b)
* [CloudTask Agent](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e07e227087fd23d377dbc3fc340c69c4edf2f3ac00b2333a183f852c651bdf69c)

### Project About

* This Project: [https://gitee.com/cloudtask](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6eb5eeb48d6e1d9423c4c43f6711e941cd)

* Documents: [https://cloudtask.github.io/cloudtask](http://u.720life.cn/g/65e55f62fe2ba0b788b4e2d2a6fa10b00cdd33b03daf59466abacc41e621e98f2541cb77d21c07dc291ce4d307bbf464)

* Demo Online At: [http://104.225.159.143:8091](http://u.720life.cn/g/8e2bcbdd5d33061d5be5fabd15b13f03765fec35fd053b1139692653d1465f13)   

  User: guest Password: 123456

## Preview

Web Login

![Login](https://cloudtask.github.io/cloudtask/_media/login.png)

Dashboard

![Dashboard](https://cloudtask.github.io/cloudtask/_media/dashboard.png)

Cluster

![Cluster](https://cloudtask.github.io/cloudtask/_media/runtime_states.png)

Tasks

![Tasks](https://cloudtask.github.io/cloudtask/_media/tasks_list.png)

## License

cloudtask is licensed under the [Apache Licence 2.0](http://u.720life.cn/g/c0fe1da5278ca9f6360e901f74721f845e8fe6a63a2e42f1caa9cfc3bfda71640d7e08e8dff8ca14a4a2db069871c2fb).   



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e66a2e9a6fd8929c08f43cd2b97d84918130f7c976991836b9aa5d18d65177adc009653c88a5914d1128254ebb2dd804828cff96e3b5d8d03297e25e0a07bb22d)