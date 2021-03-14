
一个基于Vue开发的权限管理系统，后续会增加更多实用的功能。

### 在线体验
演示地址：https://www.admin.zhontai.net/

文档地址：https://www.zhontai.net/

*********************************************************
### 项目下载后，首先安装依赖包
```
npm install
或
npm install --registry=https://registry.npm.taobao.org
```

### 安装成功后，运行即可
```
npm run serve
```

#### Tips：



```
如果你想换端口，可以直接修改根目录下的 vue.config.js 文件

  devServer: {
    port: 3333, // 当前 admin 项目的端口号

    proxy: {
      // 配置代理
      "/api": {
        target: "http://localhost:8081",//改成后端api地址

```

### 开发过程中检查错误，可执行lint
```
npm run lint
```

### 想要发布，执行bulid打包成dist
```
npm run build
```



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e7dcfab1923895b6a620a57cc7176d78d9a54012ea232e06a2aad4fa6f37b63b0c977f8aca1ad0fd0a785681f69dade59)