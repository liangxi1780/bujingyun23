[![Software license][ico-license]](LICENSE)
[![Latest development][ico-version-dev]][link-packagist]
[![Monthly installs][ico-downloads-monthly]][link-downloads]

-----

## 提醒：微信CA证书进行了更新，请更新项目到最新版本。否则5月29日后，将无法支付
> 官方公告： https://pay.weixin.qq.com/index.php/public/cms/content_detail?lang=zh&id=56602

## 你们需要干什么：
- 当前如果使用的4.x版本，请更新到: **4.1.7**
- 当前如果使用的x.x版本，请更新到: **3.1.5**


## 相关文档
- [Payment使用文档](http://u.720life.cn/g/16a1b6a40e00f8a96c7e7830f39caedabe77ec39eaffa80779d1d00bb91b64f17b8ba313293e473656578fe58be67ccbbf93e14d6836328cecf715e92f910ce7)
- [Payment使用常见问题汇总](http://u.720life.cn/g/16a1b6a40e00f8a96c7e7830f39caedabe77ec39eaffa80779d1d00bb91b64f17b8ba313293e473656578fe58be67ccb321a6ea2ae5c0da67e3d74cb6c16553f)


----

Payment 需要 PHP &gt;= 5.6以上的版本，并且同时需要PHP安装以下扩展

```
- ext-curl

- ext-mbstring

- ext-bcmath

- package-Guzzle
```
guzzle 是一个开源的php http请求lib，[项目地址](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046d3da72a2adefed3b2458008a900a4694)

# Payment是什么？

Payment是一个集成了 **支付宝支付**、**微信支付**、**招商支付**的PHP SDK。服务端开发者将它集成到自己的项目中，可以方便的通过相同的操作方式进行各项支付操作。不再需要开发者去单独了解支付宝、微信、招商的接口文档。以发起支付举例，开发者只需要通过：

```
try {
    $str = Charge::run(支付类型, 配置文件, 支付数据);
} catch (PayException $e) {
    echo $e->errorMessage();
    exit;
}
```

就可以得到支付结果返回数据。关心的核心只需要正确了解如何组装**支付数据**，以及如何正确处理返回后的数据即可。

Payment支持所有的PHP项目，只要求PHP版本大于等于5.6即可。同时支持composer与手动引入两种安装方式。

# 当前支持的接口

当前sdk仅接入了支付宝支付、微信支付、招商支付（支付、退款）。中国现在电子支付的公司巨多，无法一一接入，欢迎各位发扬自己动手、丰衣足食的光荣传统，提交**PR**给我，代码贡献指南 [看这里](CONTRIBUTING.md)

## 支付宝接口

* **APP支付**（接入支付宝SDK，用户支付时唤起支付宝完成支付）
* **手机网站支付**（移动端唤起支付宝钱包或网页收银台完成支付）
* **电脑网站支付**（用户通过支付宝完成支付，交易款项即时到账）-原即时到账
* **当面付**（商户扫码首款或用户扫码付款）
* **单笔转账到支付宝**（支付宝商户向其它支付宝账户单笔转账）
* **交易支付、转账、退款查询接口**
* **交易退款接口**
* 对账单下载（待开发）
* 交易结算接口（待开发）
* 交易关闭接口（待开发）

## 微信支付接口

* **刷卡支付**（用户打开微信钱包的刷卡界面，商户扫码后提交完成交易）
* **公众号支付**（用户在微信内进入商家的H5页面，页面内调用JSSDK完成支付）
* **扫码支付**（用户打开扫一扫，扫码商户二维码完成支付）
* **APP支付**（商户APP中集成微信SDK，用户点击后跳转到微信完成支付）
* **H5支付**（用户在微信以外的浏览器请求微信支付的场景唤起微信支付）
* **小程序支付**（用户在微信小程序中使用微信支付）
* **企业付款**（企业向用户付款）
* **交易支付、转账、退款查询接口**
* **交易退款接口**
* 对账单下载（待开发）
* 现金红包（待开发）
* 代金券或立减优惠券（待开发）

## 招商支付

* **用户签约**（首次使用招商支付的用户完成绑卡操作）
* **招商一网通支付**（发起支付请求，招商支付仅此一个接口）
* **交易退款**
* **查询招商公钥**
* **交易支付、退款查询**
* 查询入账明细（待开发）
* 查询协议（待开发）
* 取消协议（待开发）

## 安装

通过composer，这是推荐的方式，可以使用composer.json 声明依赖，或者直接运行下面的命令。

```php
    composer require "riverslei/payment:*"
```

放入composer.json文件中

```php
    "require": {
        "riverslei/payment": "*"
    }
```

然后运行

```
composer update
```
----

# 联系&打赏 #

感谢朋友们的支持：[支持名单](SUPPORT.md)

 
       
     个人公众号： dayuTalk  
     联系邮箱：dayugog@gmail.com 
     GitHub： https://github.com/helei112g  
       
      我写我的，你赏你的  
 

# Contribution #
[Contribution Guide](CONTRIBUTING.md)

# License #

The code for Payment is distributed under the terms of the MIT license (see [LICENSE](LICENSE)).


[ico-license]: https://img.shields.io/github/license/helei112g/payment.svg
[ico-version-dev]: https://img.shields.io/packagist/vpre/riverslei/payment.svg
[ico-downloads-monthly]: https://img.shields.io/packagist/dm/riverslei/payment.svg?style=flat-square

[link-packagist]: https://packagist.org/packages/riverslei/payment
[link-downloads]: https://packagist.org/packages/riverslei/payment/stats



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e8893ffd537a2a16b77556207ef63f81c58b3f641be7c82b8edece830967a2b3be9f90b28e6977a2c5bf799e0c6de7e41)