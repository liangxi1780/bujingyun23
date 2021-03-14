# AnyRTC-RTMP
   
本次开源的客户端基于RTMP协议的推流拉流客户端，由我司CTO亲自操刀设计，采用跨平台架构一套代码支持Android、iOS、Windows等平台。 
直播涉及的流程：『音视频采集->编码->传输->解码->音视频渲染』本项目统统包含，这不是软文，这是实实在在的商业级实战代码；无论是你新手还是老司机，我们都热烈欢迎您前来筑码。

# 项目特点
**1，商业级开源代码，高效稳定** 
**2，超小内存占有率，移动直播针对性极致优化，代码冗余率极低** 
**3，打破平台壁垒，真正的跨平台，一套核心代码支持Android、iOS、Windows等** 
**4，超过200+Android手机、iOS全平台适配，硬件编解码可保证99%的可用性** 
**5，接口极简，推流：2个   拉流：2个** 
**6，底层库C++核心库代码风格采用：Google code style** 
**7，极简内核，无需再去深扒复杂的FFMpeg代码** 
**8，实用主义，那些什么坑什么优化等概念请搜索相关文章** 
**9，OpenH264软件编码，FFMpeg软件解码，FAAC/FAAD软件编解码，适配不同系统的硬件编解码统统包含** 
**10，支持SRS、Nginx-RTMP等标准RTMP服务；同时支持各大CDN厂商的接入** 

# 为什么开源？
本公司此次开源移动直播解决方案的根本目的：回馈开源社区，特别是SRS和WebRTC项目，大家也可以看到本次开源项目的框架使用了WebRTC，RTMP协议部分使用的是srs_librtmp；这两个开源项目可以说在流媒体领域给予了大家太多，所以适当的回馈是理所应当。

##编译环境
Android Studio、NDK 
XCode 
VS2015 

##支持的系统平台
Android 4.0及以上 
iOS 8.0及以上 
Windows 7及以上 

##支持的CPU架构
Android armv7 arm64 
iOS armv7 armv7s arm64 
Windows win32、x64 

##第三方库版本
libfaac		1.28 
libfaad2	2.7 
ffmpeg		3.0 
libyuv		newest 
openh264	1.6.0 

##技术交流
直播技术QQ群：554714720 
连麦技术QQ群：580477436(即将满员) 

##授权声明
本次开源在未授权情况下不可应用于任何的闭源商业项目，具体请参照GNU License中的声明。 
咨询QQ:2628840833  
联系电话:021-65650071 

##版权声明
若本开源项目涉及到其他软件的版权，请及时联系作者进行修正。 

##捐赠
本项目不接受任何形式的捐赠，您的支持就是最大的动力。 

## License
AnyRTC-RTMP is available under the GNU license. See the LICENSE file for more info.




 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e61b440f9e5ce3d9e4d40aef6b16e4bfc092f4e00a121d7eac8a18a40f6a208a23c270439b2b554570845b3c953aeacc2)