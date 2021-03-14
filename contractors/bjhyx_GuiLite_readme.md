# GuiLite - 最小UI框架
- [功能介绍](#功能介绍)
- [实例程序](#实例程序)
- [开发文档](#开发文档)
- [视频链接](#视频链接)
- [致谢](#致谢)
***
## GuiLite是什么鬼？
- GuiLite（超轻量UI框架）是5千行代码的**全平台UI框架**，可以完美运行在iOS，Android，Windows（包含VR），Mac，单片机和**市面所有的 ARM Linux物联网终端设备**上。
- GuiLite可以嵌入在iOS、Android、MFC、QT等其他UI系统中，让你的界面集百家之长，又不失个性。
- GuiLite鼓励混合编程，开发者可以用GuiLite接管UI部分，用Swift，Java，Go，C#，Python开发业务部分。

相比QT、MFC，GuiLite不预设开发者的使用场景，不在具体功能上，大包大揽；用框架的简洁，换取开发的自由；GuiLite在图形绘制上面，力图一步到位，运行效率感人。

## 为什么开发GuiLite？如何使用？
- 任何UI框架都不是为你我而生的，只有掌握核心原理，对其深度定制，才能真正掌握自己的命运！因此，我们开发了GuiLite，希望用这5千行代码揭示UI的核心原理和定制方法。
- 我们不推荐开发者全盘使用GuiLite；鼓励开发者在吃透代码后，根据自身业务特点，修改出更加丰富、个性的界面；或者发展出适合自己的UI框架。
- 为了聚焦UI核心原理，GuiLite会一直保持单片机的代码体量。

## 新功能：动画demo -- HelloAnimation
![HelloAnimation](doc/HelloAnimation.gif)

**信不信由你，代码只有100+行！**[查阅代码](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e75932b06f4e590a70dd42a457637ddb9b6ca79ee3002b276a41167dfd33c56ad872b1f4a071c53a1c9d2419c85873e0833674acc592c7471d8d18feafad1c5524d36480134e1736b30664ec35e13fedd)

## 功能介绍
### 卓越的跨平台能力
在Mac, iOS下的运行效果:

![Mac](doc/Mac.gif) ![iOS](doc/Ios.landscape.gif)

在Android，嵌入式ARM Linux下的运行效果:

![Android](doc/Android.gif) ![Linux](doc/Linux.gif)

在Windows混合现实下的运行效果:

![Win MR](doc/WinMR.gif)

### 万国语和墙纸
墙纸：
![unicode](doc/wallpaper.jpg)

万国语(unicode)：
![unicode](doc/unicode.jpg)

[如何制作多种文字/位图资源?](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304638f0e26956953fb595b5ea8b0426585fe389d0827e0ccd02f5c6fee2b54aa43b)

### “换肤”功能
![multi-theme](doc/multi-theme.png)

[如何“换肤”？](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e75932b06f4e590a70dd42a457637ddb9b6ca79ee3002b276a41167dfd33c56ad869468bbe7c65615afccfddad54021c770c7ed12578f80509a02986b46140f9c9b23b194b92226dc0cc015607bad3332c16358b5d462054f54018118fcc3ab01)

### 自我监控
**上报“编译/运行”情况至“云端”：**

![BuildInfo](doc/BuildInfo.png)

**同步“本地数据”至“云端”：**

![DataOnCloud](doc/data_on_cloud.png)

## 实例程序
GuiLite只是一个框架，本身并不能生成UI。为了能够展示如何用GuiLite开发App，我们提供了一些实例程序给大家参考。
- 点击[这里](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e75932b06f4e590a70dd42a457637ddb9cafdd4f90d95e594e4bc0c2954e7f3e1)预览UI效果。
- 实例程序的功能说明：

| 实例名称 | 支持的平台 | 功能简介 | 编译方法 | 难度 |
| --- | --- | --- | --- | --- |
| HelloGuiLite | Windows, Linux | 初始化GuiLite，加载资源，布局界面元素，按钮响应 | [编译/运行](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e75932b06f4e590a70dd42a457637ddb9b6ca79ee3002b276a41167dfd33c56ad4f0eef9699c6bb3dffa4d188e7e85fad1b2adb328b92b7091ffad7b2f5506cc3) | 初级 |
| HelloFont | Windows, Linux | 显示多种语言（不限：中、英文） | [编译/运行](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e75932b06f4e590a70dd42a457637ddb9b6ca79ee3002b276a41167dfd33c56ad22336813da3e8e976ead23a6c707516cee331c5537a1626c1091e3760a3453c8) | 初级 |
| HelloAnimation | Windows, Linux | 动画的应用 | [编译/运行](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e75932b06f4e590a70dd42a457637ddb9b6ca79ee3002b276a41167dfd33c56ad872b1f4a071c53a1c9d2419c85873e08c7d95b3188ded34737b343578dd96eaf) | 初级 |
| HelloSlide | Windows, Linux | 滑屏界面的应用 | [编译/运行](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e75932b06f4e590a70dd42a457637ddb9b6ca79ee3002b276a41167dfd33c56ad0ff1ec32b1ab8d8bde1889a94748c296cd1dd9f165c7b07203f680e29d654e79) | 中级 |
| HostMonitor | iOS, Mac, Android, Windows, Linux | 创建复杂界面，扩展自定义控件，适配全平台 | [编译/运行](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e75932b06f4e590a70dd42a457637ddb9b6ca79ee3002b276a41167dfd33c56ad869468bbe7c65615afccfddad54021c7b2b3a2fcbe1551db2dd4fe626d703389) | 高级 |
## 开发文档
- [如何编译?](doc/HowToBuild.md)
- [设计原理](doc/CodeWalkthrough-cn.md)
- [UML示意图](doc/UML.md)
- [如何布局UI?](doc/HowLayoutWork.md)
- [如何传递消息?](doc/HowMessageWork.md)

## 视频链接:
- [GuiLite简介](http://u.720life.cn/g/f18b4a37eaf8af1318d738e4ab50599579e26468ca5b657e37710243a17c33666ec0f3fcd64994581d8543bde561ad48)
- [3D GuiLite](http://u.720life.cn/g/f18b4a37eaf8af1318d738e4ab50599579e26468ca5b657e37710243a17c33660c72fa41641d3c99a1fd7044de561bc6)

## GitHub链接
[GitHub链接](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304638f0e26956953fb595b5ea8b0426585faaa7b003fa57cd780a1ccf0b7b8a4ef8)

## 致谢
### 感谢开发者群的所有同学，是你们塑造了今天的GuiLite！也欢迎新的大神/小白加入我们。
![QQ group: 527251257](doc/qq.group.jpg)
### 感谢来自码云用户的捐赠，您的每一分钱都会用来帮助急需帮助的中国儿童或家庭。




 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ed3314b8073dd445e4828806bd02652af5ad72a1188caf2b2c9ed8010e52a0041cddaf5c70f913531029c5baa35ac7e22)