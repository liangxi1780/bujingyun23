# serverms

#### 介绍
基于spring cloud 2.1.0、spring security、oauth2.0、jwt微服务架构；提供zuul网关统一授权，oauth认证，Header 头携带Authorization jwt token授权，前后分离鉴权，eureka服务治理，fegin client内部调用，提供密码模式、code授权码模式认证。

#### 软件架构
spring cloud 2.1.0、spring security、oauth2.0、jwt、redis

#### 使用说明
说明：[http://blog.lenosp.cn/#/detail/17873126](http://u.720life.cn/g/84cbd937a2fb8dda97f90fee81aee5650d5cfb8d3fafe64c779e4a6bbe2c47ec6250c773cb9f0c9491a3226cd449acb0)
一张git图：
![图片说明](https://s2.ax1x.com/2019/04/04/AgXZw9.gif "图片说明")
1、下载maven依赖
2、启动五个服务，等待eureka注册服务
```bash
密码模式获取token：curl -X POST 
              http://localhost:8899/auth/oauth/token 
              -H 'cache-control: no-cache' 
              -H 'content-type: multipart/form-data; boundary=----WebKitFormBoundary7MA4YWxkTrZu0gW' 
              -F password=1234 
              -F grant_type=password 
              -F client_id=web 
              -F username=admin 
              -F client_secret=secret 
              -F scopes=app
 授权码获取token：
 1、先登录 支持ajax http  curl -X POST 
                 http://localhost:8899/auth/login 
                 -H 'Content-Type: application/x-www-form-urlencoded' 
                 -H 'X-Requested-With: XMLHttpRequest'
                 -d 'username=admin&password=1234'
 2、curl -X GET 
            'http://localhost:8899/auth/oauth/authorize?response_type=code&client_id=web&redirect_uri=http://www.baidu.com&scope=app'
 3、根据code获取token  curl -X POST 
                    http://localhost:8899/auth/oauth/token 
                    -H 'content-type: multipart/form-data; boundary=----WebKitFormBoundary7MA4YWxkTrZu0gW' 
                    -F grant_type=authorization_code 
                    -F code=E63HGD 
                    -F client_id=web 
                    -F client_secret=secret 
                    -F redirect_uri=http://www.baidu.com
```


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e17427ba8bd5041ecce1895b04fa58eaf7245975cc4dede8b1f467eed1920755d33e7f96433db9c4e53fe413932fe9861)