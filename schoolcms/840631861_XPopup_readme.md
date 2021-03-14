## XPopup
![](https://api.bintray.com/packages/li-xiaojun/jrepo/xpopup/images/download.svg)  ![](https://img.shields.io/badge/platform-android-blue.svg)  ![](https://img.shields.io/badge/author-li--xiaojun-brightgreen.svg) ![](https://img.shields.io/badge/compileSdkVersion-26-blue.svg) ![](https://img.shields.io/badge/minSdkVersion-15-blue.svg) ![](https://img.shields.io/hexpm/l/plug.svg)
![](screenshot/logo.png)

### 中文 | [English](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304647926f563762a4819377f96a8d4881eef0c6e332c83a264effbe90bb09ab9b56becffbd1ee1da5c9df05487358a8b374)

功能强大，UI简洁，交互优雅的通用弹窗！可以替代Dialog，PopupWindow，PopupMenu，BottomSheet，DrawerLayout，Spinner等组件，自带十几种效果良好的动画，
支持完全的UI和动画自定义！它有这样几个特点：
1. 功能强大，内部封装了常用的弹窗，内置十几种良好的动画，将弹窗和动画的自定义设计的极其简单；目前还没有出现XPopup实现不了的弹窗效果。
   内置弹窗的UI是固定的，但允许你使用项目已有的布局或者自己的布局，同时还能用上XPopup提供的动画，交互和逻辑封装。
2. UI和动画简洁，遵循Material Design，在设计动画的时候考虑了很多细节，过渡，层级的变化；或者说是模拟系统组件的动画，具体可以从Demo中感受
3. 交互优雅，实现了优雅的手势交互以及智能的嵌套滚动，具体看Demo
4. 适配全面屏，目前适配了小米，华为，谷歌，OPPO，VIVO，三星，魅族，一加全系全面屏手机
5. 通用性，项目需求复杂多变，产品经理天马行空，XPopup力求做到交互和动画通用；至于弹窗的UI和逻辑可能需要你自定义
6. 易用性，所有的自定义弹窗只需继承对应的类，实现你的布局，然后在`onCreate`方法写逻辑即可


**编写本库的初衷有以下几点**：
1. 项目有这样常见需求：中间和底部弹出甚至可拖拽的对话框，指定位置的PopupMenu或者PopupWindow，指定区域阴影的弹出层效果
2. 市面上已有的类库要么功能不足够，要么交互效果不完美，有着普遍的缺点，就像BottomSheet存在的问题一样。比如：窗体消失的动画和背景渐变动画不一致，窗体消失后半透明背景仍然停留一会儿


**设计思路**：
综合常见的弹窗场景，我将其分为几类：
1. Center类型，就是在中间弹出的弹窗，比如确认和取消弹窗，Loading弹窗
2. Bottom类型，就是从页面底部弹出，比如从底部弹出的分享窗体，知乎的从底部弹出的评论列表，我内部会处理好手势拖拽和嵌套滚动
3. Attach类型，就是弹窗的位置需要依附于某个View或者某个触摸点，就像系统的PopupMenu效果一样，但PopupMenu的自定义性很差，淘宝的商品列表筛选的下拉弹窗也属于这种，微信的朋友圈点赞弹窗也是这种。
4. DrawerLayout类型，就是从窗体的坐边或者右边弹出，并支持手势拖拽；好处是与界面解耦，可以在任何界面显示DrawerLayout
5. 大图浏览类型，就像掘金那样的图片浏览弹窗，带有良好的拖拽交互体验，内部嵌入了改良的PhotoView
6. 全屏弹窗，弹窗是全屏的，就像Activity那样，可以设置任意的动画器；适合用来实现登录，选择性的界面效果。
7. 自由定位弹窗(Position)，弹窗是自由的，你可放在屏幕左上角，右下角，或者任意地方，结合强大的动画器，可以实现各种效果。


## ScreenShot

![](screenshot/preview.gif) ![](screenshot/preview_bottom.gif)

![](screenshot/preview_attach.gif) ![](screenshot/preview_drawer.gif)

![](screenshot/bottom_edit.gif) ![](screenshot/fullscreen.gif) 

![](screenshot/horizontal_attach.gif) ![](screenshot/preview_part.gif) 

![](screenshot/image_viewer1.gif) ![](screenshot/image_viewer2.gif) 

![](screenshot/image_viewer3.gif) ![](screenshot/preview2.gif) 

![](screenshot/preview3.gif) ![](screenshot/preview4.gif)

![](screenshot/comment_edit.gif) ![](screenshot/bottom_pager.gif)

![](screenshot/position.gif)

## 快速体验

扫描二维码下载Demo：
![](screenshot/download.png)

如果二维码图片不可见，[点我下载Demo体验](http://u.720life.cn/g/9a66678b1db044b097eec5994fee903d1b8c4d71d4c9a31b8879d34897afd5d5)



## Gradle

首先需要添加Gradle依赖：
```groovy
implementation 'com.lxj:xpopup:1.8.10'
//for androidx.
implementation 'com.lxj:xpopup:1.8.10-x'
```

必须添加的依赖库：
```groovy
//版本号在26以及以上即可
implementation 'com.android.support:appcompat-v7:28.0.0'
implementation 'com.android.support:recyclerview-v7:28.0.0'
implementation 'com.android.support:design:28.0.0'
```



## 使用文档

具体使用方法全在WIKI中，请查看下面各个章节：
- [介绍](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304647926f563762a4819377f96a8d4881ee11ef7a095759fca4dfb81c1cf8d926e88ebc7b6acf46b95e6d40559795745ae9)
- [如何使用内置的弹窗](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304647926f563762a4819377f96a8d4881eebdced594d8e820ab29038d13895184ebbef540e73f460c12ad73cc2af1cb46fc1cd038633fff7f8b085e8dd7c87532b827d6eafd48c818717be2e04952bde649082667cb32bf038d99770e6a232af122)
- [如何自定义弹窗](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304647926f563762a4819377f96a8d4881eeb8e248090ec81c5c8a1e0d5437d91af22bd8979450b8a4eded0631c3492abab96d812b5175cd65eb996030f4169a5004613dab8b56ddd05893ab1be9b64c9a81)
- [如何自定义动画](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304647926f563762a4819377f96a8d4881eeeaac30ed89f8aa8c9b20aeda173373048117877360bad580ffe9fb93bd16b8e7f4a3995c327d9084507c1e56cb4d16e77c14f5f9e0f613c3e9df0c2c1ceb58ee)
- [常用设置](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304647926f563762a4819377f96a8d4881ee6969eceb0af158e87ede6c2e2488277100538379c4ab77c7ad092b172e92833c39359df74c04aa593d4b4c857ee646eebdbaf3b662ff7bb0078460c64f8cfadb)
- [常见问题](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304647926f563762a4819377f96a8d4881ee9e074670f6e6a865cb985158649592fe240185807e059b3d1e0f8787202db5f821865e8e842cd2722803fcd095462ad0d4d4106ff57e4d63233c10cde6fdc5dd)
- [也许你想要这些效果](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304647926f563762a4819377f96a8d4881eeb3947abb93d2b5c84c17db6ecdcddb186381ed47619a76a769bb2e138ba4fb45fdb9f7d1460129ba0f8c1e276c5edb24b50dea1aa7870b536342995e98da3db0b09297d5c861b1df43f40f15ef25d03bf69eeda946e8408e4b6f84581b5fc338)



## 混淆

```
-dontwarn com.lxj.xpopup.widget.**
-keep class com.lxj.xpopup.widget.**{*;}
```



## 谁在用XPopup

我本人很希望您能[点击这里附上](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304647926f563762a4819377f96a8d4881ee3ef96a4fecb6c2318f4deed7d5890c3d)使用这个库的App名或者公司名，这样会给我更大的动力和热情去维护这个类库。

根据热心朋友提供的信息，目前使用XPopup的产品和公司有：
- 海鸥地图（https://cn.gullmap.com/）
- 马自达汽车检测（主要是一个汽车厂商工作人员使用的汽车检测APP）
- 变福侠App
- 进境肉牛检疫追溯系统(App端)
- 太极 (,维术大神作品，VirtualXposed作者， 下载地址：https://www.coolapk.com/apk/me.weishu.exp)
- 爱勘(ican)App
- 医美消费指南(http://u.720life.cn/g/e803f566be8474896d38f22dee65fcdf0dccf6353752350cd4199a5e87c46bf5c273ecdd9e2ae9a65392e7397189a03b)
- 蜜尚（APP名，广州时尚商业城有限公司（时尚集团））
- 关爱岛
- 密籍(下载地址：https://www.coolapk.com/apk/com.rair.unikey)
- 万话筒
- 易果无忧
- Moo日记， 下载地址 https://www.wandoujia.com/apps/8044755
- 智华泊位(重庆即停科技有限公司)
- 中英互译（梅州小白科技有限责任公司 https://sj.qq.com/myapp/detail.htm?apkName=com.messi.languagehelper）
- 采蘑菇（https://a.app.qq.com/o/simple.jsp?pkgname=com.lx.cmg）
- 蜂鸟屋APP，蜂鸟屋SAAS 平板
- 茶臻选（https://android.myapp.com/myapp/detail.htm?apkName=com.aiso.tea&ADTAG=mobile）



## 打个赏

如果你觉得我帮助到了你，节省了你的时间，可以对我进行打赏（打赏时可以附上自己的大名和Github地址），金额随意，以表支持。[打赏名单](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304647926f563762a4819377f96a8d4881eef0c6e332c83a264effbe90bb09ab9b56c1d6f7edbd96baf86cd77e4a677b7e1a)

![](screenshot/pay.png)



## 联系方式

XPopup交流群：**783659607**

Gmail: lxj16167479@gmail.com

QQ Email: 16167479@qq.com

QQ: 16167479



## Licenses

```
 Copyright 2019 li-xiaojun

 Licensed under the Apache License, Version 2.0 (the "License");
 you may not use this file except in compliance with the License.
 You may obtain a copy of the License at

     http://www.apache.org/licenses/LICENSE-2.0

 Unless required by applicable law or agreed to in writing, software
 distributed under the License is distributed on an "AS IS" BASIS,
 WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
 See the License for the specific language governing permissions and
 limitations under the License.
```


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e5400261d221c24e3c9510d74a859a0f9122ca55f62d35808782ab27266d384700d540873103a92cf0e8040780376de15)