与Discuz模板引擎有着相同的语法标签，仅仅是更换为用PHP扩展实现。

PHP调用模板引擎方法：

$view_obj = new ext_view();

$view_obj->setTemplateDir("./template/");//设置模板所在路径

$view_obj->setCompileDir("./complie/");//设置模板解析后的缓存路径

$view_obj->setOpenCache(1);//开发环境请设置0，禁用缓存

$view_obj->assign('title', 'Test is a test!');

$data = array(
    'key'   =>  'key1',
    'key2'  =>  'key2'
);

$view_obj->assigns($data);

$view_obj->display('index');

模板中使用方法：

一、引用变量

{$title}

二、引用数组

{$arr['key']}

三、包含其他模板文件

{template /path/header}

{template ./header}

四、IF条件

{if $true}

{elseif $second_true}

{else}

{/if}

五、foreach循环

{loop $each $item}

{/loop}

{loop $each $idx $item}

{/loop}

四、可以在模板中直接使用PHP标签

 


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6eb7c0036fe201a43c45c8f2a6eaccae3fa83e370776967d29b4099c6d4e6ef7d69ce4aeb2a74a60f8229ee6d27a95b0d8c5381253867cc474a400ee2b75a9063a)