 yshop意象商城系统 


#### 项目简介
yshop基于当前流行技术组合的前后端分离商城系统： SpringBoot2+Jpa+MybatisPlus+SpringSecurity+jwt+redis+Vue的前后端分离的商城系统， 包含商城、拼团、砍价、商户管理、 秒杀、优惠券、积分、分销、会员等功能，更适合企业或个人二次开发；；

**开发文档**  【[查看文档](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6eb307128f9b2acfb6a9a1bc35842bae21cffe9a58b9e0ed4c04aaac4a4cef44f57477bcc7d68e3c0a55e996203d157fc3db12df43590c6a10cd2ff09af007569dd92a36d47207ab8201474b8826973939ea7e0e4b131487d098e3a62e39440421)】 

#### 体验地址

|     |   后台系统  |   前端(公众号)  |
|---  |--- | --- |
|   |  https://yshop.dayouqiantu.cn  |H5:https://h5.dayouqiantu.cn 测试号：hupeng/123456,也可以自行注册 |
|    |  后台体验账号/密码：admin/123456   |  公众号:![输入图片说明](https://images.gitee.com/uploads/images/2019/1116/060936_fd73496c_477893.jpeg "qrcode_for_gh_95df5a2881cc_258.jpg")   |


#### 项目源码

|     |  后台系统源码 |   后台系统前端源码  |
|---  |--- | --- |
|   码云  |  https://gitee.com/guchengwuyue/yshopmall  | https://gitee.com/guchengwuyue/yshopmall_qd |
|   github   |  https://github.com/guchengwuyue/yshopmall |https://github.com/guchengwuyue/yshopmall_qd  |

#### 开源版本与VIP版本说明

###  开源版
1.包括整个商城系统后台、数据库、api(只是简单的配置好模块);

2.本版本本身属于独立后台商城管理系统、可独立作为cms、商城等等后台使用;

3.可以个人、企业直接使用。

### VIP版
1.包括整个商城系统后台、数据库、API、H5;

2.本版本是演示的所有功能代码;

3.加入VIP、享有后续所有功能免费升级及其技术支持等。

4、VIP为终身，【[详情请查看](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6eb307128f9b2acfb6a9a1bc35842bae211caff5bf08f28987d29d1f4a528e9e77352011ec8b19813d2360dbf46e22faa8d4a326731514b79c3a3dc879176375ce93fd3c3ba3b4bdd5b41f8e40e3e63f11)】 

## 商城功能

* 一：商品模块：商品添加、规格设置，商品上下架等
* 二：订单模块：下单、购物车、支付，发货、收货、评价、退款等
* 三：营销模块：积分、优惠券、分销、砍价、拼团、秒杀(、到店核销等
* 四：微信模块：自定义菜单、自动回复、微信授权、图文管理、模板消息推送
* 五：配置模块：各种配置
* 六：用户模块：登陆、注册、会员卡等
* 七：其他等
       

####  已经完成功能
- 可以具体查看演示地址查看当前版本已经完成的功能，不再絮叨啦

#### 项目结构
项目采用分模块开发方式
- yshop-api       公众号(H5)API模块
- yshop-mp        微信相关模块
- yshop-common    公共模块
- yshop-system    后台模块
- yshop-logging   日志模块
- yshop-tools     第三方工具模块
- yshop-generator 代码生成模块
- yshop-shop      商城模块

#### 系统预览
 
     
           
           
     
     
           
           
     
     
           
           
     
        
            
            
     
 
 
     
           
           
     
     
           
           
     
     
           
           
     
 

## 技术选型
* 1 后端使用技术
    * 1.1 SpringBoot2
    * 1.2 mybatis、MyBatis-Plus
    * 1.3 SpringSecurity
    * 1.4 JPA
    * 1.5 Druid
    * 1.6 Slf4j
    * 1.7 Fastjson
    * 1.8 JWT
    * 1.9 Redis
    * 1.10 Quartz
    * 1.11 Mysql
    * 1.12 swagger
    * 1.13 WxJava
    * 1.14 Lombok
    * 1.15 Hutool
    * 1.16 Mapstruct
	* 1.17 Redisson
        
* 前端使用技术
    * 2.1 Vue 全家桶
    * 2.2 Element

#### 项目发布明细

- 1.0版本
- 1.1版本新增积分与优惠券抵扣
- 1.2版本分销功能已经发布
- 1.2.1增加了未付款订单取消功能库存销量退出、优惠券、积分功能，个人中心增加了积分流水
- 1.3版本新增拼团功能，已经发布
- 1.3.1版本手机端新增商户管理、后台新增统计
- 1.3.2新增后台微信相关及其支付配置，新增自动回复配置
- 1.3.3新增 后台微信图文发送功能，小程序配置，增加小程序授权等,修复一些bug等
- yshop1.4版本发布，更新如下：
  - 1.1、新增积分签到
  - 1.2、新增会员等级、任务等功能，新增会员价格等
  - 1.3、修复Redisson linux系统启动报错问题
  - 1.4、修复商户简单权限功能
  - 1.5、修复加入购物车覆盖问题
  - 1.6、修复拼团出现undefined
  - 1.7、会员后台新增余额调整
  - 1.8、修复新增配置数据有时候不成功问题等
- 1.4.1个人中心新增账单流水
- yshop1.4.2 发布更新如下：
   - 1.商品新增多图评价
   - 2.订单新增快递查询
- 1.4.3版本，后台图标更新,后台模块重新拆分,物流快递单独管理,导出最新sql
- 1.4.4版本，新增模板消息通知、H5端商家管理发货修改及其列表时间显示修复
- yshop1.5版本发布：
	- 1、新增秒杀功能
	- 2、手机端新增H5支付
	- 3、修复其他bug
- yshop1.6发布：
  - 1、新增砍价功能
  - 2、新增加锁功能
  - 3、修复其他bug
- yshop1.6.1发布：新增移动端浏览记录，下单增加简单ReentrantLock锁
- yshop1.6.2发布：修复用户昵称带有表情导致入库失败问题，修复下单订单金额为0不能支付的问题

	
#### 反馈交流
- QQ交流群：964166879
- 喜欢这个商城后台的小伙伴留下你的小星星啦,star,star哦！

####  特别鸣谢
- eladmin:https://github.com/elunez/eladmin
- mybaitsplus:https://github.com/baomidou/mybatis-plus
- hutool:https://github.com/looly/hutool
- wxjava:https://github.com/Wechat-Group/WxJava
- vue:https://github.com/vuejs/vue
- element:https://github.com/ElemeFE/element



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e2c549aa78325dfa8f9af98dd1be661fc06e240a29e436e789adb55e4af0d54d01ef64d8e3d54028e81337230080bdecc)