
# WeChatExt
WeChatExt是一个基于微信PC hook的项目，可实现微信PC端个人号接口、微信机器人等功能。

注入Dll参考[pcWeChat](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304652d578c86629c260d64d4909bfaab7cf3422809377a34eb9910e8d21325c3a33)项目，使用C++开发，控制端使用WPF开发。

其中C++和C#的通信采用WebSocket方式通信，当前控制端也可以使用其他语言开发，只需要实现一个WebScoket服务即可。

# 开发环境以及类库依赖
## 一、开发环境
WeChatPC：2.8.0.112

语言环境：C++、C#

开发工具：VS2019

分析工具：Cheat Engine 7.0、Ollydbg

## 二、依赖库
1、C++标准库：[Boost 17.2.0](http://u.720life.cn/g/c066f2a4cf26e6788a89c6b5375ffb6910c3140eec8d406e062af6af94984db9)

2、WebSocket Client:[WebSocketpp](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046369a2fa7152907e172f86febee2fa4dbd44b23956c60675a86277a5879d76d50)

3、WebSocket Server:[Fleck](http://u.720life.cn/g/54145d0471d91890860f7f8463c030463132826137dd6bf51f9b86d36e5b2f12eb35bc8e0e4890c39937c4dd1f910d75)

4、Hook功能实现：[pcWeChat](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304652d578c86629c260d64d4909bfaab7cf3422809377a34eb9910e8d21325c3a33)

5、EVString：[EVlib](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e1b11b6f638f32713d592c889749904379fdfbb74fe37c4e712f810e9000900cf)
##### 说明
非常感谢[codeByDog](http://u.720life.cn/g/54145d0471d91890860f7f8463c030469896d5aa589a59cbc13cdb551f562768)开源的此项目，让我能够接触到逆向相关的知识。

# 功能列表
1、获取登录二维码

2、获取登录信息

3、获取联系列表

4、获取数据库句柄

5、获取聊天信息

6、发送文本消息

7、发送图片消息

8、发送文件消息

9、发送群@消息

10、发送名片消息

11、发送链接消息

12、添加好友

13、删除好友

14、无痕清粉

15、获取群成员

16、设置群名称

17、设置群公告

18、添加群成员

19、删除群群成员

20、退出群

# 声明

本项目仅供技术研究，请勿用于任何商业用途，请勿用于非法用途，如有任何人凭此做何非法事情，均于作者无关，特此声明。



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e98e11eb766502276107212167be0489118bf019cb197715f4d844cca67c6795e9a205c6ab93bd88629de89b2fdae8bde)