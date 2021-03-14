#docker_ci
when running

in test 
cp ./docker/dev/* ./
./docker_build.sh


in prod
cp ./docker/pord/* ./
./docker_build.sh


after a local docker registry setup

https://docs.docker.com/registry/deploying/
docker run -d -p 5000:5000 --restart=always --name registry \
  -v `pwd`:/var/lib/registry \
  registry:2


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e5031040a7879254fa7c463824f607fa08c6d4bcd0de0f183e639b230690e93b9e513a32073be7b62d689a23ac25c92a7)