##goxiang
* game server by golang
* jkkkls@163.com

###架构说明
* 架构分为三部分，客户端，网关，游戏区服务器，以及其他逻辑服务器（例如pvp服务器）
* 消息头为14个字节；id，消息源或者目标id，4byte；seq，消息序列号，2byte；ret，消息返回结果，2byte；cmd，消息命令字，2byte；len，消息体长度，2byte，理论上不要超过65535字节. 消息加密密钥暂时写死。实际使用时可以使用其他方式生成加解密密钥
* 配置是直接读取xlsx文件，保存为二维map，详情参考common目录的GxDict目录
* 数据库使用redis保存重要数据和热数据，mysql保存冷数据
* 提供管理后台接口

###项目说明
* Gate - 网关服务器，用于转发客户端与游戏服务器之间的消息，验证玩家数据，负载均衡，广播，数据统计
* Login - 登陆服务器，玩家通过登陆服务器获取token，再使用token与Gate登陆，并提供第三方登陆和充值功能
* Center - 游戏区服务器，提供每个区服的逻辑
* Fight - 跨服战服务器
* Public - 公用服务器，提供充值等功能
* Client - 客户端测试程序
* Stress - 压力测试
* Tool - 工具集合，创建新服，创建数据库表等工具

###编译说明
1. go get git.oschina.net/jkkkls/goxiang
2. cd goxiang
3. build.sh



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e13e8af857d92f7d5275ec48372ca72b1039264b5049ac76c51b67802057c1ba53884eb871b5d7465b8b35ac10db5169b)