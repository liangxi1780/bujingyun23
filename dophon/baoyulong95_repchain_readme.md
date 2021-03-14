# RepChain
[RepChain文档](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6eb97b9ecefb73f19c28197fb59bd92fae0e70f139083b80d76804fd11c32e5bdc)   [单机多节点部署](http://u.720life.cn/g/df6a10df2dd476381be783e791aa2bade26c7b4d4d15a190034c130fcd99bc703cc7bd35027662c8cb82af1d2a50a29f47a88fb821344f20509d176260cd10d7c5475205ac9aefc459d2222e0900ee010f0638d640ea386043491c3f71c6cf625d7d27ac50d4ca0beceaefff1a08b8ca79092cdc8b9057e05d40fd7e2d7a806e2d4f945ff837c92b34e17f1cf14d4acd)   [多机多节点部署](http://u.720life.cn/g/df6a10df2dd476381be783e791aa2bade26c7b4d4d15a190034c130fcd99bc703cc7bd35027662c8cb82af1d2a50a29f47a88fb821344f20509d176260cd10d7c5475205ac9aefc459d2222e0900ee0166b08eae283914f798b15e7bee5f46b9275a39a51efd5880bcacc5ad842d0dca49be25dd1192108b0ef9def598b0a09802dbabfc4530be5616d87e9af403f6a8)

## 参考阅读
- [akka](http://u.720life.cn/g/19a302edd9b1090a7aa23348d86d0a8d) ——系统内部模块采用akka actor实现
- [akka remoting security](http://u.720life.cn/g/5c1739d7b03585fc8f8bb22efc5a9f28555825942a3b9850210bccec80e0a95135354de84401cc0f1d4f773fe5d8bbcf70304a4794bb3b902ea263fc57ae8624) ——节点之间安全通信采用akka Remote支持的TLS
- [akka serialization](http://u.720life.cn/g/5c1739d7b03585fc8f8bb22efc5a9f28555825942a3b9850210bccec80e0a95106e8eafb0b09de518fea63bec17ccafcad07e93e2786caca92a48e7ecc736de3)——节点之间消息交互采用protobuf序列化
- [scalaPB](http://u.720life.cn/g/d9846f7eb09dedc2f404786989f307729b08dfc2544d4d89917cc6a35aabe48d)——从proto定义生成Scala类的工具
- [protobufjs](http://u.720life.cn/g/54145d0471d91890860f7f8463c030465cd1e41cdd31b299bf01f9cf431e8d06e684e42b127f7b5c0eecd943783ddbe5)——在web端根据proto定义，反序列化protobuf字节流
- [swagger-scala](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046ee873d8b7265bda98dbeb1b913855dc8e6c9719908a55a1dab06ff20e951a30c1682139a37398cf6ff06a25b808b0ed1)——API支持Swagger UI
- [json4s](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046d69b70fa5e3263c3703500a93296768c)——在API层提供输入对象的json反序列化，返回结果的json序列化
- [d3.js-force layout](http://u.720life.cn/g/54145d0471d91890860f7f8463c030463d96b3d42b3125089de8377dd1f7dbc21024737f9d6b69a409d33fd63c3567b5922f3664a3d2a6680b7daea08590711e1469d82390f832b90818ace88a398885)——入／离网节点的自动布局
- [leveldb for java](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304669caa290d17fc4702902b3a24df7b6a2)——存取Blocks、Transactions索引
- [java security](http://u.720life.cn/g/93f16c577429ee5ee9d7562025a6bc747e39f32b07de0d874c0a10a1a6d32086c242e1245c001363b1771441ef63829f3700477044f6c6204c49f5e29a9debba2fab2e14d618bc4bd8f41be8758e4aca)——hash、签名、密钥对及证书管理均采用jdk内置方法

## 安装
- install [jdk8+](http://u.720life.cn/g/0832d3c13dcf440b8c2ddd37014597194dfce0f4546bd12c9ba469d981d9d729007ebfc8068b2baf5cdf0064d40d499907fcdb961ed5489f9d3009acbb39641a0931ff7ad6e1f2b0f260aebddd28593e379c733776164d165e258f441c53afb4)
- install [Python](http://u.720life.cn/g/dd2f6da1de73fd81cbeeed608e80e8779ac5ab940be4eecd4e601cd95d022670)
- install [Scala](http://u.720life.cn/g/ea08d14ebddcd426bb95926b3d6ff10a160cd15195afe55830f1d8d3c766b72b96101907bc3b46381435c95731e4d8ea)
- install [SBT](http://u.720life.cn/g/af86998b18536574a0a3fe9f3158d005aea961f3a7457f3e34873427af95fde0ce924d6f55a157509ff7b7e9c1fdac1c)
- install [Scala IDE](http://u.720life.cn/g/4e7f6c664266ddd790d885a4ceac026d9338ff9874282afc912c14bd13a7d177)
- install [keystore-explorer](http://u.720life.cn/g/df8a04d46dfee53e035acbe6fa9acc065ee15b6f1f98e033a1fb0947f941bce7) ——用于生成密钥对的工具,非必须
- install [protobuf editor](http://u.720life.cn/g/54145d0471d91890860f7f8463c030465be5c232fffc2df9ed921eb891490485b46c129c2fe09b261cde0fe24d5e8f1a)——编辑protobuf定义工具，非必须

## 运行
- `git clone https://gitee.com/BTAJL/repchain.git`
下载项目到本地
- `sbt` 
在项目的根目录下下载项目依赖项，可以配置仓库或者使用阿里镜像
- `compile` 
编译成Protocol Buffer Scala类
- `eclipse` 
生成eclipse工程文件
- 打开 Scala IDE, File->Import->Existing Projects,导入项目
- 右键单击 rep.app.Repchain.scala,Run As->Scala Application(单机组网4个节点)
- 运行配置VM参数 -Dlogback.configurationFile=conf/logback.xml (使logback配置生效)
- 查看实时图 http://localhost:8081/web/g1.html 
- 查看API  http://localhost:8081/swagger/index.html

## 修改配置
- 生成RepChain节点密钥对及信任证书列表（见[《RepChain开发者指南》](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6eb97b9ecefb73f19c28197fb59bd92fae92293f4bcfdc13b3665e88bafe2c1dce8aa3e43abccd33f2abb3b51919557643) 2.1.5）
- 制作创世区块（见[《RepChain开发者指南》](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6eb97b9ecefb73f19c28197fb59bd92fae92293f4bcfdc13b3665e88bafe2c1dce8aa3e43abccd33f2abb3b51919557643) 2.1.6）
- 调整系统配置参数（见[《RepChain开发者指南》](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6eb97b9ecefb73f19c28197fb59bd92fae92293f4bcfdc13b3665e88bafe2c1dce8aa3e43abccd33f2abb3b51919557643) 2.1.7）

## 打包
- assembly 
打包成jar包，进行分布式部署

## 论坛社区
- http://bbs.repchain.net.cn/ 



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e4edd885054fa85ed48543c001ac6ca06e0c3e96d2b09727a49c2843f4d81e9e157bd884241548f913a8840c20bd0ff87)