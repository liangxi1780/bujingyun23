---
title: "基于uni-app多平台管理系统模板uniapp-admin"
author: silianpan
date: 2019-10-26
output: word_document
---

## 基于uni-app多平台管理系统模板uniapp-admin

 
 
 
 
 

[H5在线预览](http://u.720life.cn/g/45538919818c829156f00f8d274e9a033eccf8b86ba6860f930425c57edeb2e3)

[Android APK 下载地址](http://u.720life.cn/g/cb1b492f202d07a3ed9c8a6ae4543755a984a02a2c9338284ba40d055f6194ae08e477c0c778c4e3c711b942506e03c28849f209949e2f381c636fd5a473f77a)

[Github](http://u.720life.cn/g/54145d0471d91890860f7f8463c030469960db3b5cdc254a4fb655a06bd8e5c00f26d7c44f432ed183a486b74ae53206)

[Gitee](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6eef9937d9dc0fe702c25a2b46e905186cff719666615c0a1f55ca11fd34a1c27c)

### 一、前言

&emsp;&emsp;uniapp-admin是基于uni-app开发的管理系统模板。该模板集成了如下的功能：

* **UI方面**：登陆模板、顶部固定搜索框、顶部滑动选项卡、字段信息卡片、一周信息卡片、时间轴
* **功能方面**：下拉刷新上拉加载功能、文件在线预览功能
* **内置组件**：底部标签导航、顶部导航栏、商品导航、uni ui
* **第三方插件**
  * **UI库** [colorUI css库](http://u.720life.cn/g/56a49702a3afd725f8e57f2b0f403ab0b1f28ff7e3d4835e80e0290c80bea17e02ed58c6734ebad72cdaf76c706df3ea)、[ThorUI组件库]https://ext.dcloud.net.cn/plugin?id=556
  * **其他** [uCharts高性能跨全端图表](http://u.720life.cn/g/880fcbad480e0a6ae5a3f8cfae23ba1303b1eb9fe4b05c345944a2c9efdfe7823225126d47b9bd20b8e553d090c4f20e)、[mescroll-支持uni-app的下拉刷新上拉加载组件 ](http://u.720life.cn/g/880fcbad480e0a6ae5a3f8cfae23ba1303b1eb9fe4b05c345944a2c9efdfe782cf364a05ce1645478144df23d61e7cf5)、[日期时间选择器tui-datetime]http://ext.dcloud.net.cn/plugin?id=239
* **解决方案(重要)**
  * 文件在线预览方案，另见文章[《跨平台（uni-app）文件在线预览解决方案》](http://u.720life.cn/g/54145d0471d91890860f7f8463c030469960db3b5cdc254a4fb655a06bd8e5c0333af2d89a6e6878d86f4325de12a7b0f8ca71036453f9e81148191bf9396a298fcb55975eff8d7646c60e8eef9394e0)
  * 开发环境和生产环境跨域方案
  * APP整包升级/更新方案
  * API调用方案
  * 消息推送方案，另见文章[《uni-app消息推送方案》](http://u.720life.cn/g/54145d0471d91890860f7f8463c030469960db3b5cdc254a4fb655a06bd8e5c0333af2d89a6e6878d86f4325de12a7b0f145376fd47b1d4d103747f3832a00ec2b50fb1157812797b4bdbb0a6ddc9bbb)

&emsp;&emsp;如果有欠缺的地方，或者有更好的想法，大家可以**多多交流**，文章最后可以加我。

### 二、开发环境和生产环境跨域方案

> 跨域的解决方法之一就是采用**代理**

#### 2.1 开发环境

* 在manifest.json源码视图中，修改h5部分，添加端口port和代理proxy。

```json
"h5" : {
  "devServer" : {
      "port" : 9090,
      "disableHostCheck" : true,
      "proxy" : {
          "/ua/ua-service" : {
              "target" : "http://localhost:8080",
              "changeOrigin" : true,
              "secure" : false,
              "pathRewrite" : {
                  "^/ua" : ""
              }
          },
          "/ua-service" : {
              "target" : "http://localhost:8080",
              "changeOrigin" : true,
              "secure" : false
          }
      }
  },
  "title" : "uniapp-admin",
  "router" : {
      "mode" : "hash",
      "base" : "/ua"
  }
}
```

* 根据不同平台，自定义全局配置baseUrl，[参考代码](http://u.720life.cn/g/54145d0471d91890860f7f8463c030469960db3b5cdc254a4fb655a06bd8e5c0333af2d89a6e6878d86f4325de12a7b0e64d3690fa8dc82648c769af900d98c53b1bc86aaa48b6925a19d4cd7a34a69b)

> 原理：h5端配置api前缀，然后proxy代理（在manifest.json的proxy）；
> APP端不存在跨域问题，直接配置全域名或ip地址即可

```js
/**
 * ip地址或域名
 */
const ipAddress = 'http://localhost:8080'
// 文件访问地址
const fileAddr = 'http://localhost:8082/fileUpload/'
/**
 * api前缀
 */
const apiPrefix = '/ua-service'
/**
 * 针对不同平台的baseUrl
 */
const getBaseUrl = () => {
	// #ifdef H5
	return apiPrefix
	// #endif
	// #ifndef H5
	return ipAddress + apiPrefix
	// #endif
}
export default {
	/**
	 * 针对不同平台的baseUrl
	 */
	baseUrl: getBaseUrl(),
	fileAddr
}
```

* 在ui.request的参数选项中配置baseUrl，[参考代码](http://u.720life.cn/g/54145d0471d91890860f7f8463c030469960db3b5cdc254a4fb655a06bd8e5c0333af2d89a6e6878d86f4325de12a7b0dc7723647c5c3b86a406dfbe67bc5462)

```js
// 设置默认配置
minRequest.setConfig((config) => {
	config.baseURL = globalConfig.baseUrl
	return config
})
```

#### 2.2 生产环境

> 生产环境的跨域，典型的方案就是采用Nginx代理

配置如下：

```conf
# 前端访问代理
location /ua {
  alias /root/ua;
  index index.html index.htm;
  try_files $uri $uri/ /index.html?/$request_uri;
}
# 服务端代理，对应开发环境proxy
location ~/ua/ua-service/* {
  rewrite ^/ua/(.*)$ /$1 break;
  proxy_pass http://service;
  proxy_http_version 1.1;
  proxy_set_header Upgrade $http_upgrade;
  proxy_set_header Connection "upgrade";
  proxy_connect_timeout 360000s;
  proxy_read_timeout 360000s;
  proxy_send_timeout 360000s;
}
# 服务端代理，对应开发环境proxy
location ~/ua-service/* {
  proxy_pass http://service;
  proxy_http_version 1.1;
  proxy_set_header Upgrade $http_upgrade;
  proxy_set_header Connection "upgrade";
  proxy_connect_timeout 360000s;
  proxy_read_timeout 360000s;
  proxy_send_timeout 360000s;
}
```

其中*proxy_pass http://service*的service是配置在nginx的http{}下的后端服务

```config
upstream service {
  server 127.0.0.1:8080 max_fails=1 fail_timeout=10s;
}
```

rewrite ^/ua/(.*)$ \/\$1 break;是路径替换，第一个参数是正则表达式，\$1是正则表达式中第一个括号内容。

### 三、APP整包升级/更新方案

参考文档，[uni-app 整包升级/更新方案 ](http://u.720life.cn/g/09e6d6b5dd3d7091e3f3f255e4f37c2000817b11caff78f705968127e2b3809bbce61ff71cbd49df0f61b2a11ae2a0a4)，另外也有，[uni-app 资源在线升级/热更新](http://u.720life.cn/g/09e6d6b5dd3d7091e3f3f255e4f37c2000817b11caff78f705968127e2b3809baa07517fd146c21d4d77bddcb1d5378b)

本项目是采用整包升级更新方案，如下：

```js
/**
  * app整包更新检测
  */
appUpgrade() {
  //#ifndef APP-PLUS
  uni.showToast({
    title: '目前只支持Android版本软件更新',
    icon: 'none'
  })
  //#endif
  //#ifdef APP-PLUS
  uni.getSystemInfo({
    success: sysInfo => {
      let platform = sysInfo.platform
      plus.runtime.getProperty(plus.runtime.appid, (wgtinfo) => {
        // app版本字符串如：1.1.0
        // this.appInfo.version = wgtinfo.version
        // app名称
        // this.appInfo.name = wgtinfo.name
        let params = {
          appid: plus.runtime.appid,
          // app整数版本号，如110，一定要用versionCode做判断
          version: wgtinfo.versionCode,
          platform: platform
        }
        this.$minApi.findUpgradeApp(params).then(appRes => {
          if (appRes.appid) {
            uni.showModal({
              title: "下载更新提示",
              content: appRes.note,
              showCancel: false,
              confirmText: '确定',
              success: sucRes => {
                if (sucRes.confirm) {
                  plus.runtime.openURL(appRes.url)
                  // uni.downloadFile({
                  //     url: appRes.url,
                  //     success: res => {}
                  // })
                }
              }
            })
          } else {
            uni.showToast({
              title: '已经是最新版本了。',
              icon: 'none'
            })
          }
        })
      })
    }
  })
  //#endif
}
```

 注意：一定要使用plus.runtime.getProperty(plus.runtime.appid, (wgtinfo) =>())，回调函数返回的wgtinfo对象的versionCode做判断，wgtinfo.version是版本字符串，wgtinfo.name是app应用名称 

### 四、API调用方案

核心是调用uni.request，[参考代码](http://u.720life.cn/g/54145d0471d91890860f7f8463c030469960db3b5cdc254a4fb655a06bd8e5c0333af2d89a6e6878d86f4325de12a7b0055284a67612094c3dad05a5514e6ba257cd592a39e3b4b3cb4f90232e925531)

```js
request(options = {}) {
  options.baseURL = options.baseURL || this[config].baseURL
  options.dataType = options.dataType || this[config].dataType
  options.url = MinRequest[isCompleteURL](options.url) ? options.url : (options.baseURL + options.url)
  options.data = options.data
  options.header = { ...options.header,
    ...this[config].header
  }
  options.method = options.method || this[config].method

  options = { ...options,
    ...MinRequest[requestBefore](options)
  }

  return new Promise((resolve, reject) => {
    options.success = function(res) {
      resolve(MinRequest[requestAfter](res))
    }
    options.fail = function(err) {
      reject(MinRequest[requestAfter](err))
    }
    uni.request(options)
  })
}
```

### 五、消息推送方案

另见文章[《uni-app消息推送方案》](http://u.720life.cn/g/54145d0471d91890860f7f8463c030469960db3b5cdc254a4fb655a06bd8e5c0333af2d89a6e6878d86f4325de12a7b0f145376fd47b1d4d103747f3832a00ec2b50fb1157812797b4bdbb0a6ddc9bbb)

### 六、问题解决

#### 6.1 怎么获取应用真正的名称和版本信息？

一定要使用plus.runtime.getProperty(plus.runtime.appid, (wgtinfo) =>())，回调函数返回的wgtinfo对象的versionCode做判断，wgtinfo.version是版本字符串，wgtinfo.name是app应用名称

#### 6.2 APP端，模板中v-for不能调用方法，如：v-for="xxx in func(xxx)"，这种情况下，func方法不会调用。具体原理不太清楚，还请大佬能解释一下不？

解决办法：提前将数据格式化好，然后套上模板。

### 七、后续计划

- [x] 消息推送

大家也可以提出想要的模板或功能

### 八、效果

 

#### H5

 

#### Android APK

 

 

 

####  开源不易，且用且珍惜！ 

 
 赞助作者 
 
 
 

 
 

转载请注明：[溜爸 » 基于uni-app多平台管理系统模板uniapp-admin](http://u.720life.cn/g/cb1b492f202d07a3ed9c8a6ae45437558ead6fc638d3bad80d7e7b5792af41477c1888e1c6a919dd799ec8f9ff77177c0db131683240b492905d39ad2bb310b9)



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6eb6a06d61dc88e9aaed20e1743525008b7aa73f0fc320e3fd8ef96489bffa2043d9b56a57244772e3e6f2ba68b2dbc129460056004d123ccce871c6271b8462f0)