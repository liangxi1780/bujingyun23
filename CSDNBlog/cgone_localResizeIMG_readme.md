[![Build Status](https://travis-ci.org/think2011/localResizeIMG.svg?branch=master)](https://travis-ci.org/think2011/localResizeIMG)
[![npm version](https://img.shields.io/npm/v/lrz.svg)](https://www.npmjs.com/package/lrz)
[![npm](https://img.shields.io/npm/l/express.svg)]()

# 🚨重要!!

很抱歉，这个项目已不再维护了，可能很长一段时间都不会更新了。

# 演示

![](http://think2011.github.io/localResizeIMG/test/demo.gif)

# 试试

![](https://raw.github.com/think2011/localResizeIMG/master/test/qrcode.png)


[点我直接进入演示页面](http://u.720life.cn/g/61e0b272d85151ad2da15964d0b3ab869586edf6dbebf34133b56d8ccd3c87346c1dfdcb401ea8d1f6bd9de2f1180fc3)

# 简述
在客户端压缩好要上传的图片可以节省带宽更快的发送给后端，特别适合在移动设备上使用。

# 为什么需要

1. 已踩过很多坑，经过几个版本迭代，以及很多很多网友的反馈帮助、机型测试
    * 图片扭曲、某些设备不自动旋转图片方向，没有jpeg压缩算法..
    * 不支持new Blob,formData构造的文件size为0..
    * 还有某些机型和浏览器（例如QQX5浏览器）莫名其妙的BUG..
    
2. 按需加载（会根据对应设备自动异步载入JS文件，节省不必要带宽）

3. 原生JS编写，不依赖例如`jquery`等第三方库，支持AMD or CMD规范。

> 尽管如此，在某些 `Android` 下依然有莫名其妙的问题，在您使用前，请一定大致浏览下 [issues](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046fb535391cde2adc5d271e891da48db18f48cebe22b31054a9e63a194c4fcc8d04a81fb4593f3efe76b99e682389df3e9)

# 如何获取

通过以下方式都可以下载：

1. 执行`npm i lrz`（推荐）
2. 执行`bower install lrz`

接着在页面中引入
```html
  
```

# 如何使用

### 方式1:

如果您的图片来自用户拍摄或者上传的，您需要一个`input file`来获取图片。

```html
 
```

接着通过change事件可以得到用户选择的图片
```js
document.querySelector('#file').addEventListener('change', function () {
	lrz(this.files[0])
        .then(function (rst) {
            // 处理成功会执行
            console.log(rst);
        })
        .catch(function (err) {
            // 处理失败会执行
        })
        .always(function () {
            // 不管是成功失败，都会执行
        });
});
```

### 方式2：

如果您的图片不是来自用户上传的，那么也可以直接传入图片路径。

```js
lrz('./xxx/xx/x.png')
        .then(function (rst) {
            // 处理成功会执行
        })
        .catch(function (err){
            // 处理失败会执行
        })
        .always(function () {
            // 不管是成功失败，都会执行
        });
```

# 后端处理

[后端处理请查看WIKI。](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046fb535391cde2adc5d271e891da48db1807327518b24334dc4572f4876638f78b)


# API

[具体参数说明请查看WIKI。](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046fb535391cde2adc5d271e891da48db1807327518b24334dc4572f4876638f78b)

# 兼容性

IE10以上及大部分非IE浏览器（chrome、微信什么的）

# FAQ

[有疑问请直接在 issues 中提问](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046fb535391cde2adc5d271e891da48db18f48cebe22b31054a9e63a194c4fcc8d04a81fb4593f3efe76b99e682389df3e9)

```
请一定记得附上以下内容：💡
请一定记得附上以下内容：🙈
请一定记得附上以下内容：💡

平台：微信..
设备：iPhone5 IOS7..
问题：问题描述..
```

* Q：有时拍摄完照片后，页面自动刷新或闪退了。
* A：虽然已作了优化处理，但内存似乎还是爆掉了，常见于低配android手机，建议每次只处理一张图片。

* Q: 怎么批量上传图片?
* A: 您可以自己写个循环来传入用户多选的图片，但在移动端上请谨慎处理，原因同上。

* Q: 直接传入图片路径的无法生成图片
* A: 可能是跨域的问题，具体请看[CORS_enabled_image](http://u.720life.cn/g/a69e8f5dba5b4106ccc3875c547b14848492c6553bd52bb7c59a8587071dd1265b767b2b60ec6d6803b7855507c32936f6119098540f326e106c5d6fa7405d13a6dc4612540dad4208be81116f02f05c)

* Q: 想要商用可以吗？
* A: 没问题，但请留意issue里已知的问题。

# 感谢

* @dwandw
* @yourlin
* @wxt2005

以上在之前的版本帮忙参与维护的朋友，以及提出问题的朋友们，真的真的很感谢你们。：D



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6efb353cbf25ef9236d505b5c409c2e1581e997b48b45f4abc26e79e3eaf3f062d6ae8c728bdc508a110eddf13d1c8a6d0)