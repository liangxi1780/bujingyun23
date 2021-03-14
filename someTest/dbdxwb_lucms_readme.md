## lucms

## 项目概述

- 产品名称：lucms
- demo: http://lucms.codehaoshi.com/dashboard  账号：dev@lucms.com  密码： 123456

lucms 是一个基于 `laravel5.5*` 与 `iviewjs` 开发的一套后台管理系统。

 
   
   Ucer-admin 
   
   
     
   
   
   
     
   
   
     
   
   
     
   
 

## 功能如下

- 用户认证 —— 登录、退出
- 用户管理 —— 头像上传、资料修改
- 权限系统 —— 多角色、多权限管理
- 权限系统 —— 多角色、多权限管理
- 附件管理 —— 服务器文件管理
- 新闻系统 —— 基础新闻管理

## 开发环境部署/安装

本项目代码使用 PHP 框架 Laravel 5.5 开发，本地开发环境使用 Laravel Homestead。

下文将在假定读者已经安装好了 Homestead 的情况下进行说明。如果您还未安装 Homestead，可以参照 Homestead 安装与设置 进行安装配置。

### 基础安装

- 克隆源代码

克隆 lucms 源代码到本地：

> git@gitee.com:zhjaa/lucms.git

- php 配置修改

1). 配置本地环境，根目录指向 `public`

2). 目录访问权限配置

```text
  $ chmod -R 777 storage
```

3). 安装 passport 客户端, vue api 请求 token 认证要用到
```
 $ art passport:install
```

4). 生成配置文件
```html
cp .env.example .env
你可以根据情况修改 .env 文件里的内容，如数据库连接、缓存、邮件设置等：
```

5). 生成数据表及生成测试数据

/database/lucms.sql
```sh
$ art migrate
```

6). 生成密钥
```html
art key:generate
```

7). 设定图片上传软链接 `storage/app/public/*` 到 `public/storage/images`

8). 配置 .env 
```sh
.

.

.
QUEUE_DRIVER=sync 「同步模式，不使用任何队列」 => redis

.

.

.
```

- 修改 js 配置

1). 修改基本域名

`lucms/lu/src/libs/util.js`
```js
const ajaxUrl = env === 'development'
    ? 'http://lucms.test/api'
    : env === 'production'
        ? 'http://lucms.test/api'
        : 'http://lucms.test/api';
```

`lucms/lu/src/main.js`
```js
const app_url = '//lucms.test/api';
```

`lucms/lu/build/webpack.prod.config.js`
```js
.
.
.
    output: {
        //publicPath: 'http://lucms.test/lu/dist/',  // 修改 https://iv...admin 这部分为你的服务器域名
        publicPath: 'http://lucms.codehaoshi.com/lu/dist/',  // 修改 https://iv...admin 这部分为你的服务器域名
        filename: '[name].[hash].js',
        chunkFilename: '[name].[hash].chunk.js'
    },
. 
.
.
```

### vuejs 安装与运行

1). 开发环境
```
cd lu
cnpm install
npm run dev
```

## 扩展包使用情况

| 扩展包	| 一句话描述	| 本项目应用场景|
| --- | --- | --- |
| [laravel/passport](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046d793ad1b877da8cec40339f68c97c25e6eae3a757db67236ddbd9cab593ddd91)     | jwt 用户认证包          | api 登录认证|
| [Intervention/image](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304646bcb5b273ea3ba0555ac016e73a7b5c080c7a08376aee3010544d87326d614c)     | 图片处理包     | 图片上传裁剪|
| [laravel-permission:~2.7](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046c08be62736a1d8ac2f47a64332e5540c6b12fa922b030fe5f7fb3704a0fb214a)     | 权限管理包     | 权限管理|
| [mews/purifier](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046c6bdeb872382d2297e7108d05ccca3053fba12339bf815333af4bf8da79bdf2a)     | xss过滤     | 富文本编辑器|
| [overtrue/pinyin](http://u.720life.cn/g/54145d0471d91890860f7f8463c030461950c29934e7846d21d3b04581b832eb1146cad7044b3c4356e828ff00a352e4)     | 基于 CC-CEDICT 词典的中文转拼音工具     | 文章 seo 友好的 url|
| [nrk/predis](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046d4e5c5c140b5f21fe057bd5e8631ca50)     | redis 队列驱动器     | 队列管理 |
| [laravel/horizon](http://u.720life.cn/g/ff3399089b3832085c090d6930f1cbc619639cf09a509e401ee78468a60623a90aab39f1d694c87c4a16244d69ed31b64881d7112cb6285254be2dd721bf4c88)     | 队列监控     | 队列监控 |
| [rap2hpoutre/laravel-log-viewer](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304693de5e8bcee61ba2d43601b1135946d0bf1f4063252736d6d9d904dc0e76e6fb05f7e2beee19b83b89e10ababfd597ca)     | laravel 日志查看     | 查看日志 |


## 队列

| Jobs | 一句话描述|
|--- | --- |
| TranslateSlug | 翻译文章 title |





 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e6281d04b8fbda1a9295d0dc810fa83b8f99b40e272cb6a19464b6af2693323f7079f70054e9dc97a04e84a658e100637)