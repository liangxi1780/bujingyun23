# gclife/gclife-base

### 组件

gclife 基础支撑服务，包括网关、配置中心、服务注册与发现中心、鉴权服务、监控服务等。

服务 |  说明 | 版本 | 端口
---  | ---   | --- | ---
gclife/gclife-gateway | 网关 |  0.0.1 | 13000
gclife/gclife-config | 配置中心 |  0.0.1 | 13010
gclife/gclife-registry | 服务注册中心 |  0.0.1 | 13020-13021
gclife/gclife-monitor | 监控 |  0.0.1 | 13030,13031
gclife/gclife-auth-service | 鉴权 |  0.0.1 | 13040
gclife/gclife-proxy | 反向代理（可选） | 0.0.1 | 13050

### 系统要求

1. 内存 > 8G
2. docker 1.10+
3. docker-compose 1.10+
4. maven 3.0+

### 安装

* 配置 hosts （生产环境另行配置）

    ```bash
    127.0.0.1 gclife-registry gclife-registry-peer1 gclife-registry-peer2 gclife-config gclife-gateway gclife-rabbitmq gclife-monitor gclife-auth-service gclife-proxy gclife-postgres
    ```

* 打包项目并构建 docker 镜像

    ```bash
    cd 进入项目根目录
    mvn clean package
    ```

* 以 docker 容器方式快速启动项目

    ```bash
    docker-compose up -d
    ```

### 测试

> 项目中自带一个 gclife-service-test01 和 gclife-service-test02 的服务，但并未加入 gclife-base 工程中，也没有做 docker 构建配置。请在本地 IDE 中自行编译运行。

1. 获取 Token

    ```bash
    # 对于 HTTP
    curl -X POST -vu client:secret http://gclife-gateway:13000/uaa/oauth/token -H "Accept: application/json" -d "username=admin&password=admin123&grant_type=password&scope=read%20write"
 
    # 对于 HTTPS
    # 其中 --insecure 是因为使用了自签名的ssl证书
    curl -X POST --insecure -vu client:secret https://gclife-proxy:13050/uaa/oauth/token -H "Accept: application/json" -d "username=admin&password=admin123&grant_type=password&scope=read%20write"
    ```

2. 刷新 Token

    ```bash
    curl -X POST --insecure -vu client:secret https://gclife-proxy:13050/uaa/oauth/token -H "Accept: application/json" -d "grant_type=refresh_token&refresh_token=7bbcb043-3149-4d21-bcbc-7d94e8ca03fb"
    ```

3. 调用 test01 服务接口

    ```bash
    # 注意用上一步骤取得的 access_token 替换下面的
    curl -i -H "Authorization: Bearer c0678f31-1a2a-4039-a0fb-6d2afc96f31f" http://localhost:8080/hello?name=bob
    ```

4. 通过 swagger-ui 调用 test 服务接口

    打开网址 http://服务IP:8080/swagger-ui.html



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e61b8b8facfa6f8f45d0071110a666eabaabbe80b01d90811063d08fdd7c30f4b25f16113dd9328f445aec2456973f584)