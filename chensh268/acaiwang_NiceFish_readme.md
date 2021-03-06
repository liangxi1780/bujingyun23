
 

# NiceFish（美人鱼）

谢谢大家，过了1000个星儿了，我可以拿到一个开源奖杯了 :) 

既然求星儿是有效的，那就继续求星儿、求捐助。

NiceFish是一个系列项目，都是Angular这个技术栈。

- NiceFish：美人鱼，这是一个微型Blog系统，前端基于Angular 4.x + PrimeNG。http://git.oschina.net/mumu-osc/NiceFish/

- NiceFish-Admin：这是系统管理界面，基于Angular 4.x+PrimeNG，http://git.oschina.net/mumu-osc/NiceFish-Admin

- NiceFish-ionic：这是一个移动端的demo，基于ionic。http://git.oschina.net/mumu-osc/nicefish-ionic

- NiceFish-SpringMybatis：这是Java版后台服务，http://git.oschina.net/mumu-osc/NiceFish-SpringMybatis 

- NiceBlogElectron：https://github.com/CN-Tower/NiceBlogElectron ,这是一个基于Electron的桌面端项目，把NiceFish用Electron打包成了一个桌面端运行的程序。这是由ZTE中兴通讯的前端道友提供的，如果您正在研究如何利用Electron开发桌面端应用，请参考这个项目。

## 对应的视频教程

此项目对应的视频教程（超清），包括所有PPT，请点这里：http://damoqiongqiu.github.io/videos/index.html

## 用法

用git克隆本项目，从命令行进入进入项目根目录，依次执行以下命令：

	npm i -g cnpm --registry=https://registry.npm.taobao.org
	cnpm i -g @angular/cli
	cnpm install
	ng serve

如果之前装过angular-cli需要先卸载：npm uninstall -g angular-cli
如果之前装过@angular/cli需要先卸载：npm uninstall -g @angular/cli
如果你之前已经尝试安装过node模块，请把NiceFish根目录下的node_moduels目录删掉
然后依次执行以下命令：

	npm cache clean
	npm prune
	npm i -g cnpm
	cnpm i -g @angular/cli
	cnpm install
	ng serve

打开你的浏览器，访问http://localhost:4200/

如果你想让加载的包更小，请使用以下方式启动angular-cli内置的轻量级http server

	ng serve --prod

如果你需要把项目发布到其它类型的Server上，例如Tomcat，需要对Server进行一些简单的配置才能支持HTML5下的PushState路由模式，我在这篇文章里面有详细的介绍https://my.oschina.net/mumu/blog/830696

【注意】如果你发现ng serve起不来，或者起来有报错，请把NiceFish根目录下的node_modules目录删掉，然后重新执行cnpm install，全局的@angular/cli也需要重装。

## 如何更新NiceFish的代码

打开命令行，进入NiceFish根目录，依次执行以下命令：

	git pull
	cnpm update
	ng serve

噢对，如果你pull代码之后发现起不来了，请把你项目下的node_modules全部删掉，然后重新cnpm update。这里确实有点坑，但是我也不知道为什么，目测是npm包的版本问题。

## AOT&TreeShaking

开发状态打出来的bundle体积比较大，在发布到生产环境之前需要进行prod和AOT，用法如下：

打开命令行，进入NiceFish根目录，执行以下命令：
	
	ng build --prod

加上--prod参数之后，angular-cli会自动启用TreeShaking（摇树）特性，简而言之，就是把用不到的包全部剔除掉，就像从树上把枯叶子摇下来一样，很形象吧？

angular-cli会在项目根目录下生成一个dist目录，里面就是编译、压缩好的文件了。仔细观察你会发现，这些文件的体积已经被大幅度压缩，加上gzip之后有一些文件只剩下1/4左右的大小。

关于Tomcat如何启动gzip，我专门写了一篇文章来介绍配置，请点这里：https://my.oschina.net/mumu/blog/830742

【请注意】最新版本的@angular/cli已经内置了对AOT和TreeShaking的支持，只要像上面这样在build的时候加上--prod参数就可以了，不需要再做任何其它任何配置工作，中文网站上的那一篇指南过时了。

## 推荐项目

- 目前最完善的Angular组件库PrimeNG，共有81个组件，十几套皮肤，能全面覆盖你的日常开发需求：https://www.primefaces.org/primeng/#/

- 一个非常好的后台管理模板项目ng2-admin: https://github.com/akveo/ng2-admin

- ng2整合各种插件的项目-Code Be：https://git.oschina.net/zt_zhong/CodeBe

- awesome-angular: https://github.com/AngularClass/awesome-angular 几百个开源项目和组件列表

- 医院挂号系统，基于Ionic3：https://github.com/stewchicken/hospital-booking

## 在线交流QQ群

    Angular-1区-丝绸之路:286047042（满） 

    Angular-2区-敦煌:139357161（满） 

    Angular-3区-玉门关:473129930（满） 

    Angular-4区-河西走廊:483016484（满） 

   
Angular-5区-楼兰:483016484（满）
 

   将本娃娃-桃花岛-83163037（将满） 

如果您有Angular相关的问题需要讨论，或者单纯想跟我Say Hello，请加上面几个扣扣群。注意，我每天都会收到大量的求助消息，真的有点忙，所以请您优先在扣扣群里面讨论问题。

## 关于我

我是大漠穷秋，我的Github个人主页在这里：http://damoqiongqiu.github.io/ 。

如果您觉得看视频教程不过瘾，想要找我去现场讲，请联系我的微信scriptbaby。当然，现场版的演讲会比线上内容更详细，而且可以带着大家实际上手写一些代码。

注意，微信号只谈公事，不聊天儿，也不答技术问题。不要腆着个脸把那些很二的问题随便甩过来，有一个网站叫百度，你知道的！

## 开源许可证
 MIT

 你可以随意使用此项目，无需通知我，因为我可能很忙没空搭理你。



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e899279667cc9a4b6f493eba03d915a40cb745a15b2c784ae0998a42a5df1ac74fe716d89d6162d8ac5fd14978f32ec87)