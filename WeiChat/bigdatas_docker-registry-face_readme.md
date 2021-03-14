# Docker Registry Face

之前画的 [Lazy_balancer](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046028dddd04e55c6a9254ce01234455eecd3a15a7adf13db25b871c2052dd3b12d) (Nginx WebUI) 推出之后广受好评。最近项目使用 Docker，一段时间内，因为持续集成的原因，每天会产生很多镜像，目前只能选择 Registry 、Nexus Repo 之类的产品，但是要么太重，要么太丑。想要点点鼠标就优雅的解决这个问题还是得靠自己，项目又诞生了。因为上一个项目使用了 Django，这里尝试使用 Flask。

因为官方的 Registry 木有脸，所以这里就叫脸了 ... 非专业开发，代码凑合看。

> * 项目基于 [Flask](http://u.720life.cn/g/ffc6fea2abd6b10aaab2b5478d7153f1e84ef3ac19d9f146ad3091273448f679) + [Bootstrap](http://u.720life.cn/g/e23be2821e5181a1a46a005bc6e93d9dc1c8dad0ef41593aa593e12a30fc455b) + [jQuery](http://u.720life.cn/g/bf5ee7c5d8e747312b9dff6cfd25472308f0e1fd43291f641e8858d899a5b79d) 构建，在 Python 2.7 上测试通过；为了保证良好的兼容性，请使用 Chrome 浏览器。
> * 为了轻量化，没有使用数据库等，配置将使用环境变量或者文件的方式保存；需要本地测试的同学请使用 Vagrant 或者 Docker 运行
> * 后端理论支持任何使用 Docker Registry V2 协议的仓库，如 Nexus，官方 Registry 等
> * 镜像路径最高只支持两级，如 xxxx/xxxx:xxx 或 xxxx:xxx

## 项目地址
- GITHUB - https://github.com/v55448330/docker-registry-face
- OSCHINA - http://git.oschina.net/v55448330/docker-registry-face

## 功能
* 支持镜像查询
* 支持镜像批量删除（API 删除）
* 支持镜像标签清单和历史操作记录查看
* 支持 Docker 方式部署
* 适配手机浏览器

## 运行
* 克隆代码
```
mkdir -p /app && cd /app
git clone https://github.com/v55448330/docker-registry-face.git
cd /app/docker_registry_face
```
* 安装运行环境
```
pip install -r pip-freeze.txt 
```
* 启动服务
```
python runserver.py
```
* 访问
```
http://[IP]:3000/  
```
> 若使用容器运行，请配置 `REGISTRY_URL`、`REGISTRY_USER`、`REGISTRY_PASS`，环境变量，此时配置将通过环境变量获取，并 **不可** 在页面修改！
>
> ```
> docker run -d --restart=always -p 3000:3000 \
>     -e REGISTRY_URL=http:// :  \
>     -e REGISTRY_USER=  \
>     -e REGISTRY_PASSWORD=  \
>     v55448330/docker-registry-face:latest
> ```

## 演示
![image](readme_img/1.png)
![image](readme_img/2.png)
![image](readme_img/3.png)
![image](readme_img/4.png)

## 授权

本项目由 [小宝](http://u.720life.cn/g/84d9c51058250fd680e4ca101430ea77edbdea82881084de5210f79ab4e51c2c) 维护，采用 [GPLv3](http://u.720life.cn/g/0faf03d8167674bee364b61e9b7d6858dd29ebe81bbdead4b3a4fad1590c19d36e74f5e3d5e7d037e652b69709323949) 开源协议。欢迎反馈！欢迎贡献代码！



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e6919468432a0edf74d00a4717648da63b45764352081eef84a44b51f287f8d048fbc3cd7359acb8526ed6984a7eb15186622ae9fd03e63a6daa661613e3bb225)