## 简介

最简单的spring boot web 示例,message的curd演示操作
没有使用数据库,数据都保持在内存中

因为没有用到数据库,所以可以用来检测服务器java环境是否正确安装
- 使用mvn/mvnw命令打包项目,生成jar文件
- 将jar文件,application配置文件放到服务器目录
- 执行`java -jar xxx.jar`
- 启动成功后浏览页面查看是否正常运行

### 仓库地址

- [github仓库](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304642c9b9574b5b4f345ee0001652b3ef3ab56ef9b9e177d9013c60657c17b3d56b108bcb97bfdbae83c225d27b4a56f244)
- [gitee仓库](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ed3bbbf5cda107f3490d6166712fe477ca6aa1a36b07e1341863fe84bc68304dc6fb16d5be07b5fccf44c73aecb8fca61)

### 打包命令

`mvn clean package -Dmaven.test.skip=true`

`mvnw clean package -Dmaven.test.skip=true`

在powershell和git shell中执行mvnw会提示错误，请使用当前目录执行命令`./mvnw clean package`

### 运行截图

![](screenshot/home.png)
![](screenshot/detail.png)
![接口](screenshot/api-json.png)


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ed3bbbf5cda107f3490d6166712fe477ca6aa1a36b07e1341863fe84bc68304dc1d32de9e30ecab0205641cd498f9e66e4a4a3de4c376dd1bbd7a068839cd8706)