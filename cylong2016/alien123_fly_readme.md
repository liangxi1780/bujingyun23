Fly Template 由 layui 官方社区（Fly社区）友情抽取，页面基于 layui 搭建而成，提供了全屏和固宽两类排版，并且具备响应式适配能力，可很好地作为简约型问答社区的页面支撑。

# 目录说明  
```
├─html 可直接预览的模板文件
│  ├─jie
│  ├─common
│  └─user
├─res 静态资源
│  ├─css
│  ├─images
│  │  ├─avatar
│  │  └─other
│  ├─layui
│  └─mods 模板业务模块
└─views 动态模板参考（NodeJS端）
    ├─jie
    ├─common
    └─user
```

# 全屏风格
模板提供了全屏风格，你可以打开 html/full.html预览效果，使用全屏风格只需在原有css的基础上，引入 css/full.css即可。

# 字符解析
该模板自带一个特定语法的编辑器，当你把内容存储到数据库后，在页面读取后浏览，会发现诸如“表情、代码、图片”等无法解析，这是因为需要对该内容进行一次转义，通常来说这是在服务端完成的，但鉴于简单化，你还可以直接在前端去解析，在模板的detail.html中，我们已经把相关的代码写好了，你只需打开注释即可（在代码的最下面）。

当然，如果觉得编辑器无法满足你的需求，你也可以把该编辑器换成别的HTML编辑器或MarkDown编辑器。

# 在线预览
http://fly.layui.com/

# 开源协议
MIT License

# 社区相关
* [Fly社区](http://u.720life.cn/g/3af817c5bf081df3449053a61af9e608780f3272995e5f13892b195ff4f245d5)
* [码云](http://u.720life.cn/g/3e7e8f170da15d1979f4c6b1321cc36b493b907fe1ea3dd772339ba453ee6b7181f636db1c04f410fa02931c6d8ba0e4)
* [GitHub](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304695c3a5433c01a43159c16cbc6e491a82)



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ea2b11629014777bd030e2b6c7f2f1ec8e29bab26323f8d1b78d62992ee74f6c76b159f969155116f7d0e0dfe06bc0622)