# monitor 阿修罗监控系统 
代码在github托管 https://github.com/AsuraTeam/monitor 请到这里关注, 将首先更新 
阿修罗监控，最好用的分布式开源监控系统,运维工作中自己开发的linux监控系统，功能强大灵活, 系统安装简单,配置简单 
相比zabbix, nagios,cacti，小米监控等都使用相当简单。只需要会写脚本，语言不限就可以实现任意监控需求。 
系统安装简单,配置简单 
 
1、数据采集免配置: agent自发现、agent主动推送, 任何数据自定义脚本 
2、可扩展性, 扩展简单,随时扩，随心扩 
3、历史数据查询, 可以秒级返回全年数据趋势图， 多个指标数据, 趋势图更明晰: 
   3天 7天，15天，30天，60天，90天，120天，180天，240天，360天时间段趋势 
4、架构设计高可用: 整个系统无核心单点，所涉及到的  
   负载均衡(nginx, haproxy, lvs)都可以用来负载server端， mysql(无数据压力，不做数据存储), 
    redis(需要高可用配置,推荐使用Codis),  
   共享存储设备(本地磁盘，nfs,mfs等). 
5、任何数据图像实时查看,历史查看功能 
6、针对统一系统,基础监控无需添加配置,自动添加(比如cpu,负载,磁盘使用率,网络流量,ss状态信息等,都可以自定义实现) 
7、报警组配置,支持微信，钉钉，手机，邮件功能(微信,钉钉需要单独处理,不是人都有的) 
8、分布式监控,每个装agent的都是一个监控系统,除配置外(配置只能在server端完成) 
9、自定义数据上报时间,最低5秒上报一次数据 
10、不同server性能对比,更简单,更清晰 
11、支持图像搜索,主机名,ip地址搜索图像 
12、图像收藏功能,常用的直接在收藏列表点开查看 
13、支持ldap认证登陆 
14、支持任何指标数据多条件筛选排序,资源使用情况一目了然 
15、集群数据分析,任何指标求和,平均 
16、支持项目模板导入导出 
17、自定义监控支持克隆配置 
18、支持grafana风格图像自定义展示 
19、支持对单个主机停止报警,多时间段内 
20、支持报警升级，最多5个级别的升级 
21、自动结合grafana画图工具,自动可生成图像 
22、可绘制网络top图
 

为国内用户下载方便，同步更新开源中国 
请到 https://gitee.com/asuramonitor/monitor  下载代码 
欢迎加入 阿修罗监控系统 QQ群 149469467 
 
 整体架构 
 
![image](https://raw.githubusercontent.com/AsuraTeam/monitor/master/images/img1.png)
 


 监控大盘 
 
 
![image](https://raw.githubusercontent.com/AsuraTeam/monitor/master/images/img2.png)
 
 网络TOP绘制  
 
![image](https://raw.githubusercontent.com/AsuraTeam/monitor/master/images/top1.png)
 
 报警信息查看  
 
![image](https://raw.githubusercontent.com/AsuraTeam/monitor/master/images/img9.png)
 
 图像展示  
 
![image](https://raw.githubusercontent.com/AsuraTeam/monitor/master/images/img3.png)
 
 大图显示  
 
![image](https://raw.githubusercontent.com/AsuraTeam/monitor/master/images/img12.png)
 
 grafana风格大屏展示  
 
![image](https://raw.githubusercontent.com/AsuraTeam/monitor/master/images/20.png)
 
![image](https://raw.githubusercontent.com/AsuraTeam/monitor/master/images/grafana.png)
 
![image](https://raw.githubusercontent.com/AsuraTeam/monitor/master/images/21.png)
 
![image](https://raw.githubusercontent.com/AsuraTeam/monitor/master/images/22.png)
 
![image](https://raw.githubusercontent.com/AsuraTeam/monitor/master/images/23.png)
 
![image](https://raw.githubusercontent.com/AsuraTeam/monitor/master/images/24.png)
 
![image](https://raw.githubusercontent.com/AsuraTeam/monitor/master/images/25.png)
 
![image](https://raw.githubusercontent.com/AsuraTeam/monitor/master/images/26.png)
 
 多维数据显示(任何机器任何数据组合对比)  
 
![image](https://raw.githubusercontent.com/AsuraTeam/monitor/master/images/img11.png)
 
 
![image](https://raw.githubusercontent.com/AsuraTeam/monitor/master/images/img15.png)
 
 
![image](https://raw.githubusercontent.com/AsuraTeam/monitor/master/images/img16.png)
 
 指标排序功能  
 
![image](https://raw.githubusercontent.com/AsuraTeam/monitor/master/images/img17.png)
 
 图像搜索功能  
 
![image](https://raw.githubusercontent.com/AsuraTeam/monitor/master/images/img13.png)
 
 指标聚合功能,单指标多服务器,平均和求和  
 
![image](https://raw.githubusercontent.com/AsuraTeam/monitor/master/images/img18.png)
 
 集群指标信息,平均和求和  
 
![image](https://raw.githubusercontent.com/AsuraTeam/monitor/master/images/img19.png)
 
 图像收藏功能  
 
![image](https://raw.githubusercontent.com/AsuraTeam/monitor/master/images/img14.png)
 
 系统概览  
 
![image](https://raw.githubusercontent.com/AsuraTeam/monitor/master/images/img4.png)
 
 报警统计  
 
![image](https://raw.githubusercontent.com/AsuraTeam/monitor/master/images/img5.png)
 
 监控添加页面  
 
![image](https://raw.githubusercontent.com/AsuraTeam/monitor/master/images/img7.png)
 
 脚本添加页面  
 
![image](https://raw.githubusercontent.com/AsuraTeam/monitor/master/images/img8.png)
 
 
 有钱赞助 
 
 大家可以赞助点,1毛不嫌少，1万不嫌多,您乐意就行,当然有问题可以联系，提供更多服务! 
 
 
![image](https://raw.githubusercontent.com/AsuraTeam/monitor/master/images/img-1.png)
 

 
    特别注意:本系统不能在公网开放,只能在私有网络运行，避免数据泄露或篡改  
    请注意防火墙, 监控上报数据使用 tcp 80端口和udp的50000到50300端口, 请保证agent都能连接到server的这些端口 
 
 

 系统组成部分:  
   1、java环境， jdk1.8 
   2、tomcat 
   3、redis 
   4、mysql数据库 
   5、mvn 
   6、agent 有java版和go版2个,后期都维护go版 
   7、elsticsearch 5.2 (可选) 
   
 运行系统 Centos 6.5  
 为方便使用,软件包tools/下面已集成mvn, java, redis,tomcat工具，直接可以使用, 无需自行下载, elsticsearch5.2 grafana 自行下载 
 

 准备工作:  
   1、mysql准备好，将cmdb.sql grafana.sql 导入到数据库 
     对需要链接的服务器进行授权 
     mysql>source cmdb.sql
     mysql>source grafana.sql
     mysql>grant select,update,insert,delete on cmdb.* to monitor@你的ip地址 identified by "aZkl299feM"; 
     mysql>flush privileges; 
     请绑定host os.dbm.com 到你的数据库的地址 
     ping os.dbm.com 看是否能解析到你的数据库IP地址 
     如果要修改域名请在安装完成后修改 /home/runtime/tomcat_8081/webapps/ROOT/WEB-INF/classes/jdbc.properties 替换成你自己的域名 
   2、准备一个redis服务 
     请绑定host os.redis.com到你的redis地址 
     ping os.redis.com 看是否能解析到你的redis的IP地址 
     如果要修改域名请在安装完成后修改 /home/runtime/tomcat_8081/webapps/ROOT/WEB-INF/classes/system.properties 替换成你自己的域名 
   3、修改对应的环境变量 
   4、绑定本机hostname到你的ip地址 
   5、本系统强制依赖时间，请保证所有服务器时间一致 
 
  安装步骤:  
   1、安装mysql数据库 
   2、安装java8 
   3、安装redis服务 
   4、安装tomcat 
   5、安装mvn 
   Mysql库请使用utf8字符集 
   其中redis, tomcat, mvn，java8可以直接使用tools里面的包， 安装程序统一部署到 /home/runtime 目录 
   详情查看deploy.sh脚本
   
   目录结构: 
   #ls /home/runtime 
    java8 tomcat_8081 redis maven 数据库自行配置即可 

 agent安装配置 go版  
1、安装go
2、cd monitor-agent-go 目录
3、查看README.md 文件
    
 agent安装配置 java版  
 6、安装agent  
      1、使用mvn打包, 打包完成后,将target/agent.jar 记录，稍后会用到 
      2、程序运行环境在tools/monitor.tar.bz2, 解压到 /home/runtime/目录 
      3、将tools里面的java8解压并改名为 /home/runtime/monitor/java/ 目录 
      4、修改agent配置文件，将所有v.asura.com替换为你的服务端的地址，为方便后期负载,尽量使用nginx等负载设备, 使用域名形式配置 
         修改redis.server 和server端使用的redis一致 
      5、将刚才的 agent.jar 复制到 /home/runtime/monitor/lib/ 目录 
         cp -v agent.jar /home/runtime/monitor/lib/ 
      6、启动 cd /home/runtime/monitor/bin; sh agent start 
      7、查看日志 tail -f /home/runtime/monitor/logs/agent.log
 
 
系统登录
系统默认密码用户名为 admin admin 
登录后请修改密码 
如果需要ldap登录，需要修改配置文件进行配置ldap服务信息 
 
安全设置 
redis添加密码: 
修改server redis.properties 和 agent agent.conf 
添加 redis.password="redis密码" 

   
针对授信任的server 
agent只接受该服务器的数据和发送数据到该服务器 
请到 tomcat_8081/webapps/ROOT/static/agent/agent.jar.servers 添加服务器地址,多个用换行分隔 
比如 
vim tomcat_8081/webapps/ROOT/static/agent/agent.jar.servers 
10.16.25.111  
10.16.25.222 
添加后,所有agent只接受这些服务器的数据和上报数据到这些服务器 
 
 
 
 配置流程  
 
因系统调用了hostname, 所以请将你的主机名和ip地址做下绑定 
示例: 
cat /etc/hosts 
10.1.1.1 localhost.localhost 
10.1.1.1 web_xx_xx 
 
1、配置资源信息 
   点击 资源信息->资源配置 配置下列资源数据 
   该模块主要是记录资源数据 
   1、机房配置(可选) 
   2、机柜配置(可选) 
   3、环境配置 
   4、业务线配置 
   5、管理员配置 
   6、服务器类型配置 
   7、服务类型配置 
   8、系统类型配置 
   以上配置只为第9条准备 
   9、服务器配置  
2、配置告警相关配置 
   点击 监控分析->监控配置->告警发送配置 配置下列信息 
   注意：发送报警只对组发送 
   1、配置联系组 
   2、配置联系人 
   3、消息通道配置 
      消息通道配置默认有邮件和手机的配置模板，自行修改即可 
3、其他更多配置,需要大家共享 
4、欢迎共享监控脚本 
  监控脚本输出为json格式: 
  示例: 
  [ 
   { 
     "name":"", 
     "groups":"", 
     "status":"", 
     "ip":"", 
     "messages":"", 
     "value":"", 
     "command":"", 
   } 
  ] 
  name 为指标名字比如 system.load.min1 | system.memrory.used | system.io.r_s.vda   
  groups 为指标所在的组，一个组里放相关的指标, 比如所有cpu指标都放在cpu组里  
  status 脚本逻辑执行返回状态,  
         1为正常, 2为危险,  
         3为警告, 4为未知, 
         在报警时只有状态为2发送报警，其他状态不发送报警，在监控全局可以看到该状态  

  ip 可选, 默认脚本返回json没有ip字段，系统会按请求到数据上报的客户端地址记录ip地址 
  messges 报警信息,可选, 在发送报警时发送的信息，自定义想写啥写啥，就是你的报警内容中会出现的文字 
  value 程序采集指标结果，为数字类型，不能为空 
  command 可选 
  任何一个脚本只要能返回这样的一个json格式的数据,就可以配到监控脚本，开始监控你的系统了 
  上传一个CPU类型的数据采集返回值: 
  [{"status": "1", "name": "system.cpu.user", "messages": "system.cpu.user 5.67", "value": "5.67", "command": "7", "groups": "cpu"}, {"status": "1", "name": "system.cpu.nice", "messages": "system.cpu.nice 0.00", "value": "0.00", "command": "7", "groups": "cpu"}, {"status": "1", "name": "system.cpu.system", "messages": "system.cpu.system 1.08", "value": "1.08", "command": "7", "groups": "cpu"}, {"status": "1", "name": "system.cpu.iowait", "messages": "system.cpu.iowait 0.58", "value": "0.58", "command": "7", "groups": "cpu"}, {"status": "1", "name": "system.cpu.steal", "messages": "system.cpu.steal 0.00", "value": "0.00", "command": "7", "groups": "cpu"}, {"status": "1", "name": "system.cpu.idle", "messages": "system.cpu.idle 92.66", "value": "92.66", "command": "7", "groups": "cpu"}]
  
配置完以上信息基本就可以跑演示版本了 

演示步骤: 
1、首先在服务端访问
   curl http://127.0.0.1:8081/monitor/configure/cache/all 初始化缓存信息 
2、启动agent
   启动agent后，稍等一会就可以看到一个演示版本了



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e52a389f6bed9213a995e7cb5f1e307a8909663d137e09ce30ade35c3897c1805e1544f8fcbb124f6b0bbccf289dca2bb)