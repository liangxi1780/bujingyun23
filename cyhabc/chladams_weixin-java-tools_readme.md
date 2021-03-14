## WxJava（原weixin-java-tools）微信Java开发工具包（SDK）

[![码云Gitee](https://gitee.com/binary/weixin-java-tools/badge/star.svg?theme=blue)](https://gitee.com/binary/weixin-java-tools)
[![Github](http://github-svg-buttons.herokuapp.com/star.svg?user=Wechat-Group&repo=WxJava&style=flat&background=1081C1)](https://github.com/Wechat-Group/WxJava)
[![GitHub release](https://img.shields.io/github/release/Wechat-Group/WxJava.svg)](https://github.com/Wechat-Group/WxJava/releases)
[![Maven Central](https://img.shields.io/maven-central/v/com.github.binarywang/wx-java.svg)](http://mvnrepository.com/artifact/com.github.binarywang/wx-java)
[![Build Status](https://travis-ci.org/Wechat-Group/WxJava.svg?branch=develop)](https://travis-ci.org/Wechat-Group/WxJava)
[![使用IntelliJ IDEA开发维护](https://img.shields.io/badge/IntelliJ%20IDEA-提供支持-blue.svg)](https://www.jetbrains.com/?from=WxJava-weixin-java-tools)
[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)

---------------------------------
#### 支持包括微信支付、开放平台、公众号（包括订阅号和服务号）、企业微信/企业号、小程序等微信功能的后端开发。
---------------------------------

### 重要信息
1. **2018-12-23 项目更名为WxJava，并发布 [【3.3.0正式版】](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046201a511e2ba300ebaea50f02340949bc73fc847b519491abf898414417649c42)**！
1. 新手重要提示：本项目仅是一个SDK开发工具包，未提供Web实现，建议使用maven或gradle引用本项目即可使用本SDK提供的各种功能，详情可参考 **[【Demo项目】](demo.md)** 或本项目中的部分单元测试代码；另外微信开发新手请务必阅读[【开发文档 Wiki 首页】](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046201a511e2ba300ebaea50f02340949bc907a262f0228eff0d943a43710ca43f5)的常见问题部分，可以少走很多弯路，节省不少时间。

---------------------------------
### 技术交流方式
1. QQ群：（**注意：目前为付费群，刚入群会有5分钟禁言，稍等片刻即可正常发言**） [![加入QQ群](https://img.shields.io/badge/QQ群-343954419-blue.svg)](http://shang.qq.com/wpa/qunwpa?idkey=731dc3e7ea31ebe25376cc1a791445468612c63fd0e9e05399b088ec81fd9e15) 或 [![加入QQ群](https://img.shields.io/badge/QQ群-343954419-blue.svg)](http://jq.qq.com/?_wv=1027&k=40lRskK)，推荐点击按钮入群，当然如果无法成功操作，请自行搜索群号`343954419`进行添加；由于群容量有限，为了维持运营千人QQ群的所需支付的QQ年费会员费用，故开启付费入群模式，申请者只需支付少量金额即可加入，这样也可以保证只有真实交流需求的人进入，避免闲杂做广告人员的乱入；当然如果确实因为各种原因无法付费入群的，请联系群主说明原因即可入群；
1. 微信群： 请关注公众号后点击相关菜单入群；
1. 钉钉企业群：[请点击链接申请加入](http://u.720life.cn/g/817e59162edd059e3bf9e401f9ed47c5a54199b94e95c24eeeb1b0346a8c767bf309a4215a68d3dddc94b20727dc4c5bd9e17fa048c46a2eab3a4d53840c87c6781ea17e83667d56763693a3028751c6a8c3fe152ba924202ee8b358eb707ef2b1dc85dd8116cc48fb3c25955255ec2f) 或者 [用手机钉钉APP扫码](qrcodes/ding_qrcode.jpg) 申请加入。
1. 新手提问前，请先阅读[【提问的智慧】](http://u.720life.cn/g/f12d6675aaefe49442d321d10c0352d5e64ba1342598bd37f79daeed3e51f7895146f2c14a954bb6bc8f3f0d3606a0f35a4fefa428574c82be696ac52849ca15)，并确保已查阅过 [【开发文档Wiki】](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046baa7244917c0ef77762f29cdc461153c20dbeacc992383298ddc69d0da2b2df6)；
1. 寻求帮助时需贴代码或大长串异常信息的，请利用http://paste.ubuntu.com
1. **另外，想要得到更多开发交流讨论方式，请扫描以下二维码，关注微信公众号【WxJava】，或者加入企业微信，当然也可以在微信中搜索 `weixin-java-tools`或 `WxJava` 关注公众号，公众号会及时通知SDK相关更新信息，并不定期分享微信Java开发相关技术知识。**

![微信公众号及企业微信](qrcodes/cp_mp_qrcodes.png) 

--------------------------------
### 其他说明
1. 本项目Fork自chanjarster/weixin-java-tools，但由于原项目已停止维护，故单独维护和发布，且发布到maven上的groupId也会不同，详细信息见下文。
1. [开源中国本项目的首页](http://u.720life.cn/g/1dbc517b01e71dde51eaf55b6f5fa8331383ff1d692dd66194059598090f474af5dd99e990934e0a0f2cd1e73db3d41e)，欢迎大家积极留言评分 🙂
1. SDK详细开发文档请查阅 [【开发文档Wiki】](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046baa7244917c0ef77762f29cdc461153c20dbeacc992383298ddc69d0da2b2df6)，部分文档可能未能及时更新，如有发现，可以及时上报或者自行修改。
1. **阅读源码的同学请注意，本SDK为简化代码编译时加入了lombok支持，如果不了解lombok的话，请先学习下相关知识，比如可以阅读[此文章](http://u.720life.cn/g/408fb60b53d11d245635ad5e8e8cd697fae83842e2e75528f54314d215518c913fe08db285a0f217e685906cb1b6fab7e845894118225fb4d0419105b40f4417)；**
1. 如有新功能需求，发现BUG，或者由于微信官方接口调整导致的代码问题，可以直接在[【Issues】](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046201a511e2ba300ebaea50f02340949bcb16b4fe0b9f13efb5b6529286cd96c91)页提出issue，便于讨论追踪问题；
1. 如果想贡献代码，请阅读[【代码贡献指南】](contribution.md)；
1. **如果本SDK对您有所帮助，欢迎对我们的努力进行肯定，可以扫描[【支付宝付款码】](qrcodes/alipay_qrcode.jpg)或者[【微信支付二维码】](qrcodes/wepay_qrcode.jpg)进行打赏，或者直接前往[【托管于码云的项目首页】](http://u.720life.cn/g/e0d2c85055613e6181156334353bc3d91a4f823d2a59372774810b8732fa7e7474d67689a6152096fa5a3b7108bcb18b)，在评论区上方可以找到“捐助”按钮。非常感谢各位打赏和捐助的同学！**
1. 各个模块的Javadoc可以在线查看：[weixin-java-miniapp](http://u.720life.cn/g/3ef0aa548822b7c906d16665d94d2fa25cff21929e783c7f874f5536514b04fb42714f0ee4d076ffb4700fb38fadaa11)、[weixin-java-pay]http://binary.ac.cn/weixin-java-pay-javadoc/
1. 本SDK要求的最低JDK版本是1.7，还在使用JDK6的用户请参考[【此项目】]( https://github.com/binarywang/weixin-java-tools-for-jdk6) ，而其他更早的JDK版本则需要自己改造实现。
1. 本SDK项目在以下代码托管网站同步更新:
* 码云：https://gitee.com/binary/weixin-java-tools
* GitHub：https://github.com/wechat-group/WxJava

---------------------------------
### SDK使用方式
注意：最新版本（包括测试版）为 [![Maven Central](https://img.shields.io/maven-central/v/com.github.binarywang/wx-java.svg)](http://mvnrepository.com/artifact/com.github.binarywang/wx-java)，以下为最新正式版。

```xml
 
   com.github.binarywang 
   （不同模块参考下文） 
   3.3.0 
 
```
* 各模块的`artifactId`：
  - 微信小程序：`weixin-java-miniapp`   
  - 微信支付：`weixin-java-pay`
  - 微信开放平台：`weixin-java-open`   
  - 公众号（包括订阅号和服务号）：`weixin-java-mp`    
  - 企业号/企业微信：`weixin-java-cp`

---------------------------------
### 版本说明
1. 本项目定为大约每两个月发布一次正式版，版本号格式为X.X.0（如2.1.0，2.2.0等），遇到重大问题需修复会及时提交新版本，欢迎大家随时提交Pull Request；
1. BUG修复和新特性一般会先发布成小版本作为临时测试版本（如3.1.8.B，即尾号不为0，并添加B，以区别于正式版）；
1. 目前最新版本号为 [![Maven Central](https://img.shields.io/maven-central/v/com.github.binarywang/wx-java.svg)](http://mvnrepository.com/artifact/com.github.binarywang/wx-java) ，也可以通过访问链接 [【微信支付】](http://search.maven.org/#search%7Cgav%7C1%7Cg%3A%22com.github.binarywang%22%20AND%20a%3A%22weixin-java-pay%22) 、[【微信小程序】](http://search.maven.org/#search%7Cgav%7C1%7Cg%3A%22com.github.binarywang%22%20AND%20a%3A%22weixin-java-miniapp%22) 、[【公众号】](http://search.maven.org/#search%7Cgav%7C1%7Cg%3A%22com.github.binarywang%22%20AND%20a%3A%22weixin-java-mp%22) 、[【企业微信】](http://search.maven.org/#search%7Cgav%7C1%7Cg%3A%22com.github.binarywang%22%20AND%20a%3A%22weixin-java-cp%22)、[【开放平台】](http://search.maven.org/#search%7Cgav%7C1%7Cg%3A%22com.github.binarywang%22%20AND%20a%3A%22weixin-java-open%22)
分别查看所有最新的版本。 

----------------------------------
### 使用案例
1. 开源项目：https://github.com/workcheng/weiya
1. 开源项目：https://github.com/jmdhappy/xxpay-master 
1. 微信点餐系统开源项目：http://www.sqmax.top/springboot-project/
1. 小程序：[喵星人贴吧助手(扫码关注)](http://u.720life.cn/g/0b1e802cae4421653873ac634f70b143b501e2f0d853c8d1fcd305fce14dbaa13f3af199c5f1a3fe29f1865b2d558ed839449251ec54243a78ddcc440e5b55fa)
1. 小程序：树懒揽书+
1. 小程序：广廉快线，鹏城巴士等
1. 小程序：360考试宝典
1. 平台：[小猪餐餐](http://u.720life.cn/g/36ffb061987569450550171cebb4f2bd9983c969bae2f1bff5ac4ab108c4946f)
1. 平台：[餐饮系统](http://u.720life.cn/g/69bc678920091a4233a9bb77cd3373acdccbd05c5d5cb0477829c80b61b4fec1)
1. 公众号：中国电信上海网厅（sh_189）
1. 公众号：E答平台
1. 公众号：[全民约跑健身便利店](http://u.720life.cn/g/36b70055edaf2cd6f28877c4c8e426145bcee1c8a013a6c6a2fe62433a5adb8d)
1. 公众号：[洽洽食品](http://u.720life.cn/g/408fb60b53d11d245635ad5e8e8cd6978b4d2cb74e32e8c85e88931381eba4fdd2534c28269a07b1c21f567c79ea2d3b4ddd3f26a530e887bc48f6c9f7c839c8a7fccf02d78e5d62e56d672544ca26389b2b534ff268a4d992487c8135f490070a113536bc9300437aafb525c30ec9d9f20eb4d624ed1dcecf7fb3cd9fdbf1acc52724a31ffd1bac4df173ae5589d774c2e50def9f8e641e3201856136734489)、[洽洽合伙人]https://mp.weixin.qq.com/cgi-bin/showqrcode?ticket=gQFP8jwAAAAAAAAAAS5odHRwOi8vd2VpeGluLnFxLmNvbS9xLzAyOUpJaU5VcXBlWTAxMDAwME0wN1oAAgSau4RbAwQAAAAA
1. 公众号和小程序：民医台（可自行搜索）
1. 洽洽企业号
1. 高善人力资源
1. 其他更多案例请[【访问这里】](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046201a511e2ba300ebaea50f02340949bcca63bd4327b4be140b9c98ec0254b23ebab184dbdb8dc65854e62ebda5df6625)，持续更新中。

----------------------------------
### 贡献者列表
特别感谢以下参与贡献的所有同学！
1. [chanjarster (Daniel Qian)](http://u.720life.cn/g/f6754e90a70fcffec3c12b5e1e01b2d39dd8d452637e8e67b052f2b86c068e1e)
1. [binarywang (Binary Wang)](http://u.720life.cn/g/f6754e90a70fcffec3c12b5e1e01b2d315d264942efecc9b7f53d6b42d88f16e)
1. [mgcnrx11](http://u.720life.cn/g/f6754e90a70fcffec3c12b5e1e01b2d39eb9ef8f841598381d94b8fd31333ea0)
1. [007gzs](http://u.720life.cn/g/f6754e90a70fcffec3c12b5e1e01b2d33419949801adae43e030ee831aacb8dd)
1. [aimilin6688 (Jonk)](http://u.720life.cn/g/f6754e90a70fcffec3c12b5e1e01b2d3a86f43abf38374bb144a17dde9f61582)
1. [kakotor](http://u.720life.cn/g/f6754e90a70fcffec3c12b5e1e01b2d3940dd19e8fe7b2fd47722c64da0838b6)
1. [kareanyi (MillerLin)](http://u.720life.cn/g/f6754e90a70fcffec3c12b5e1e01b2d3f4ede29bd281cc6d9ec95a60846663a9)
1. [tianmu](http://u.720life.cn/g/f6754e90a70fcffec3c12b5e1e01b2d3ddd44c75425c588832c28c94d4d96f7a)
1. [rememberber (周波)](http://u.720life.cn/g/f6754e90a70fcffec3c12b5e1e01b2d31856bbca3c2fe758825c0bdf46e32550)
1. [charmingoh (Charming)](http://u.720life.cn/g/f6754e90a70fcffec3c12b5e1e01b2d33d7442be77753d49cf72bc453d850994)
1. [gaigeshen (gaigeshen)](http://u.720life.cn/g/f6754e90a70fcffec3c12b5e1e01b2d3eb67668796b8b71d4dc7a288bbd8b3d4)
1. [ukid](http://u.720life.cn/g/f6754e90a70fcffec3c12b5e1e01b2d3157568de7d20cf0e807c4b7143301eed)
1. [forfuns (爱因斯唐)](http://u.720life.cn/g/f6754e90a70fcffec3c12b5e1e01b2d310af76922f94d6dee490a1a084237592)
1. [yuanqixun (yuanqixun)](http://u.720life.cn/g/f6754e90a70fcffec3c12b5e1e01b2d304996613adf76d7eb4061656e9ff5f65)
1. [zxkane (Meng Xin Zhu)](http://u.720life.cn/g/f6754e90a70fcffec3c12b5e1e01b2d3798f5f3ba9865d9f5fcecabaa0faa6f4)
1. [crskyp (我是木予)](http://u.720life.cn/g/f6754e90a70fcffec3c12b5e1e01b2d39a6de64140488f671f5c9f641c7fcdd6)
1. [dylanleung (dylanleung)](http://u.720life.cn/g/f6754e90a70fcffec3c12b5e1e01b2d32f7387bc3587d57bf331201086de7a06)
1. [huansinho](http://u.720life.cn/g/f6754e90a70fcffec3c12b5e1e01b2d30160ce7da68bf44ab83eb4140910d069)
1. [codepiano (codepiano)](http://u.720life.cn/g/f6754e90a70fcffec3c12b5e1e01b2d339585abbdc293c62edf68f11949e9d7b)
1. [stvliu (Steven Liu)](http://u.720life.cn/g/f6754e90a70fcffec3c12b5e1e01b2d3d488346b455eb97b69efec809eec9ebe)
1. [unlimitedsola (Sola)](http://u.720life.cn/g/f6754e90a70fcffec3c12b5e1e01b2d3b161d5985d537a1bb56a75274213fdff)
1. [fxdfxq (fxdfxq)](http://u.720life.cn/g/f6754e90a70fcffec3c12b5e1e01b2d30e69fe36a0d2d39b1812ac2703bf2c5c)
1. [withinthefog (withinthefog)](http://u.720life.cn/g/f6754e90a70fcffec3c12b5e1e01b2d35a7c820988f4a787c810eb40ed8f5710)
1. [DDLeEHi](http://u.720life.cn/g/f6754e90a70fcffec3c12b5e1e01b2d3fa586b1ee92f6c2c6384ddf076f7bef3)
1. [nickwongwong (Nick Wong)](http://u.720life.cn/g/f6754e90a70fcffec3c12b5e1e01b2d33829b00ed6a242fc85cbbbd38c735146)
1. [jink2005 (Jink2005)](http://u.720life.cn/g/f6754e90a70fcffec3c12b5e1e01b2d3caffa4f8dc08cedbd3827da89e58adfd)
1. [ajffdnt](http://u.720life.cn/g/f6754e90a70fcffec3c12b5e1e01b2d3f40589d559639abed6174354be4d718e)
1. [iwareserictsai (Eric.Tsai)](http://u.720life.cn/g/f6754e90a70fcffec3c12b5e1e01b2d36325823c887ec6ff918d5ada9bddb8fa)
1. [SimonDolph (Simon Dolph)](http://u.720life.cn/g/f6754e90a70fcffec3c12b5e1e01b2d3baf960301c8be5a1d1515af799c57520)
1. [ZhaoxiongTan (xiong)](http://u.720life.cn/g/f6754e90a70fcffec3c12b5e1e01b2d3c4a1d43e8c2bed04d8465e83ccd27229)
1. [howardliu-cn (看山)](http://u.720life.cn/g/f6754e90a70fcffec3c12b5e1e01b2d3df550cae2c2192bd3a6f3e8895da935e)
1. [SunshineTech (SunshineTech Zhang)](http://u.720life.cn/g/f6754e90a70fcffec3c12b5e1e01b2d3e148803acf3ae1d6f13239c156ef1bdb)
1. [xusheng1987 (flying)](http://u.720life.cn/g/f6754e90a70fcffec3c12b5e1e01b2d3b403c32520cbd27f5fa75f6ff577d904)
1. [lwxian](http://u.720life.cn/g/f6754e90a70fcffec3c12b5e1e01b2d34a1deb0c2a6388eded2171dcb5508bb7)
1. [aliangsoft (阿亮软件)](http://u.720life.cn/g/f6754e90a70fcffec3c12b5e1e01b2d30ddb0ed300eb6fb87dafa45205f4865a)
1. [zhfish (zhfish)](http://u.720life.cn/g/f6754e90a70fcffec3c12b5e1e01b2d3bf089003628822c5336bf2c58b853b6f)
1. [dwandw (dwandw)](http://u.720life.cn/g/f6754e90a70fcffec3c12b5e1e01b2d3829ca5417949d9cd01b310306a7b47a7)
1. [alanchenup (alanchen)](http://u.720life.cn/g/f6754e90a70fcffec3c12b5e1e01b2d37caa027cb7f386972d4525b9015943b5)
1. [zexpp5 (Lance7in)](http://u.720life.cn/g/f6754e90a70fcffec3c12b5e1e01b2d3f0923177c8c97ecb304b717924eb5068)
1. [xiaohulu (huluwa)](http://u.720life.cn/g/f6754e90a70fcffec3c12b5e1e01b2d3120ddaaaed47d0715d86ffb87d443126)
1. [aalx (devina)](http://u.720life.cn/g/f6754e90a70fcffec3c12b5e1e01b2d30a35e09ede21326a3668b07e066b0d0f)
1. [rtsbtx (强哥)](http://u.720life.cn/g/f6754e90a70fcffec3c12b5e1e01b2d3cb834ed44457c187c985f797017f6353)
1. [dracupid (Jingchen Zhao)](http://u.720life.cn/g/f6754e90a70fcffec3c12b5e1e01b2d3fe281b7edf74e569ec65b8e7ffb23c6c)
1. [lijunkun1988](http://u.720life.cn/g/f6754e90a70fcffec3c12b5e1e01b2d3a2def54b7a8fa1a0cdff0918ea0e970d)
1. [lly835](http://u.720life.cn/g/f6754e90a70fcffec3c12b5e1e01b2d3f7a51f9bf1682e1c58cc2881d7dc1549)
1. [mog0202 (蘑菇0202)](http://u.720life.cn/g/f6754e90a70fcffec3c12b5e1e01b2d398a5eade1ad72aeff0e4d91100706ee5)
1. [bobbyguo (bobby_guo)](http://u.720life.cn/g/f6754e90a70fcffec3c12b5e1e01b2d3f541a0593fd51bf44f0709d6c492d7b2)
1. [huotaihe (白马度和)](http://u.720life.cn/g/f6754e90a70fcffec3c12b5e1e01b2d3af3e7aef2f616a0d33d920795f8546f4)
1. [axeon](http://u.720life.cn/g/f6754e90a70fcffec3c12b5e1e01b2d32878d74142ff1bd57c48ae57d8d70068)
1. [dxwts (xuewu)](http://u.720life.cn/g/f6754e90a70fcffec3c12b5e1e01b2d3d92d05c1230f11754df5b39b76c8f44c)
1. [Mkluas (Mklaus)](http://u.720life.cn/g/f6754e90a70fcffec3c12b5e1e01b2d35a296991437588b77395624fbb50af9a)
1. [CodeIdeal (康阳)](http://u.720life.cn/g/f6754e90a70fcffec3c12b5e1e01b2d38cee2e7429b85812d7113352b2eef9ce)
1. [leeis (IOMan)](http://u.720life.cn/g/f6754e90a70fcffec3c12b5e1e01b2d3dc73eff59a7e774db42ad8307324d7d5)
1. [lichenliang666 (李晨亮)](http://u.720life.cn/g/f6754e90a70fcffec3c12b5e1e01b2d3d6ec09c0f8bc7fd8a6808afff9c4cd3e)
1. [627535195](http://u.720life.cn/g/f6754e90a70fcffec3c12b5e1e01b2d3aa19c5af16d29bbfacf93bfc6e00a7ac)
1. [ztmark (Mark)](http://u.720life.cn/g/f6754e90a70fcffec3c12b5e1e01b2d34d1decd415c721772a0d4e366db321b1)
1. [gtyang](http://u.720life.cn/g/f6754e90a70fcffec3c12b5e1e01b2d3020a93e53431d9aba0b246b411dbecb0)
1. [scott-z (scott)](http://u.720life.cn/g/f6754e90a70fcffec3c12b5e1e01b2d3c27e968abc336f3a50ff0882c9a67443)
1. [borisbao (Boris)](http://u.720life.cn/g/f6754e90a70fcffec3c12b5e1e01b2d3ac5db5aae12492022983f0309cdef2b6)
1. [qsjia (QSJia)](http://u.720life.cn/g/f6754e90a70fcffec3c12b5e1e01b2d3b126dcd88d9d58efe91ec6c03be436e8)
1. [webcreazy (webcreazy)](http://u.720life.cn/g/f6754e90a70fcffec3c12b5e1e01b2d328e9b507011fbe6333541a6fe73f416a)
1. [TonyLuo (Tony)](http://u.720life.cn/g/f6754e90a70fcffec3c12b5e1e01b2d32cb55b3d0936eb7282ff613e98a3a913)
1. [cwivan (鱼丸Cwivan)](http://u.720life.cn/g/f6754e90a70fcffec3c12b5e1e01b2d3a38bd27e87585a22f4f258630dfb6f44)
1. [biggates (Xiaoyu Guo)](http://u.720life.cn/g/f6754e90a70fcffec3c12b5e1e01b2d38718f8f1cff5bc644e81145cd4a234e6)



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e054613c36b964faca007fd7f07b67d785d3a4cf8c90a6243e9fca94cabea02d0db8a5224db354eba5a7b8206d2e06870bb1a47049c19f3963e9dda41cad32539)