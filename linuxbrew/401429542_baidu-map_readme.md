  🗺️ baidu-map  

 可能是我用过的最好用的百度地图 SDK 了 

[![Build Status](https://travis-ci.org/her-cat/baidu-map.svg?branch=master)](https://travis-ci.org/her-cat/baidu-map) 
[![StyleCI build status](https://github.styleci.io/repos/200389077/shield)](https://github.styleci.io/repos/200389077)

## 环境要求

- PHP >= 5.6
- [Composer](http://u.720life.cn/g/d5f1cf35647bbcd870aa9cc0452a2958e2335b0b7c0efe9734806c0884dd1bac)
- fileinfo 拓展（获取静态图需要用到）

## 安装

```shell
$ composer require "her-cat/baidu-map" -vvv
```

## 单元测试

```shell
$ composer test
```

## 使用

```php
  'your ak',
//    'sk' => 'your sk',
    'log' => [
        'file' => './baidu-map.log'
    ],
    'response_type' => 'array',
];

$webApi = Factory::webApi($config);

$result = $webApi->timezone->get('116.30815', '40.056878');

//    Array
//    (
//        [status] => 0
//        [timezone_id] => Asia/Shanghai
//        [dst_offset] => 0
//        [raw_offset] => 28800
//    )
```

## 文档

[详细文档](http://u.720life.cn/g/3e30c6ddf1da731f690e3aef3483b5b0c4f800189668c1f6544befa33564f2a8)

## Features

- [ ] [LBS云](http://u.720life.cn/g/63a232df0842fe23005681c996a4860b02a1117a341a000bdae64fd4b65ccb362528b6aaa09b700b86d809601a602e0e)
- [x] [Web服务API](http://u.720life.cn/g/63a232df0842fe23005681c996a4860b02a1117a341a000bdae64fd4b65ccb360ea0aa8b5397ea2a974f4913c165cfdd)
- [ ] [鹰眼轨迹服务](http://u.720life.cn/g/63a232df0842fe23005681c996a4860b02a1117a341a000bdae64fd4b65ccb36d8308c00dc8adb851cb028b1ded19dea)

## 参考

- [overtrue/wechat](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046a9ad670262ec3ac29fecbf1849b17fcbcd4ebd1a4f1c3f1cdfa72b6d8dc07ee5)
- [PHP 扩展包实战教程 - 从入门到发布](http://u.720life.cn/g/9908dc68064c12f79245d328edea428f9a87b958e86a2b207010c087cb2b5cb7e5b7a79d87171b26de2be24542b712e9)

## License

MIT



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6eac4e2f111e18cd6ca90e96a78de6fc61e78c45a70d6b022fc2afcf4ac041c78f2f46e53c8d756f66d26b7633078e3557)