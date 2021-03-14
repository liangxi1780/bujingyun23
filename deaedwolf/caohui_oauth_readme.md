# oauth授权登录comoser包

>只是一个包，没有什么依赖

**目录结构：**
```
|--api         第三方授权接口
|--config      配置文件（公共）
|--helper      助手文件
|--lib         核心类库
|--Github.php  Github授权渠道入口文件   
|--Qq.php      Qq授权渠道入口文件   
|--index.php   使用demo   
|--Wx.php      Wx授权渠道入口文件   

```

**使用方法：**

```
在项目中的composer.json 文件中添加如下内容

"require-dev": 
{
    "fankers/oauth": "dev-master"
},
    
"repositories": 
[
    {
        "type": "vcs",
        "url":  "git@gitee.com:fankers/oauth.git"
    }
]
    
```





 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e368d45267b2c6828f23d757d9f6541b29e22d9758c626dfa627b06930b594e38e497005c6083bbcbae2f9d60e391e321)