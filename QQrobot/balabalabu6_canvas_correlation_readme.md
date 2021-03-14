### screenshot.js

截图图片指定区域内容并输出图片base64编码到浏览器控制台

## 调用示例

```
screenshot.constructor(canvasDom,{
	sourceImg:'http://img.hb.aicdn.com/38d8f519b3f464a80d85ed9632fed904ed0181f41d632-ZHrigO_fw658',//图像地址
	width:document.body.offsetWidth,//图像显示大小
	height:document.documentElement.clientHeight-50,//图片显示大小
	drawAreaArray : [//要截取的区域坐标以及坐标
		[800,83,462,102],
		[100,50,141,60],
	]
});
```


## 截图方法：
`screenshot.getImagePortion(canvasDom);`
截取出来的内容转换成了base64码，可根据需求随意修改。
## 目前存在的问题
 截取的图片有偏移的情况，正在想办法处理。


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e755982675efdde051fd6f059bb1ad6d9edc973073bf46bf2d08162758fd3ddd03c9ba1c3e72988ade6f4455cd3277dc5970f7b54521a20dc162e6c443d6c9d31)