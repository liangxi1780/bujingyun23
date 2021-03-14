## 服务器推荐配置
| 名称        | CPU    |  内存  |  硬盘  |  价格  |
| --------    | -----:   | :----: | :----: | :----: |
| 服务器(标准型S2机型 5M 双机)       | 2核      |   8G    |   50G    |   2970元/三年    |
| MySQL高可用版| 1核      |   1G    |   100G    | 423元/三年    |

| COS资源包     | 大小     |  价格     |
| --------     | -----:   | :----:   |
| 标准型存储容量 |200GB	  |1年	171元|
| 下行流量      | 500GB	  |3个月	177元|

[抢购地址：https://cloud.tencent.com](http://u.720life.cn/g/573ff6a91b3af551e410311df33cdee585ae679e117d1a2e2de8b5fd9b4b7c1e9c252d9e1af07c3fe29a52ff2471d7f552119a99ade11e0b3f8212c5524fde1db0628c42de396d2748e023ea26038d1c664b0e21f7f2bdcb133f789251321f4be014876d28eb93b25964727872e8445d)

# 使用须知
## ✅允许
- 个人学习使用
- 允许用于学习、毕设等
- 允许进行商业使用，但是要保留 footer 水印，请自觉遵守使用协议，别给公司带来不必要麻烦，如需要商业使用推荐购买商业版

### 微同商城商业版
![](https://platform-wxmall.oss-cn-beijing.aliyuncs.com/grocery/20181228/1114545734c867.jpg "微同商城商业版")

[商业版与开源版差异](http://u.720life.cn/g/f130445ddb374f9463a59e8398269a243445e3cbe511b3666931c48ce01a37b4)

## ❌禁止
- 将本项目的代码和资源进行任何形式的出售
- 利用本项目的代码和资源进行任何商业行为
- 擅自窃用，即属严重侵权行为，与盗窃无异。产生的一切任何后果责任由侵权者自负

## 🙏呼吁
- 维护国内开源环境，人人有责！

# 微信小程序商城（Java版）

## 获得荣誉
### GVP
![](
https://platform-wxmall.oss-cn-beijing.aliyuncs.com/GVP.jpg "GVP")

## 官方首页
* [演示地址](http://u.720life.cn/g/f130445ddb374f9463a59e8398269a2499cb2fd10e936e1c808f58c8b82e78c0)
* [最新开发文档](http://u.720life.cn/g/f130445ddb374f9463a59e8398269a248034ac615ab65175a4750ee189e5bfea)

## 新手必看启动教程
- [https://www.bilibili.com/video/av66149752](http://u.720life.cn/g/0b2e9c050c16e17e2de17da38fe221e14e891e7f464d808a8bfeaa8b64b73a97585ad497962756e7ecf19643061ada3c)

### 微同商城开源版体验：
![](https://platform-wxmall.oss-cn-beijing.aliyuncs.com/gh_a7a467438863_344.jpg "微同商城开源版")

* 官方QQ群：      
* git：[https://gitee.com/fuyang_lipengjun/platform](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6eb67f87deb73d9764a28ca1f183bbfdadaf2b2f011dd27ee826e754244639938a)
* 代码生成工具IDEA插件
    * git：[https://gitee.com/fuyang_lipengjun/platform-gen](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6eb67f87deb73d9764a28ca1f183bbfdadde9f16a1a6a4204cc9d2ba4cd68ef6c7)
    
# 注意
Entity里不是缺少get、set方法，Eclipse、IDEA请先安装lombok插件
 
## 技术选型
* 1 后端使用技术
    * 1.1 springframework4.3.7.RELEASE
    * 1.2 mybatis3.1.0、MyBatis-Plus 3.1.0
    * 1.3 shiro1.3.2
    * 1.4 servlet3.1.0
    * 1.5 druid1.0.28
    * 1.6 slf4j1.7.19
    * 1.7 fastjson1.2.30
    * 1.8 poi3.15
    * 1.9 velocity1.7
    * 1.10 quartz2.2.3
    * 1.11 mysql5.1.39
    * 1.12 swagger2.4
    * 1.13 j2cache2.3.22-release
    * 1.14 weixin-java-mp3.2.0
    * 1.15 MybatisPlus3.1.0
    * 1.16 lombok
        
* 2 前端使用技术
    * 2.1 Vue2.5.1
    * 2.2 iview
    * 2.3 layer3.0.3
    * 2.4 jquery2.2.4
    * 2.5 bootstrap3.3.7
    * 2.6 jqgrid5.1.1
    * 2.7 ztree3.5.26
    * 2.8 froala_editor1.2.2

## 项目结构
~~~
platform-wechat-mall
|--platform-admin 后台管理
|--platform-api 微信小程序商城api接口
|--platform-common 公共模块
|--platform-framework 系统WEB合并，请打包发布此项目
|--platform-gen 代码生成
|--platform-mp 微信公众号模块
|--platform-schedule 定时任务
|--platform-shop 商城后台管理
|--uni-color-ui uni-mall商城参考项目
|--uni-mall 移动端商城
|--wx-mall 微信小程序商城
~~~

## 实现功能

* 一：会员管理
    * a 会员管理
    * b 会员等级
    * c 收货地址管理
    * d 会员优惠劵
    * e 会员收藏
    * f 会员足迹
    * g 搜索历史
    * h 购物车

* 二：商城配置
    * a 区域配置
    * b 商品属性种类
    * c 品牌制造商
    * d 商品规格
    * e 订单管理
    * f 商品类型
    * g 渠道管理
    * h 商品问答
    * i 反馈
    * j 关键词

* 三：商品编辑
    * a 所有商品
    * b 用户评论
    * c 产品设置
    * d 商品规格
    * e 商品回收站

* 四：推广管理
    * a 广告列表
    * b 广告位置
    * c 优惠劵管理
    * d 专题管理
    * e 专题分类

* 五：订单管理
    * a 所有订单管理

* 六：系统管理
    * a 管理员列表
    * b 角色管理
    * c 菜单管理
    * d SQL监控
    * e 定时任务
    * f 参数管理
    * g 代码生成器
    * h 系统日志
    * i 文件上传
    * j 通用字典表
        
* 六：短信服务平台  
    * **需要短信验证码、短信通知、短信营销的客户进群私聊我**
    * a 配置短信平台账户信息
    * b 向外提供发送短信接口：
    ```
    http://域名:端口/api/sendSms?mobile=13000000000,15209831990&content=发送的短信内容  
    安全起见，需配置有效IP地址。platform.properties -> sms.validIp
    ```

## 安装教程

* 配置环境（推荐jdk1.8、maven3.3、tomcat8、mysql5.7、redis4.0.1）
* 创建数据库
* 依次初始化sql脚本 
    * /_sql/platform.sql
    * /_sql/sys_region.sql
* 导入项目到IDE中
* 导入支付证书至/platform-shop/src/main/resources/cert/目录下（申请商户号、开通微信支付、下载支付证书）
* 修改配置文件 /platform-admin/src/main/resources/dev/platform.properties
    * jdbc.url
    * jdbc.username
    * jdbc.password
    * wx.appId
    * wx.secret
    * wx.mchId
    * wx.paySignKey
    * wx.notifyUrl
    * sms.validIp
    * mp.appId
    * mp.secret
    * mp.token
    * mp.aesKey
* 修改配置文件 /platform-admin/src/main/resources/j2cache.properties
    * redis.hosts
    * redis.password
* 启动后台项目（参照 开发文档 ）
* 打开微信开发者工具
* 导入 /wx-mall填写appId
* 修改 /wx-mall/config/api.js里API_BASE_URL的值
* 使用eclipse启动项目后默认访问路径
    * [http://localhost:8080/platform-framework](http://u.720life.cn/g/e71094f6077cb9592da5b56893f0ad14d023f9f6a153df3d07ea8bd6914d8551586b563887fd521ee10492a50617275c)
* 使用idea启动项目后默认访问路径
    * [http://localhost:8080](http://u.720life.cn/g/e71094f6077cb9592da5b56893f0ad140b42b73eea3c0cdc72b4d749f85d5d96)

## 生产环境打包
    platform-wechat-mall>mvn package -P prod

***
### 关注微信公众号，第一时间获取项目最新动向，即将推出视频教程
![](https://platform-wxmall.oss-cn-beijing.aliyuncs.com/upload/20180708/qr.jpg "微信公众号")

## 页面展示
### 登录页面
![](https://platform-wxmall.oss-cn-beijing.aliyuncs.com/upload/20180708/login.png "登录")
### 首页
![](https://platform-wxmall.oss-cn-beijing.aliyuncs.com/upload/20180708/index.png "首页")
### 发送短信
![](https://platform-wxmall.oss-cn-beijing.aliyuncs.com/upload/20180727/3.png "发送短信")
### 捐赠
![](https://platform-wxmall.oss-cn-beijing.aliyuncs.com/upload/20180727/4.png "捐赠")
### 小程序首页
![](https://platform-wxmall.oss-cn-beijing.aliyuncs.com/upload/20180727/5.png "小程序首页")
### 专题
![](https://platform-wxmall.oss-cn-beijing.aliyuncs.com/upload/20180727/6.png "专题")
### 分类
![](https://platform-wxmall.oss-cn-beijing.aliyuncs.com/upload/20180727/7.png "分类")
### 购物车
![](https://platform-wxmall.oss-cn-beijing.aliyuncs.com/upload/20180727/8.png "购物车")
### 登录授权
![](https://platform-wxmall.oss-cn-beijing.aliyuncs.com/upload/20180727/9.png "登录授权")
### 优惠券
![](https://platform-wxmall.oss-cn-beijing.aliyuncs.com/upload/20180727/10.png "优惠券")
### 小程序并联手机
![](https://platform-wxmall.oss-cn-beijing.aliyuncs.com/upload/20180727/11.png "并联手机")
### VUE页面
![](https://platform-wxmall.oss-cn-beijing.aliyuncs.com/upload/20180727/12.png "VUE页面")

***

###  开发文档目录 
![](https://platform-wxmall.oss-cn-beijing.aliyuncs.com/catalog.png "开发文档目录")



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e849f59cd57ad9fc22b967aab4189ae710e79e0bc7daa2436f2e07d87f44469b7f7b095e5b367add2fc9c64a462ebc113)