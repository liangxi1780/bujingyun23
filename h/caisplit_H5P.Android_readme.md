# Android平台5+App/uni-app运行环境开源项目

**重要：请使用HBuilderX2.3.6-20191020生成本地打包App资源，否则uni-app项目可能提示“运行环境版本和编译器版本不一致”，详情参考[https://ask.dcloud.net.cn/article/35627](http://u.720life.cn/g/09e6d6b5dd3d7091e3f3f255e4f37c2000817b11caff78f705968127e2b3809bf836194e9b9f3de6d44854634cd4f8e8 

## 说明
此次更新梳理了工程结构，现在开发者可以直接修改引擎中的代码，自主编译出新的引擎。

如果开发者要修改本工程源码，请注意“引擎”和“插件”的分界线。
“引擎”是对5+/uni-app规范的实现，修改引擎源码可以优化对规范的实现，但不是提供规范外的功能。规范外的功能，应该做成“插件”。如需公开，则放到[插件市场]https://ext.dcloud.net.cn/)。
比如扫码，5+/uni-app的规范已经存在，但开发者对扫码效率不满意，提供自己更好的实现，则可以改动本源码，重新Build引擎。
而如果是想新增一个ar功能，则应该做成插件，而不是加入到本工程中。即，开发者不能自主新增5+/uni-app的js API规范。

任何一个项目的源码，吃透整体都不是一件容易的事情。一般开发者有改动需求，也多集中在一些能力或SDK的实现上。
比如扫码、视频、地图、直播、摄像头、相册、蓝牙等，以及某些界面的文字。
只关注某些能力模块，吃透和修改会更加容易。

受精力所限，某些模块，比如DCloud定制过的weex源码，还未规整好，暂时以库的方式提供，未来会提供完整源码。不过这不影响开发者修改其他源码和编译工程。

## 模块与源码对应关系
| 功能模块                  | 源码目录                  | 5+APP项目                | uni-app项目              |
| :-------                | :-------                | :-------                | :-------                |
| Audio(音频)              | feature/audio             | [plus.audio](http://u.720life.cn/g/890b2d82eaa6a4198db0fe8fc66339fe2155c0e791d7790ce5d0699acd19791030daa4d8c1afba946ae8b9881bbfcb14)     | https://uniapp.dcloud.io/api/media/record-manager https://uniapp.dcloud.io/api/media/audio-context |
| Audio(MP3格式音频支持库)  | feature/audio-mp3acc      | [plus.audio](http://u.720life.cn/g/890b2d82eaa6a4198db0fe8fc66339fe2155c0e791d7790ce5d0699acd19791030daa4d8c1afba946ae8b9881bbfcb14)     |  |
| Barcode(二维码)          | feature/barcode           | [plus.barcode](http://u.720life.cn/g/890b2d82eaa6a4198db0fe8fc66339fe2155c0e791d7790ce5d0699acd1979101adc02e8cc171a6325e51480b6b1e502)  | https://uniapp.dcloud.io/api/system/barcode |
| Bluetooth(低功耗蓝牙)     | feature/bluetooth        | [plus.bluetooth](http://u.720life.cn/g/890b2d82eaa6a4198db0fe8fc66339fe2155c0e791d7790ce5d0699acd1979104a7d76a0c9344aeb186561652027736d3fb1810cce1d02642dddb30d287da11e)  | https://uniapp.dcloud.io/api/system/bluetooth |
| Camera(摄像头)            | feature/camera           | [plus.camera](http://u.720life.cn/g/890b2d82eaa6a4198db0fe8fc66339fe2155c0e791d7790ce5d0699acd1979101f75984bcd5328aede8406274a0db8e2)      |  |
| Contacts(通讯录)          | feature/contacts         | [plus.contacts](http://u.720life.cn/g/890b2d82eaa6a4198db0fe8fc66339fe2155c0e791d7790ce5d0699acd197910e370356c01f622763daadc543e6f72c886ccb0b9f506b242234669f33670ae34)  |  |
| Device(设备信息)          | feature/device           | [plus.device](http://u.720life.cn/g/890b2d82eaa6a4198db0fe8fc66339fe2155c0e791d7790ce5d0699acd197910014df441902e276039acbb7ba41ac0cb)    | https://uniapp.dcloud.io/api/system/info |
| Downloader(文件下载)      | feature/downloader       | [plus.downloader](http://u.720life.cn/g/890b2d82eaa6a4198db0fe8fc66339fe2155c0e791d7790ce5d0699acd19791092a71f696615ea68a98f6d06eb7c42d6b5102760c5968818bfb20fa11676fe31)  | https://uniapp.dcloud.io/api/request/network-file?id=downloadfile |
| Fingerprint(指纹识别)     | feature/fingerprint      | [plus.fingerprint](http://u.720life.cn/g/890b2d82eaa6a4198db0fe8fc66339fe2155c0e791d7790ce5d0699acd197910402d4c1647c57c6aba64a6efa9134c4037bd16d3a5e548e156df8c9a4d5322a9)  | https://uniapp.dcloud.io/api/other/authentication |
| Geolocation(基础定位库)   | feature/geolacation      | [plus.geolocation](http://u.720life.cn/g/890b2d82eaa6a4198db0fe8fc66339fe2155c0e791d7790ce5d0699acd197910072c1d8a26667e656a4e6ce49bdc98f8eeddd2fac64b1eab782113c1260e3c09)  | https://uniapp.dcloud.io/api/location/location |
| Geolocation(高德定位)     | feature/geolacation-amap	| [plus.geolocation](http://u.720life.cn/g/890b2d82eaa6a4198db0fe8fc66339fe2155c0e791d7790ce5d0699acd197910072c1d8a26667e656a4e6ce49bdc98f8eeddd2fac64b1eab782113c1260e3c09)  | https://uniapp.dcloud.io/api/location/location |
| Geolocation(百度定位)     | feature/geolacation-baidu	| [plus.geolocation](http://u.720life.cn/g/890b2d82eaa6a4198db0fe8fc66339fe2155c0e791d7790ce5d0699acd197910072c1d8a26667e656a4e6ce49bdc98f8eeddd2fac64b1eab782113c1260e3c09)  | https://uniapp.dcloud.io/api/location/location |
| Geolocation(系统定位)     | feature/geolacation-system | [plus.geolocation](http://u.720life.cn/g/890b2d82eaa6a4198db0fe8fc66339fe2155c0e791d7790ce5d0699acd197910072c1d8a26667e656a4e6ce49bdc98f8eeddd2fac64b1eab782113c1260e3c09)  | https://uniapp.dcloud.io/api/location/location |
| iBeacon                  | feature/ibeacon            | [plus.ibeacon](http://u.720life.cn/g/890b2d82eaa6a4198db0fe8fc66339fe2155c0e791d7790ce5d0699acd197910d392a44c6a91204a051af3c539b82327)      | https://uniapp.dcloud.io/api/system/ibeacon |
| IO(文件系统)              | feature/file               | [plus.io](http://u.720life.cn/g/890b2d82eaa6a4198db0fe8fc66339fe2155c0e791d7790ce5d0699acd197910783b91fa10364c68b31f7e50bb12cb07)                | https://uniapp.dcloud.io/api/file/file |
| LivePusher(直播推流)      | feature/media-livepusher   | [plus.video.LivePusher](http://u.720life.cn/g/890b2d82eaa6a4198db0fe8fc66339fe2155c0e791d7790ce5d0699acd197910707af03649eb8ed8ab5eea0309f011b6c51f52f9114eff0a5beeb1af29d660e922696c3ce40ff7092fe80d3bfa282115)  | https://uniapp.dcloud.io/api/media/live-player-context |
| Maps(高德地图)            | feature/map-amap           | [plus.map](http://u.720life.cn/g/890b2d82eaa6a4198db0fe8fc66339fe2155c0e791d7790ce5d0699acd1979103263d9ec3be8e62a18c01e68fc1666a7)             | https://uniapp.dcloud.io/api/location/map |
| Maps(百度地图)            | feature/map-baidu          | [plus.map](http://u.720life.cn/g/890b2d82eaa6a4198db0fe8fc66339fe2155c0e791d7790ce5d0699acd1979103263d9ec3be8e62a18c01e68fc1666a7)             | https://uniapp.dcloud.io/api/location/map |
| Messaging(短彩邮件消息)    | feature/messaging          | [plus.messaging](http://u.720life.cn/g/890b2d82eaa6a4198db0fe8fc66339fe2155c0e791d7790ce5d0699acd19791019cde509763b05126f68cd4c5ecae4bd5769ff3d84bb24cd544b09d373fbbd37)  |
| Navigator(运行环境信息)    | feature/navigatorui        | [plus.navigator](http://u.720life.cn/g/890b2d82eaa6a4198db0fe8fc66339fe2155c0e791d7790ce5d0699acd197910e81e3936c403cb49928315d9e563cd1621d38abfd658b25c4a418e8159cc58db)  | https://uniapp.dcloud.io/api/system/info |
| Oauth(登录基础库)         | feature/oauth              | [plus.oauth](http://u.720life.cn/g/890b2d82eaa6a4198db0fe8fc66339fe2155c0e791d7790ce5d0699acd197910efe04937f7f0dd8c39bcbc6c5e55ddb3)         | https://uniapp.dcloud.io/api/plugins/login |
| Oauth(小米登录)           | feature/oauth-miui         | [plus.oauth](http://u.720life.cn/g/890b2d82eaa6a4198db0fe8fc66339fe2155c0e791d7790ce5d0699acd197910efe04937f7f0dd8c39bcbc6c5e55ddb3)         | https://uniapp.dcloud.io/api/plugins/login |
| Oauth(QQ登录)             | feature/oauth-qq           | [plus.oauth](http://u.720life.cn/g/890b2d82eaa6a4198db0fe8fc66339fe2155c0e791d7790ce5d0699acd197910efe04937f7f0dd8c39bcbc6c5e55ddb3)         | https://uniapp.dcloud.io/api/plugins/login |
| Oauth(新浪微博登录)        | feature/oauth-sina         | [plus.oauth](http://u.720life.cn/g/890b2d82eaa6a4198db0fe8fc66339fe2155c0e791d7790ce5d0699acd197910efe04937f7f0dd8c39bcbc6c5e55ddb3)         | https://uniapp.dcloud.io/api/plugins/login |
| Oauth(微信登录)           | feature/oauth-weixin       | [plus.oauth](http://u.720life.cn/g/890b2d82eaa6a4198db0fe8fc66339fe2155c0e791d7790ce5d0699acd197910efe04937f7f0dd8c39bcbc6c5e55ddb3)          | https://uniapp.dcloud.io/api/plugins/login |
| Payment(支付基础库)       | feature/payment            | [plus.payment](http://u.720life.cn/g/890b2d82eaa6a4198db0fe8fc66339fe2155c0e791d7790ce5d0699acd197910dbe1294b3ab1052eaf4a05ed5683beeb)      | https://uniapp.dcloud.io/api/plugins/payment |
| Payment(支付宝支付)       | feature/payment-alipay     | [plus.payment](http://u.720life.cn/g/890b2d82eaa6a4198db0fe8fc66339fe2155c0e791d7790ce5d0699acd197910dbe1294b3ab1052eaf4a05ed5683beeb)      | https://uniapp.dcloud.io/api/plugins/payment |
| Payment(微信支付)         | feature/payment-weixin     | [plus.payment](http://u.720life.cn/g/890b2d82eaa6a4198db0fe8fc66339fe2155c0e791d7790ce5d0699acd197910dbe1294b3ab1052eaf4a05ed5683beeb)      | https://uniapp.dcloud.io/api/plugins/payment |
| Push(推送基础库)           | feature/aps               | [plus.push](http://u.720life.cn/g/890b2d82eaa6a4198db0fe8fc66339fe2155c0e791d7790ce5d0699acd1979100de02e24c4560fe99232da006b195eea)            | https://uniapp.dcloud.io/api/plugins/push |
| Push(个推推送)             | feature/aps-igexin        | [plus.push](http://u.720life.cn/g/890b2d82eaa6a4198db0fe8fc66339fe2155c0e791d7790ce5d0699acd1979100de02e24c4560fe99232da006b195eea)            | https://uniapp.dcloud.io/api/plugins/push |
| Push(个推推送-GooglePlay专版) | feature/aps-igexin-gp   | [plus.push](http://u.720life.cn/g/890b2d82eaa6a4198db0fe8fc66339fe2155c0e791d7790ce5d0699acd1979100de02e24c4560fe99232da006b195eea)            | https://uniapp.dcloud.io/api/plugins/push |
| Push(UniPush推送)            | feature/aps-unipush     | [plus.push](http://u.720life.cn/g/890b2d82eaa6a4198db0fe8fc66339fe2155c0e791d7790ce5d0699acd1979100de02e24c4560fe99232da006b195eea)            | https://uniapp.dcloud.io/api/plugins/push |
| Push(UniPush推送-GooglePlay专版) | feature/aps-unipush-gp | [plus.push](http://u.720life.cn/g/890b2d82eaa6a4198db0fe8fc66339fe2155c0e791d7790ce5d0699acd1979100de02e24c4560fe99232da006b195eea)         | https://uniapp.dcloud.io/api/plugins/push |
| Push(小米推送)             | feature/aps-xiaomi        | [plus.push](http://u.720life.cn/g/890b2d82eaa6a4198db0fe8fc66339fe2155c0e791d7790ce5d0699acd1979100de02e24c4560fe99232da006b195eea)            | https://uniapp.dcloud.io/api/plugins/push |
| Share(分享基础库)          | feature/share             | [plus.share](http://u.720life.cn/g/890b2d82eaa6a4198db0fe8fc66339fe2155c0e791d7790ce5d0699acd197910d5c9369483c9370c4a88755bd589c99b)           | https://uniapp.dcloud.io/api/plugins/share |
| Share(QQ分享)             | feature/share-qq           | [plus.share](http://u.720life.cn/g/890b2d82eaa6a4198db0fe8fc66339fe2155c0e791d7790ce5d0699acd197910d5c9369483c9370c4a88755bd589c99b)          | https://uniapp.dcloud.io/api/plugins/share |
| Share(新浪微博分享)        | feature/share-sina         | [plus.share](http://u.720life.cn/g/890b2d82eaa6a4198db0fe8fc66339fe2155c0e791d7790ce5d0699acd197910d5c9369483c9370c4a88755bd589c99b)          | https://uniapp.dcloud.io/api/plugins/share |
| Share(微信分享)            | feature/share-weixin      | [plus.share](http://u.720life.cn/g/890b2d82eaa6a4198db0fe8fc66339fe2155c0e791d7790ce5d0699acd197910d5c9369483c9370c4a88755bd589c99b)           | https://uniapp.dcloud.io/api/plugins/share |
| Speech(语音识别基础库)      | feature/speech            | [plus.speech](http://u.720life.cn/g/890b2d82eaa6a4198db0fe8fc66339fe2155c0e791d7790ce5d0699acd197910ba7d7da3a2983d6f0439f61c829b6574)         | https://uniapp.dcloud.io/api/plugins/voice |
| Speech(百度语音识别)        | feature/speech_baidu      | [plus.speech](http://u.720life.cn/g/890b2d82eaa6a4198db0fe8fc66339fe2155c0e791d7790ce5d0699acd197910ba7d7da3a2983d6f0439f61c829b6574)         | https://uniapp.dcloud.io/api/plugins/voice |
| Speech(讯飞语音识别)        | feature/speech_ifly       | [plus.speech](http://u.720life.cn/g/890b2d82eaa6a4198db0fe8fc66339fe2155c0e791d7790ce5d0699acd197910ba7d7da3a2983d6f0439f61c829b6574)         |
| SQLite(数据库)             | feature/sqlite             | [plus.sqlite](http://u.720life.cn/g/890b2d82eaa6a4198db0fe8fc66339fe2155c0e791d7790ce5d0699acd197910682c54f637b8456487af0790ca8bb12f)        |
| Statistic(友盟统计)        | feature/statistics-umeng   | [plus.statistic](http://u.720life.cn/g/890b2d82eaa6a4198db0fe8fc66339fe2155c0e791d7790ce5d0699acd197910a77c3113e6c0a03ba29d94c9140f689aab6b2f24d055af1013d59dd6f315109b)   |
| Uploader(文件上传)         | feature/uploader           | [plus.uploader](http://u.720life.cn/g/890b2d82eaa6a4198db0fe8fc66339fe2155c0e791d7790ce5d0699acd19791090b0772a9680e2962fd2676fe0d56cbe9dccb16c429284a19de755cb1c03fed4)     | https://uniapp.dcloud.io/api/request/network-file?id=uploadfile |
| VideoPlayer(视频播放)      | feature/media              | [plus.video.VideoPlayer](http://u.720life.cn/g/890b2d82eaa6a4198db0fe8fc66339fe2155c0e791d7790ce5d0699acd197910707af03649eb8ed8ab5eea0309f011b676448e837f6f00c568bff52dc53e1893c6a765582220afd8e5e2c1b3638daa73)  | https://uniapp.dcloud.io/api/media/video |
| XHR(网络请求)              | feature/xhr                | [plus.net](http://u.720life.cn/g/890b2d82eaa6a4198db0fe8fc66339fe2155c0e791d7790ce5d0699acd197910d62fd7e93500bb15ac9085f2bdc08aae)               | https://uniapp.dcloud.io/api/request/request?id=request |
| nvue原生组件: map(高德地图) | feature/weex_amap          | 不支持 | https://uniapp.dcloud.io/component/map |
| nvue原生组件: barcode(二维码) | feature/weex_barcode     | 不支持 | https://uniapp.dcloud.io/component/barcode |
| nvue原生组件: live-pusher(直播推流) | feature/weex_livepusher | 不支持 | https://uniapp.dcloud.io/component/live-pusher |
| nvue原生组件: video视频    | feature/weex_videoplayer    | 不支持 | https://uniapp.dcloud.io/component/video |
| nvue原生组件: canvas       | feature/weex_gcanvas        | 不支持 | https://github.com/dcloudio/NvueCanvasDemo |



## 源码配置

+ 文件夹中存在build.gradle文件的模块

将源码clone到本地，复制对应文件夹到所在项目的根目录，在setting.gradle中加入module配置，rebuild即可。以高德地图为例，将本工程clone到本地，复制map-amap到项目的根目录，打开setting.gradle，在最底部添加include "map-amap"，重新运行即可，如需添加到主工程中，打开主工程的build.gradle文件，在dependencies节点中添加implementation project(path: ':map-amap')即可。

+ 文件夹中不存在build.gradle文件的模块

如果模块中不存在build.gradle文件，可以将文件夹中的目录直接拷贝到主项目中。例如xhr模块，可以将src下的文件夹拷贝到主项目的src下，如果存在其他文件夹（如libs），直接将文件夹下的内容拷贝到同名文件夹下即可。


**参考HBuilder-SourceTool-as项目**

## 项目配置及打包

clone HBuilder-SourceTool-as项目到本地，直接运行即可。如果运行uni-app时出现问题，可参考：https://ask.dcloud.net.cn/article/35139。

安卓打包配置参考：https://www.cnblogs.com/lsdb/p/9337342.html。


# 许可协议
本工程大部分源码开源，使用者可以自主修改已公开的源码，编译新版本。
但注意：
1. 您不能破解、反向工程、反编译本项目下未开源的各种库文件。
2. 未经DCloud书面许可，您不得利用本项目的全部或部分源码、文件来制作与DCloud根据本项目提供的服务相竞争的产品，例如提供自主品牌的开发者服务。
3. DCloud所拥有的知识产权，包括但不限于商标、专利、著作权，并不发生转移或共享。
4. 您基于本项目，自主开发的代码及输出物，其知识产权归属您所有。除非您通过提交pull request的方式将自己的代码开源。
5. 如果您没有违反本许可协议，那么你使用本项目将无需为DCloud支付任何费用。



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)