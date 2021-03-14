# Atlassian Agent

#### Support (almost any version, include 8.0):
* JIRA Software [FAQ](doc/JIRA_FAQ.md)
* JIRA Core
* JIRA Service Desk
* JIRA plugin: Capture
* JIRA plugin: Training
* JIRA plugin: Portfolio
* Confluence [Windows特别注意](doc/Confluence_FAQ.md)
* Confluence plugin: Questions
* Confluence plugin: Team Calendars
* Bamboo [FAQ](doc/Bamboo_FAQ.md)
* Bitbucket [FAQ](doc/Bitbucket_FAQ.md)
* FishEye [FAQ](doc/FishEye_Crucible_FAQ.md)
* Crowd [FAQ](doc/Crowd_FAQ.md)
* Crucible [FAQ](doc/FishEye_Crucible_FAQ.md)
* Third party plugins

## 使用说明

### 优势
* 支持Atlassian家几乎所有产品，同时支持插件（包括插件市场的第三方插件）。
* 支持DataCenter模式。
* 相比较于传统的crack来说可以很容易的升级你的服务，而不用重新再次破解。
* 提供基于java的命令行 keygen，更方便在终端环境使用。
* 开源项目，你知道破解时都做了什么。

### 直接下载
* 直接下载本项目[release](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e753894294df82574d9944c6e8888f9c5f96bfed65cbfb6ac5fdc83c16779a6a3e8929f8cae5dfda7b1d7ccbe0e633ea7)包。

### 自行编译
* Clone本项目源码，pom.xml同级目录执行`mvn package`后即可进行编译。
* 使用`target`目录产出的`atlassian-agent-jar-with-dependencies.jar`，而非`atlassian-agent.jar`！
* *如果你不知道我在说什么，最好还是直接下载我编译好的包。*

### 使用帮助
* 破解需要成套使用，不能只破解插件，要先使用`atlassian-agent.jar`破解服务。
* 如果你已经获得`atlassian-agent.jar`，可以试着执行`java -jar atlassian-agent.jar`看看输出的帮助。
* 这里的帮助以Atlassian家的Confluence服务为例。

### 配置Agent
1. 将`atlassian-agent.jar`放在一个你不会随便删除的位置（你服务器上的所有Atlassian服务可共享同一个`atlassian-agent.jar`）。
2. 设置环境变量`JAVA_OPTS`（这其实是Java的环境变量，用来指定其启动java程序时附带的参数），把`-javaagent`参数附带上。具体可以这么做：
   * 你可以把：`export JAVA_OPTS="-javaagent:/path/to/atlassian-agent.jar ${JAVA_OPTS}"`这样的命令放到`.bashrc`或`.bash_profile`这样的文件内。
   * 你可以把：`export JAVA_OPTS="-javaagent:/path/to/atlassian-agent.jar ${JAVA_OPTS}"`这样的命令放到服务安装所在`bin目录`下的`setenv.sh`或`setenv.bat（供windows使用）`中。
   * 你还可以直接命令行执行：`JAVA_OPTS="-javaagent:/path/to/atlassian-agent.jar" /path/to/start-confluence.sh`来启动你的服务。
   * 或者你所知的其他修改环境变量的方法，但如果你机器上有无关的服务，则不建议修改全局`JAVA_OPTS`环境变量。
   * 总之你想办法把`-javaagent`参数附带到要启动的java进程上。
3. 配置完成请重启你的Confluence服务。
4. 如果你想验证是否配置成功，可以这么做：
   * 执行类似命令：`ps aux|grep java` 找到对应的进程看看`-javaagent`参数是否正确附上。
   * 在软件安装目录类似：`/path/to/confluence/logs/catalina.out`Tomcat日志内应该能找到：`========= agent working =========`的输出字样。

### 使用KeyGen
* 你得确认已经配置好agent，参考上面说明。
* 当你试着执行`java -jar /path/to/atlassian-agent.jar`时应该可以看到输出的KeyGen参数帮助。
* 请仔细看看每个参数的作用，特别是`-p`参数的取值范围。
* 第三方插件将其`应用密钥/插件关键字`作为`-p`参数。如：`-p com.gliffy.integration.confluence`
* 在Atlassian服务安装时你应该能看到类似：`AAAA-BBBB-CCCC-DDDD`的server id，请留意。
* 提供了正确的参数运行KeyGen会在终端输出计算好的激活码。
* 将生成的激活码复制出来去激活你要使用的服务。
* 举个栗子：`java -jar atlassian-agent.jar -p conf -m aaa@bbb.com -n my_name -o https://zhile.io -s ABCD-1234-EFGH-5678`

### 申明
* 本项目只做个人学习研究之用，不得用于商业用途！
* 商业使用请向[Atlassian](http://u.720life.cn/g/ab66b2f2c3939205971b7cbd6ba4319fdbb0bf2f1030daaea752553fb64d4a6c)购买正版，谢谢合作！
* 本项目使用`GNU General Public License v3.0`开源许可！
* 不允许说我代码写的糟糕，对我来说`PHP`才是世界上最好的语言（不服来辩）。

### 交流
* 给本项目发issue。
* 欢迎你来一起完善这个项目，请发PR。
* 你可以加入QQ群：30347511 和我实时交流。
* 访问网站：[https://zhile.io](http://u.720life.cn/g/80c3501f8f9d6e9ef9ad30f61510a470) 给我留言。

### 热心网友教程（感谢原作者，侵删！）
* [热心大佬的一键安装配置脚本](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046adae7df4f70394c862533a1f716b0a26fc84082ac963fcfe1b989a11be50045f2f6ec321dee84f1b8992e68570ff67d9)
* [confluence 安装及破解](http://u.720life.cn/g/e4e811bc35b0dbb835d744aa0eb990fd4229fb0bddbcda22ea0927253a81659b8b0b5f30150271a27aa181c3ee333d7dce8859626480992a4be323ea173552ae)
* [【黑科技】Atlassian产品线全破解](http://u.720life.cn/g/0142c85286e615348ce0fa33cb08b14db11a8b0c7496f733d5b2b6d305afb3ad769f9ad0fc7ef9d378f657dd49edabe2)
* [通过Docker安装JIRA和Confluence（破解版）](http://u.720life.cn/g/8a0e6e781ca1335d5641e0f9d5e96ab9dc81c95329da724a203a387c33bdca6e3fa141b27f02187fb7a4b3d0ba1a0f81)
* [通过Docker安装JIRA和Confluence（破解版）](http://u.720life.cn/g/a88615b97db01a1ba3d626afe31cb1735367f38ff682b784cc365c82f971dadf24dca5b03f62f3c6f15c3f25073fe532)


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e8931196aa89ddefc9b9afed5ae4806850775c88ea7955b46d57fee9a27871d49a5e17b8b2e1bf7767167b788fdb858f50cdbca4ef41d87d8b1f158cd30054e3e)