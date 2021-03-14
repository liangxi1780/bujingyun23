### docker-lnp 是一个封装了 Nginx+php7-fpm 以及多数常用的 php 扩展的 Dockerfile 仓库，旨在快速构建线上或线上 基于Docker的LNMP环境。



> 特性： 

- 1，支持自定义 nginx.conf 及 www.conf（站点配置文件）
- 2，支持自定义 server_name
- 3，支持自定义 document_root
- 4，Docker镜像不封装任何系统环境，仅直接封装Nginx+fpm，但支持bash环境进入Docker容器内部观察调试。由于没有封装系统环境，因此整个Docker运行环境同外部系统环境保持一致。
- 5，小巧，简单，代码通俗易懂
- 6，php扩展可以采用 pecl 方式安装，简单方便
- 7，还在想。。。



> 使用方式：

**step1 构建镜像**
```bash
cd  

sudo docker build -t docker-lnp .
```
这里可能得需要一段时间，因为需要去Docker hub上下载一些需要的包。


**step2 查看镜像**
```bash
sudo docker images
```
如果没有错的话，上面的命令会显示出来刚刚构建好的镜像。


**step3 运行镜像**
```bash
sudo docker run --name docker-lnp -d -e 'SERVER_NAME=www.koma.org' -v /data/www/local:/var/www/html docker-lnp
```
- --name 指定Docker运行名称
- -e 通过环境变量指定nginx虚拟机的server_name
- -v 实现本地(/data/www/local)和容器(/var/www/html)目录共享，这也是nginx虚拟机的document_root，其中/var/www/html是Docker build过程中已经内建好的卷


**step4 通过下面的命令找到映射IP，然后在本地访问**
```bash
sudo docker ps
sudo docker inspect  
```


**step5 调试，如果需要的话**
```bash
sudo docker ps
sudo docker exec -it   bash
```
docker-lnp内部封装了一个简单的bash shell，因此通过上面的命令可以进入到容器内部，做一些你想做的调试操作。


**step6 docker-lnp只封装了Nginx和php，并没有包含Mysql，那么如果你想在PHP中连接本地mysql的话，下面是一点儿个人思路**
- 1，新build一个mysql的容器，然后在运行docker-lnp的时候通过--link实现容器共享
- 2，在build docker-lnp的时候改变net方式（PS：理论上这种方式可行，但是在实践中可能是网络知识不扎实，尝试了各种方式实现不了）


> 最后：
欢迎提建议指正，不定时更新中。。。。。By Koma >  



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e093b8419594023376995052459cdd1d283c2ba9cc2f58a3722be3534b1ed676bbd51e7bba64956ec5bf67eb8e2da88192ef142fc9577a116dc84b753743952a0)