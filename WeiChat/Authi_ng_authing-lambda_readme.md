# authing-lambda

Using Authing in AWS Lambda.

[Live Demo](http://u.720life.cn/g/7b3137af5432a25b64022b0c2959701a881f30540074cd7c0090401c55b5f31d)

## Deploy lambda

### Install serverless

``` shell
$ npm install serverless -g
```

## Test Lambda

* `cd serverless-authorizer`
* `serverless deploy`
* Notice the displayed endpoint after deployment
* `curl --header "Authorization: allow"  ` - Should work! Authorized!
* `curl --header "Authorization: deny"  ` - Should not work
* `curl --header "Authorization: unauthorized"  ` - Should not work
* `curl --header "Authorization: blabla"  ` - Should not work
* `curl  ` - Should not work

## Run front-end

``` shell
$ npm install
$ npm run serve
```

## Build front-end

``` shell
$ npm install
$ npm run build
```



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6eb760bd82383d3532599735c64016712a40157b30ed71feca16871c9a68da96db57731c5711a17d21edaa8127cc30417e)