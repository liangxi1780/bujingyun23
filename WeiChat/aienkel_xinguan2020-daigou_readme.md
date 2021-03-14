# 社区代购

### 需求
社区、校园，因封闭管理，急需代购小程序。业主在小程序上下单，物业人员购买并交付给业主。

前端页面，从uni-app插件市场的主流电商模板中选择。

后端使用uniCloud开发。

使用场景如下：
1. 物业人员在系统中添加商品，系统预置一批日用品（如方便面、牙膏）
2. 业主在微信小程序上登陆（仅使用微信登陆，无需账户密码）、下单，付款。配送地址和电话，可以从微信API中读取。
3. 代购人员采购，买到后人工交付给业主，标记订单完成；买不到则退款给业主

参考样例：微信小程序搜索“佳乐达商城小程”

### 参与贡献的方式

1.  Fork 本仓库
2.  新建 Feat_xxx 分支
3.  提交代码
4.  新建 Pull Request


# 业务接口

### 一、用户端接口 (码云 unhejing负责)
 1. 用户登录鉴权，拦截器(@码云:yinbaoer负责 ) 接口：login，validateToken
 2. 商品列表 接口：get-product-list
  + 获取商品详情 接口：get-product-detail
 3. 购物车相关接口
  + 加入购物车 接口：add-cart
  + 更新购物车数量 接口 update-cart-num
  + 购物车列表 接口： get-cart-list
  + 删除购物车商品（多选删除）接口：delete-cart
 4. 订单相关接口
  + 订单列表 接口：get-order-list
  + 创建订单 接口：create-order
  + 修改订单状态（订单取消接口）接口：update-order-status
 5. 个人信息接口
  + 获取用户信息 接口：get-user-info
  + 修改用户信息 接口：update-user

### 二、管理端接口(@帐篷 908349383@qq.com负责)
 1. 管理员登录 接口：admin-login
 2. 获取订单列表（按状态查询，时间倒序）接口：同用户端订单接口
 3. 修改订单状态（订单完成）接口：同用户端修改订单接口
 4. 添加商品 接口：add-product
 5. 编辑商品 接口：update-product
 6. 修改商品上下架状态 接口：update-product-status
 7. 上传图片 接口：upload-file
 8. 修改管理员密码 接口：update-password
 9. 退出登录 接口：admin-logout


### 三、管理端页面原型还没确定(@码云：ITZTao 负责安排人). 
 1. 管理端业务描述
  *  商品管理：上架新商品、修改商品信息（含下架）
  *  订单管理：订单列表（未完成、已完成），未完成的订单，可以点击订单详情后操作订单完成、订单退款
  *  账户管理：修改密码、退出登陆





 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e445d3e9971364ce14b844bc1d983b5c4d53b92451ae36e1e30cd14ee1e0c4d5583ecf23b0802c8af4e05d83719566a582df507c7a14ece48e29ea0d7e273e1bd)