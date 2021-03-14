## 内存存储Client、User信息方式

### 模块介绍

1. `springcloud-service-center`：服务注册中心
2. `springcloud-auth-server`：服务认证中心
3. `springcloud-zuul-gateway`：服务网关
4. `api-user-service`：用户资源服务（资源服务器）

### 运行方式
依次启动：
1. 启动`springcloud-service-center`
2. 启动`springcloud-auth-server`
3. 启动`springcloud-zuul-gateway`
4. 启动`api-user-service`

### 获取AccessToken
```
curl client:clientSecret@localhost:60000/auth/oauth/token -d grant_type=password -d username=17156161666 -d password=123456
```

### 访问用户资源
```
curl -H 'Authorization:Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJhdWQiOlsiYXBpLXVzZXItc2VydmljZSJdLCJ1c2VyX25hbWUiOiIxNzE1NjE2MTY2NiIsInNjb3BlIjpbInJlYWQiXSwiZXhwIjoxNTQxMjMxNTk0LCJhdXRob3JpdGllcyI6WyJST0xFX1VTRVIiXSwianRpIjoiNTU3ZDQ2MGUtZGZkNS00MmIxLWFjNDgtYWRjMTBhODFlMWY1IiwiY2xpZW50X2lkIjoiY2xpZW50In0.6owz8e_Vjo0LZfrPHydibqikX5x7aaeSVTeAdVIpvH4' http://localhost:60000/user/
```


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ec208ee832028842cf80b7e2bb011da5f74f13cf60d435cff272dbd1e678ef7c098d54773706141b8d39479f9d0866e3a2c2ebc17aa2f1f671e35a3bd178fae88a33d806f0f772014ab305956985c6a77)