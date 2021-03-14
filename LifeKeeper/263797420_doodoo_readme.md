# 多多(doodoo)小程序开源版

多多客免费开源的小程序SaaS系统，koa.js + vue.js插件化最佳实践。

## 一键安装
执行命令
`wget https://gitee.com/doodooke/doodoo/raw/master/shell/oneStepInstall.sh && chmod 755 ./oneStepInstall.sh && ./oneStepInstall.sh`

## 安装部署

### 开发环境安装

1. 手动下载zip代码或者使用命令下载`git clone https://gitee.com/doodooke/doodoo.git`

2. 进入代码根目录，然后执行命令安装依赖`npm run bootstrap`

3. 进入mysql数据库，创建`doodoo`数据库

4. 首先修改`.env` `.env.web`数据库配置文件，其他配置项可稍后配置

5. 执行命令启动`npm run dev`，此时会同时启动前端和后端，并且修改前端代码会自动生效

6. 打开浏览器访问`http://127.0.0.1:3000`，会跳转到插件市场

7. 下载开源版会自动安装开源版相关的插件，安装完成之后手动执行命令重启`npm run dev`

8. 打开浏览器访问`http://127.0.0.1:3000`，会跳转到登录页面，默认没有帐号密码，需要自己注册

9. 通过以上步骤即已成功安装多多小程序开源版

### 生成环境部署

1. 通过开发环境安装，调试，配置完成之后，执行以下命令编译启动`npm run web:build && pm2 start pm2.json`



## 常见问题

1. 前后端如何分离启动？

   > 前端开发人员启动命令：`npm run web:dev`
   >
   > 后端开发人员启动命令：`npm run api:dev`

2. 启动成功之后，微信自动登录扫描之后没反应？

   > 默认启动是使用一个域名，如果遇到当前问题，需要使用两个域名，一个绑定后端，一个绑定前端

3. 从插件市场下载到插件为什么没有自动生效？

   > 环境因素，代码启动的方式不同，所有默认生产环境启动推荐使用pm2。当代码没有自动生效时，请手动重启生效



## 问题反馈

在使用中有任何问题，请使用以下联系方式联系我们

QQ群: 874449168(交流群①)

  

EMAIL: 786699892@qq.com

码云: https://gitee.com/doodooke/doodoo

## 官网
[多多客Doodooke小程序](http://u.720life.cn/g/c53677a23cad8270882242d9a3444f876891eaab2689abe067f530f4e66fe98f)

## 缩略图
![](https://gitee.com/doodooke/doodoo/raw/master/thumb/1.jpg)
![](https://gitee.com/doodooke/doodoo/raw/master/thumb/2.jpg)
![](https://gitee.com/doodooke/doodoo/raw/master/thumb/3.jpg)
![](https://gitee.com/doodooke/doodoo/raw/master/thumb/4.jpg)
![](https://gitee.com/doodooke/doodoo/raw/master/thumb/5.jpg)
![](https://gitee.com/doodooke/doodoo/raw/master/thumb/6.jpg)
![](https://gitee.com/doodooke/doodoo/raw/master/thumb/7.jpg)


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ee3c471b206c3bf5d0e088a0acfdab74e21cb7233d24a92cf23dfb5f4d2d6d8576049bbfd7bb1913500f88badbe648a54)