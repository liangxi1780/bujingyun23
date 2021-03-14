## 镜像下载

腾讯云分流下载地址： [DOWNLOAD](http://u.720life.cn/g/4e10b06b2e2244ac9967f98c7b2141687def5f17d77b9ba348f39a2d11ccc9182964d8dfd52f9d8f7264a785e7ab6a6087016264887c11be815abc8ea14d09154d0886a876094430930485769f3ae586)

## TUIKit集成

 
   
     功能模块 
     平台 
     文档链接 
   

   
​     快速集成 
​     iOS 
​      TUIKit-iOS快速集成  
   

   
​     Android 
​      TUIKit-Android快速集成  
   

   
​     快速搭建 
​     iOS 
​      TUIKit-iOS快速搭建  
   

   
​     Android 
​      TUIKit-Android快速搭建  
   

   
​     修改界面样式 
​     iOS 
​      TUIKit-iOS修改界面样式  

   

   
​     Android 
​      TUIKit-Android修改界面样式  
   

   
​     自定义消息 
​     iOS 
​      TUIKit-iOS自定义消息  
   

   
​     Android 
​      TUIKit-Android自定义消息  
   

 


## 接口升级

- [iOS v2 v3 v4](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046cac459156a38c74fb481a0e54d9dc424a891029a0e7e730f132db91ff275cdfe8b7a66f7796891f5590ffb8c5a5ba86d0892d72ece81ecf57c2f5dea62a85e50aeffc6f7c1255290b18b5d517b0e62056a9a639a75aea221b24720bc5db113437bbb78fde61a2b67970198c5cabe2191)
- [Android v2 v3 v4](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046cac459156a38c74fb481a0e54d9dc4241c5c2db90aaee4fd8ec279961eac52929baea541954659d9107904dfe7bef814f62f1579d8a8f0020deec1033b8b4b9da1f98569e411231828e91b739555598beb16f9fed98c109793379c96a21e560c1d53c5b570f8b59927bc67353832ee74)
- [Windows v2 v4](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046cac459156a38c74fb481a0e54d9dc42454ad248a0224e0a6e2085bb45d7e57b278d6b3a3d0831dde47240cadf7f87358ed3bdbe7c0814daf6b831814ef3679a8fa41f6a042a415217983e98c28d1a38709c5efeeecab819e6c1069c4e1c934e484bc4b0f0c5b8e4891473a019c497e64)

## 问题反馈
- 为了更好的了解您使用TIMSDK所遇到的问题，方便快速有效定位解决TIMSDK问题，希望您按如下反馈指引反馈issue，方便我们尽快解决您的问题
- [TIMSDK issue反馈指引](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046cac459156a38c74fb481a0e54d9dc4245ece7ef58a2c4bbd69353f41b7352fb9775eee0b09f82422276afa7c870acc3ff0006413f9afb7a0fe500cd4d9db692aef37e14751fd78450e2752fa10b1724e68dc10e77cc415050a25f22b03ae7073)

## 4.8.50 @2020.06.22

### SDK

**通用变更点**

- 修复 API 2.0 接口有人进入直播群（AVChatRoom）后没有回调 onMemberEnter 问题
- API 2.0 接口的 onGroupInfoChanged 和 onMemberInfoChanged 回调增加 groupID 参数
- 修复 C2C 消息发送成功后没有回调会话更新的问题
- 修复切换帐号加入同一个直播群（AVChatRoom）后收不到消息的问题
- 修复偶现登录后同步未读消息回调顺序不对的问题
- 增加信令接口
- 直播群（AVChatRoom）增加群自定义属性接口
- 修复已知崩溃问题

**Android 平台**

- 为兼容 android Q 版本，修改日志默认存储位置为 /sdcard/Android/data/包名/files/log/tencent/imsdk

**Windows 平台**

- 修复建群时群成员角色问题

### TUIKit & Demo

**iOS**

- tuikit 替换 api 2.0接口
- 结合 TRTC 实现了音视频通话功能
- 增加了深色模式

**Android**
- tuikit 替换 api 2.0接口
- 结合 TRTC 实现了音视频通话功能
- 支持 AndroidX


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ec5aaf6123841f1eb7362430539d1ff42cece0a5c44aba082c6d1345afc17cc44c768c88a3009c1bd2470dc14cbaa4b2d)