主程序名：mkgo-crop.js 
主程序说明：马可波罗旅行html5移动端图片裁剪程序 
作者：qizexi 
邮箱：qizexi@163.com 
公司：马可波罗旅行 
网址：www.mkgo.cn（未上线） 
微信服务号:mkgo-cn 

暂时就叫它裁剪程序吧，说框架似乎有点粗糙。 
裁剪程序的由来：项目需要用到裁剪技术，对用户的图像进行裁剪， 
	但是尝试了网上的一些图片裁剪的程序都不是很理想， 
	要么存在安卓和ios系统的兼容问题，要么就是有些手机上面存在压扁的情况， 
	所以最后决定使用html5+canvas来开发，目前版本的代码比较粗糙， 
	但是裁剪方面是比较完美的。 
	目前只是做了移动端的移动，缩放，就是对触摸事件的监听，电脑端没有实现， 
	感兴趣的朋友可以对程序加以扩展，欢迎一起学习交流。 

使用方式： 
 		var mkCrop = { 
			//图片地址 
			'imgsrc': imgsrc, 
			//图片裁剪确定成功后回调函数 
			'back_fnc': back_fnc, 
			//裁剪左旋转按钮图片路径 
			'leftrimgurl': leftrimgurl, 
			//裁剪右旋转按钮图片路径 
			'rightrimgurl': rightrimgurl, 
			//裁剪完成确定按钮图片路径 
			'okrimgsrc': okrimgsrc, 
			//图片裁剪放置在那个dom节点对象里面 
			'cropparentdom': cropparentdom, 
			//图片预览dom节点对象 
			'preimgdom': preimgdom, 
			//图片裁剪数据信息收集的input对象 
			'cropinputdom': cropinputdom 
		}
		initMkgoCrop(mkCrop); 
		
具体的使用请参考两个例子 
index.html 裁剪图片来源是图片的url 
index-2.html 裁剪的图片来源是拍照或者用户选择的相片信息 
 
示例代码（上传代码已经被屏蔽:)）： 
http://wx1.mkgo.cn/mkgo-crop/index.html 
http://wx1.mkgo.cn/mkgo-crop/index-2.html 
```
这里输入代码
```


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e6c0c60c8d3d2fa123e72ef3ca961c99248befdd799810300142de478e116afea05b03aba0e0ad8db5449a1f9d5ff25a0)