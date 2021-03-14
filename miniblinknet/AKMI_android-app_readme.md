# OSChina Android [客户端](http://u.720life.cn/g/645cc88ca89f110495efb2e933a9316ecd52c53833103758b2600155c6f053cd)

**源代码请切换置对应的分支，master分支中今后不再放源代码。**

##历史分支

编号 | 标签名 | 发布版本 | 备注
------- | ------- | ------- | -------
1 | [v2.6.2](http://u.720life.cn/g/5c954f4cd4204fb6c09a7e58aa70844d4ed3940b4f88bfab82bdc5e62a7ab4dd4a1d2c261e371a6c74bf34a022c9754e1456351c4819f2d330b75f3dbe7b7f5d)  |v2.6.2(1606121625)| 当前最新版
2 | [v2.4](http://u.720life.cn/g/5c954f4cd4204fb6c09a7e58aa70844d4ed3940b4f88bfab82bdc5e62a7ab4dd4a1d2c261e371a6c74bf34a022c9754e4ea270ca7d7f4f4f864fdfea3f69f1b3) | -- | -- |
3 | [v2.3](http://u.720life.cn/g/5c954f4cd4204fb6c09a7e58aa70844d4ed3940b4f88bfab82bdc5e62a7ab4dd4a1d2c261e371a6c74bf34a022c9754edf8e2a42bd45ff5b26085b564b07ce9e) | -- | 迁移到AndroidStudio |
4 | [v2.2.1](http://u.720life.cn/g/5c954f4cd4204fb6c09a7e58aa70844d4ed3940b4f88bfab82bdc5e62a7ab4dd4a1d2c261e371a6c74bf34a022c9754e3b26b83360cfd98e41142631468b3588) | -- | Eclipse可用 |


##写在前面的话
从2.3版本开始，项目已经完成了gradle化，完全迁移到了android studio，如果想使用eclipse进行该项目的学习，可以clone [tag v2.2.1](http://u.720life.cn/g/5c954f4cd4204fb6c09a7e58aa70844d4ed3940b4f88bfab82bdc5e62a7ab4dd4a1d2c261e371a6c74bf34a022c9754e3b26b83360cfd98e41142631468b3588)，不过需要注意的是，eclipse需要按照开发环境中提到的：进行butterknife注解设置

##开发环境
由于使用了较多的Eclipse项目Library，项目目前使用的是Eclipse。需要提示的是，由于butterknife注解特性，Eclipse需要开启注解功能，详细方法参考[这里](http://u.720life.cn/g/57119b60d4e61e29b9ca0fc66ec82c218ac17a1c5a56532b1de09b8abfb3224b681800c5015767fbc06204ac3fa074ec05cdd749f601a812df68a71466825c9522cb60e8ccaf58a1f8bc879a07748087)。对于使用Android Studio的开发者，可能你们需要等待一段时间，项目目前正在Gradle化。当然，我们也欢迎由你来转换项目并通过PullRequest提交给我们，充分发挥社区化协作的优势。  

##项目简述
1. 底部导航  
    * 主界面的底部TAB导航采用[FragmentTabHost](http://u.720life.cn/g/5c954f4cd4204fb6c09a7e58aa70844d4ca92a97baabc38190f16cf28b5f4d54d5b247c259ed9e4545aa4177727a1d7149ea7e7e78e4d6720030d9f595f66767f097b86cebe3d550fa742c57298ae36b0036db9210d02162a3b2235a02346d6067a85525fbacbf0c1571d315d2699d20)点击底部按钮时切换Fragment。中间的快捷操作按钮使用的是[自定义dialog]http://git.oschina.net/oschina/osc-android-app/blob/master/osc-android-app/src/net/oschina/app/ui/QuickOptionDialog.java  
2. 一级界面  
    * 包括资讯、动弹两个模块，采用[ViewPagerFragment](http://u.720life.cn/g/5c954f4cd4204fb6c09a7e58aa70844d4ca92a97baabc38190f16cf28b5f4d54d5b247c259ed9e4545aa4177727a1d7149ea7e7e78e4d6720030d9f595f66767f097b86cebe3d550fa742c57298ae36b8f175a89c1768e3a3baa07751fa6a8b4e87de0e0a3e38cbdf10a2dcca08e564abfe8523e3b882822adc519650fee510cd6339e62a043ba02463e8a0a3e00d0f8)根据滑动到不同页面显示不同信息。  
3. 详情界面  
    * 详情界面包括[博客详情](http://u.720life.cn/g/5c954f4cd4204fb6c09a7e58aa70844d4ca92a97baabc38190f16cf28b5f4d54d5b247c259ed9e4545aa4177727a1d7149ea7e7e78e4d6720030d9f595f66767f097b86cebe3d550fa742c57298ae36b00f7d3de043ea0859dbaed581c1f5e0d3912f057fb07eb3608126906f5f54d283e9149de5078ee70ed3cbfd58c00822f)，[动弹详情]http://git.oschina.net/oschina/osc-android-app/blob/master/osc-android-app/src/net/oschina/app/fragment/TweetDetailFragment.java [活动详情](http://u.720life.cn/g/5c954f4cd4204fb6c09a7e58aa70844d4ca92a97baabc38190f16cf28b5f4d54d5b247c259ed9e4545aa4177727a1d7149ea7e7e78e4d6720030d9f595f66767f097b86cebe3d550fa742c57298ae36b00f7d3de043ea0859dbaed581c1f5e0d515b1d5417d9544ca51a79ecbf9231438dce220f1e78e023653cf1a355b0eff9)等……是通过在Fragment中的WebView直接loadData  
    * 而详情Fragment的显示则是通过一个外部DetailActivity，来根据传入的参数不同来加载不同的Fragment。  
4. 链接跳转  
    * 整个应用打开链接的规则都定义在UIHelper.openBrowser()方法中，本方法会根据不同的url去解析，如果是www.oschina.net的链接，则会调用相应的界面去展示；如果是git.oschina.net我们目前会使用手机自带的浏览器打开(之后会改为使用[OscGit客户端](http://u.720life.cn/g/5c954f4cd4204fb6c09a7e58aa70844d3ebe649fe0f898bad97c1a21d1d51f785444c53d4f42df30bfc14658342f25e2a5b2e0e6a4af4268e0156bb7199426db)打开  
5. 侧滑菜单  
    * [侧滑菜单](http://u.720life.cn/g/5c954f4cd4204fb6c09a7e58aa70844d4ca92a97baabc38190f16cf28b5f4d54d5b247c259ed9e4545aa4177727a1d7149ea7e7e78e4d6720030d9f595f66767f097b86cebe3d550fa742c57298ae36b0036db9210d02162a3b2235a02346d604ef391202366643a84c6c9f4a4a647d0bea9b62d58d2cf59df3dc530ec4919ab)采用系统的DrawerLayout实现。关于很多朋友好奇的左上角箭头，是采用的开源控件[DrawerArrowDrawable]http://git.oschina.net/oschina/osc-android-app/blob/master/osc-android-app/src/net/oschina/app/widget/DrawerArrowDrawable.java

##依赖包介绍
1. jar包依赖  
  * 网络请求库 **android-async-http** ：http://loopj.com/android-async-http/  
  * 注解绑定控件 **butterknife** http://jakewharton.github.io/butterknife/  
  * 网络图片加载库 **KJFrameForAndroid** http://git.oschina.net/kymjs/KJFrameForAndroid  
  * XML解析库 **xstream** http://xstream.codehaus.org/  
2. 源码依赖  
  * **PhotoView-library** ：用于图片预览界面展示
  * **UmengShareLib** ：用于分享到第三方平台

##开源协议
 
	The MIT License (MIT)
	
	Copyright (c) 2016 OSChina.net
	
	Permission is hereby granted, free of charge, to any person obtaining a copy
	of this software and associated documentation files (the "Software"), to deal
	in the Software without restriction, including without limitation the rights
	to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
	copies of the Software, and to permit persons to whom the Software is
	furnished to do so, subject to the following conditions:
	
	The above copyright notice and this permission notice shall be included in all
	copies or substantial portions of the Software.
	
	THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
	IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
	FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
	AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
	LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
	OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
	SOFTWARE.
	
	





 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ee305fbf0bbdca2fbbea9b1a6cb0c2c8fe4fa46756fcd1b36f4ae263ca2cdb1b4f68c55a07577b1a3ef4be28eda297369)