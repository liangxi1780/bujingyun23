# DUXCMS 2.1
[![LICENSE](https://img.shields.io/badge/license-Anti%20996-blue.svg)](https://github.com/996icu/996.ICU/blob/master/LICENSE)
[![Build Status](https://travis-ci.org/xiaodit/duxcms-2.1.svg?branch=master)](https://travis-ci.org/xiaodit/duxcms-2.1)
[![Release](https://img.shields.io/github/v/release/xiaodit/duxcms-2.1.svg?style=flat)](https://github.com/xiaodit/duxcms-2.1/releases/latest)
[![Scrutinizer Code Quality](https://scrutinizer-ci.com/g/xiaodit/duxcms-2.1/badges/quality-score.png?b=master)](https://scrutinizer-ci.com/g/xiaodit/duxcms-2.1/?branch=master)
[![HitCount](http://hits.dwyl.io/{username}/xiaodit/duxcms-21.svg)](http://hits.dwyl.io/{username}/xiaodit/duxcms-21)

[最新版本](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046d3cf0513b86d7c9c6e6134c25e1b776671e4a8e02f3b8156580cba805545b219fe50af67e9d6e194e889317bca2a4a58)

默认没有前台模板的，请下载[官方仓库](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e4a9e32b86ab90e186a79ef141906d45094bdbe0159c9d4166bcc56f75e7c605421f106676b6abe689195f16b17469c7a)模板文件进行开发  

没安装Composer？ 请在最新版本链接下找`DuxCMS_Full.zip`下载

* `DuxCMS_Full.zip` 含composer包的完整程序 建议首次下载
* `DuxCMS-update.zip` 提供给在线更新的增量更新包

**此项目只是方便自己平时做私单项目顺便共享给其它人用， 不会频繁地添加新功能**

## 特征
* 支持php 5.6+ 7.4-
* [支持多语言](#多语言)
* [添加常用判断标签](#标签)
* [提供更稳定的分词服务](#分词功能)
* [提供文章推送百度收录](#百度推送)
* [提供更好的异常接管（Whoops）](http://u.720life.cn/g/8428c54a615a10bbf1f082879d49f7e511e515ac9f681a8fb6033300f7d467815dd6cbcb6f0f06798bcfa406a1118931)
* [提供多条件筛选](#多条件筛选)
* [提供在线更新服务(增量更新)](#在线更新) 🚀
* 提供网站地图生成
* [提供api接口调用](#api-调用)

## 安装
* mysqli扩展必须安装
* pdo扩展可选安装
```sh
$ composer install
```

## 预览
[线上预览](http://u.720life.cn/g/7f70da87553afd6a11af80e3fb66f631681cfa75b87f129c1e0bdf81d7f17ac8)  
感谢 👉[foxhost](http://u.720life.cn/g/8e973567eb4fed83acc959d0cf8fd126efd2592cfc03815a36ee21db3ff3ec87f41fdb1e5726950efef67d1d94d193e1)👈提供免费服务器支持

## 数据库驱动
* mysqli
* pdo

## 参考模板
[GITEE](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e4a9e32b86ab90e186a79ef141906d45094bdbe0159c9d4166bcc56f75e7c605421f106676b6abe689195f16b17469c7a)  
[开发文档](http://u.720life.cn/g/251b87a01595c66786e97402b49737e5615cefe692db3bfddaedbde9ee8c5bb3)

## 多语言

### 添加语种
[在此文件](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046d3cf0513b86d7c9c6e6134c25e1b7766c2ddad28ba76c6daa8d1dd735d4635fdd23549c0ecd7c354b4a9d3eff154c2d9cbd0a1c164d6055662c61c47cf2f3ac8)添加其它语种

### 开启语言
1. 后台设置->多语言设置->开启
2. 选择默认语言

### 切换语言
#### 前台切换
```php
// 切换英文
http://www.domain.com/en-us

// 切换中文
http://www.domain.com/zh-cn
```
#### 前台获取语言配置
模板调用 `$lang_list` 获取列表

```php
 
```

具体用法
```html
 
 $vo}-->
    {$vo.label}  
 
 
```

## 百度推送
* 模板使用 ` `
* 后台实时提交 系统设置->百度链接提交->开启


## 小功能
### 栏目页
* 添加分类文章统计（支持频道、列表） `$categoryInfo['article_count']`

## 助手函数
* `hasSub($cid)` 是否有下级分类
* `articleSumByCid(int $cid, $positionId = '', $isShow = true)` 获取分类文章统计
* `isOdd($index)` 是否为奇数 例子 ` 单数  偶数 `

## 标签
| 标签 | 说明| 参数 | 例子
| ----|----|----|----
| empty | 数组为空时| name | `{empty name="$list"}{/empty}`
| noempty | 数组不为空时 | name | `{noempty name="$list"}{/noempty}`
| defined | 常量已定义时 | name | `{defined name="APP_NAME"}{/defined}`
| nodefined | 常量未定义时 | name | `{nodefined name="APP_NAME"}{/nodefined}`
| isset | 变量定义时 | name | `{isset name="$test"}{/isset}`
| noset | 变量未定义时 | name | `{noset name="$test"}{/noset}`
| between | 变量存在某个区间时 | name, value | `{between name="$test" value="1,2"}{/between}`
| nobetween | 变量不存在某个区间时 | name, value | `{nobetween name="$test" value="1,2"}{/nobetween}`
| in | 变量存在数组时 | name, value | `{in name="$test" value="1,2"}{/in}`
| noin | 变量不存在数组时 | name, value | `{noin name="$test" value="1,2"}{/noin}`
| page | 单页信息| class 分类id, id 调用的变量名 | `{page class="$class_id" id="page"}{$page.content}{/page}`
| progress | 获取文章阅读进度 | container, parent, child, class | [详细说明](#文章阅读进度)

### 文章阅读进度
参数
* `container` 包着文章内容的根 （id, class） 例如 .back-to-top
* `parent` 包着百分比的根（id, class） 例如 .back-to-top
* `child` 包着百分比的标签 例如 span
* `class` 当页面浏览到文章内容内，加的类名 例如 on
```
   
    文章内容
   
  {progress container=".g-bd" parent=".back-to-top" child="span" class="on"}
     
        
     
  {/progress}
```
## 分词功能
由于http://keyword.discuz.com 出现403(应该关服务了)

使用[@梁斌penny](http://u.720life.cn/g/7233e45c492e5f3d09dc161393e23f001af0fc5c12d16f42a73f92a53235c947)的分词服务, 使用此项目的'模板工'们，你们应该感谢梁厂长！

## 多条件筛选

### 后台
1. 后台创建扩展模型 
2. 添加【下拉菜单】类型的字段， 【字段配置】用逗号分隔 例如创建一个码数的字段 字段配置：m,xl,xxl

### 前台
`$duowei`数组  
`$v['selected']`当前属性是否已选择  
`$v['url']` 当前属性的url 相当于 使用当前属性进行筛选  
`$v['durl']` 当前属性的url 相当于 不使用当前属性进行筛选  
```
 
   
     
       {$vo.name} 
      {noempty name="$vo['child']"}
       
         
           
             
              {$v.name}
             
           

           
             
              {$v.name}
             
           
          
       
      {/noempty}
     
   
    
```

## 伪静态 规则
* 列表页 `urlname` 栏目URL
* 列表详情页 `class_urlname` 上级分类栏目URL `urltitle` 当前页URL
* 单页面 `urlname` 当前页URL  

|名称 | 规则 | 对应类| 例子|
|----|----|----|----|
|列表页|` `|`article/Category/index`|`' /index.html' => 'article/Category/index'`
|列表详情页|` ` ` `|`article/Content/index`|`' / .html' => 'article/Content/index'`
|单页面|` `|`page/Category/index`|`'page/ .html' => 'page/Category/index'`

## api 调用

GET `/api.php`

**注意区分大小写**  

| 参数 | 说明(参数范围)| 是否必传 | 
| ----|----|----|
| signature |  签名 | 是 |
| timestamp |  时间戳 | 是 |
| nonce | 随机字符串| 是 |
| app |  ['DuxCms', 'Article']| 是 |
| label | ['contentList', 'categoryList', 'tagsList'] | 是 |
| ... | 其它查询参数，与普通模板标签一样 | 否 |

签名生成参考
```
$params = [
  time(),   // timestamp 参数值
  rand(1, 99999),   // nonce 参数值
  'DuxCms', // app 参数值
  'categoryList' // label 参数值
];
sort($params, SORT_STRING);
$tmpStr = implode( $params );
$sign = sha1( $tmpStr );
```

## 在线更新
为了不影响已有的文件，作了增量更新包。  
更新服务默认下载releases的Duxcms-update.zip压缩包，进行程序升级。  
[更新服务](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046d3cf0513b86d7c9c6e6134c25e1b7766ffcdc6fdc1ae6ca011321357820ef295)  
[检测地址](http://u.720life.cn/g/bb9e19de933fd87f05600116164183c0b3ddd62d3854e3432c88c12f9e59c662f1b5ca3b769773bd22db366804c312e9cfd8c21ef0cddc1773f48759707a5ebc936359677d6560950448d53eda4d814d)





 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ef129717bcf0a54e9d92815c9cd6a421144a68de8db0f96d3f3a36b4a8acc2a51c18ff2c12d41349bc5babe2e3528050d)