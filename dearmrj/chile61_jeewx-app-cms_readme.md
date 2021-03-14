### 项目介绍
Jeewx-app-cms是jeewx开发的小程序网站项目，基于小程序wepy语言，具备cms网站的基本功能，能够打造简单易用的公司官网。

### 开发常用命令

#### 1、安装（更新）wepy命令行工具
	npm install wepy-cli -g

#### 2、安装依赖包
	npm install

#### 3、开发实时编译
	npm run dev

#### 4、生产压缩
	npm run build //上传代码时，请先执行此命令，否则会提示包体积过大

#### 开发使用说明(重要)

1、使用微信开发者工具-->添加项目，项目目录请选择dist目录。

2、微信开发者工具-->项目-->关闭ES6转ES5。  重要：漏掉此项会运行报错。  

3、微信开发者工具-->项目-->关闭上传代码时样式自动补全。   重要：某些情况下漏掉此项也会运行报错。  

4、微信开发者工具-->项目-->关闭代码压缩上传。   重要：开启后，会导致真机computed, props.sync 等等属性失效。  


### 技术交流

*   官 	  网：	www.jeewx.com
*   邮    箱：	jeecg@sina.com
*   QQ交流群：	131894955
*   文档帮助：

  * [wepy开发文档](http://u.720life.cn/g/bf465cec2447162e50307102004cc72dfe39c327076d3a1b2197d4b30abda5e2) 
  * [小程序开发文档](http://u.720life.cn/g/bf465cec2447162e50307102004cc72dfe39c327076d3a1b2197d4b30abda5e2)
  * [小程序实战开发](http://u.720life.cn/g/612a1b449e9993b7ddf793e732dee5bece1b76c9452b6f35c404abec7db745af1a2213705199eca11f08511232aa300a)

### 在线体验
扫码下方二维码体验小程序。

![github](http://img-blog.csdn.net/20180605175157225?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3poYW5nZGFpc2NvdHQ=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70 "jeewx-app-cms")
	
### 目录结构

    ├── api
    │   └── api.js              //接口
    ├── app.wpy                 //入口文件
    ├── components                  //组件
    │   └── tab.wpy             //选项卡组件
    ├── img                  //图片文件夹
    │   └── alert.png
    │   └── contact.png
    │   └── contact_selected.png
    │   └── error.png
    │   └── icon_API.png
    │   └── icon_API_HL.png
    │   └── icon_component.png
    │   └── icon_component_HL.png
    │   └── jeecg.png
    │   └── location.png
    │   └── logo.png
    ├── pages                   //页面
    │   └── article.wpy			//文章详情页
    │   └── articleList.wpy		//文章列表页
    │   └── contact.wpy			//联系我们页
    │   └── index.wpy			//首页
    │   └── theme.wpy			//专题页
    └── utils                   //工具类
    │   ├── md5.js                  //md5
    │   ├── tip.js                  //提示弹框组件
    │   ├── util.js                 //工具
    │   └── wxRequest.js            //ajax请求
    └── wxParse             //富文本
        ├── html2json.js
        ├── htmlparser.js
        ├── showdown.js
        ├── wxDiscode.js
        ├── wxParse.js
        ├── wxParse.wxml
        └── wxParse.wxss    


		
### 功能截图

![github](http://img-blog.csdn.net/20180604194422754?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3poYW5nZGFpc2NvdHQ=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70 "jeewx-app-cms")
![github](http://img-blog.csdn.net/20180604194436526?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3poYW5nZGFpc2NvdHQ=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70 "jeewx-app-cms")
![github](http://img-blog.csdn.net/20180604194441960?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3poYW5nZGFpc2NvdHQ=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70 "jeewx-app-cms")
![github](http://img-blog.csdn.net/20180604194447937?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3poYW5nZGFpc2NvdHQ=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70 "jeewx-app-cms")
![github](http://img-blog.csdn.net/20180604194452656?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3poYW5nZGFpc2NvdHQ=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70 "jeewx-app-cms")



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e3b5c65c77141251e7b7e2ebce27b19217d682b05de2b1676328a8ddf8e08bd70f8cf4c97b224600f633e57ad107a6ace)