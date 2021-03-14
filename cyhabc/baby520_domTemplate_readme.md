# domTemplate.js
一个非侵入式、不会破坏原来静态页面结构、可被浏览器正确显示的、格式良好的前端HTML模板解析引擎。彻底实现前后端分离，让后端专注业务的处理。
####Demo http://parky18.github.io/demo/

##目录
* [概述](#概述)
* [用法](#用法)
* [model标签](#model标签)
* [刷新model标签](#刷新model标签)
* [属性标签](#属性标签)
* [其他属性标签](#其他属性标签)
* [html标签](#html标签)
* [删除标签](#删除标签)
* [if条件标签](#if条件标签)
* [unless条件标签](#unless条件标签)
* [switch条件标签](#switch条件标签)
* [each遍历标签](#each遍历标签)
* [自定义标签](#自定义标签)
* [字符串拼接运算](#字符串拼接运算)
* [其他算术运算](#其他算术运算)
* [自定义函数](#自定义函数)

概述
-----------
 这是一个非侵入式、不会破坏原来静态页面结构、可被浏览器正确显示的、格式良好的前端引擎。

传统MVC开发模式，V层使用服务器端渲染。美工设计好静态HTML文件，交给后端工程师，需要转换成 `Jsp`、`Freemarker`、`Velocity`等动态模板文件。这种模式有几个缺点

1、动态模板文件不能被浏览器解释、必须要运行在服务器中才能显示出效果  
2、动态效果和静态效果分别存在不同文件，美工和后端工程师需要分别维护各自页面文件，其中一方需要修改页面，都需要通知另一方进行修改  
3、页面数据不能分块加载、获取跨域数据比较麻烦  

domTemplate.js 模板引擎是通过在标签中添加自定义属性，实现动态模板功能，当没有引入domTemplate脚本， 则自定义标签属性不会被浏览器解析，不会破坏原有静态效果，当引入domTemplate脚本，模板引擎回去解析这些标签属性， 并加载数据进行动态渲染。 下图：对比服务器页面渲染和使用domTemplate前端引擎开发流程 

| 服务器端模板解析 | domTemplate.js前端解析 |
| ---- | ---- |
|![before](http://git.oschina.net/parki/domTemplate/raw/master/docs/images/before.jpg)|![after](http://git.oschina.net/parki/domTemplate/raw/master/docs/images/after.jpg)|
用法
-----------
导入`jquery.js`或者`zepto.js`和`domTemplate.min.js`
```javascript
$(function () {
 $.domTemplate.init(options,callback);//可以通过selector指定根节点，默认根节点是body,表示从body开始，渲染整个页面 
 }); 
 ```
 或者解析某一个html片段。
 ```javascript
  $('selector').domTemplate(options,callback);//渲染数据是通过h-model 自动去获取数据，也可以通过data指定全局数据 
  ```
  Options
--------

| Name 	| Type 	| Default | 	Description| 
--------- | -------- | -------- | --------| 
| selector |	selector |	body 	| 根节点选择器| 
| data |	json |	{} |	渲染数据| 
| prefix | 	string |	h- |	标签前缀| 
| escape |	boolean |	true 	| 是否转义| 
| $parentElement |	jquery或者zepto对象 |	$(selector) |	当前上下文渲染父元素| 
| $currentElement |	jquery或者zepto对象 |	$parentElement 	| 当前上下文渲染元素| 

  callback
--------
模板渲染成功回调函数,`callback(model)`,所有需要等页面渲染成为做的逻辑需要注册这个回调函数，例如用`jquery.lazyload.js`实现图片懒加载
model标签
-----------
模板引擎通过` `标签获取渲染数据,并把数据放到上下文`Context`中
方式1(把h-model取数据放在任意标签):
  ```html
   xxx1  
 /body>
  ```
 方式2(把h-model取数据放在任意标签,可以连续取多个Model数据):
  ```html
   
  xxx1  
   
   ```
 方式3(把h-model取数据放在任意标签,不同块数据相互不影响):
  ```html
   
  xxx1  
   
   
  xxx1  
   
   ```
方式4(h-model标签可以嵌套使用):
 ```html
   
   
   
  成语  出处:    
  拼音:    
  出处:    
  范例:    
   
  成语  
  出处:    
  拼音:    
  出处:    
  范例:    
   
   
   
   
 ```
方式5(可以定义一个全局函数对model数据进行干预):
 ```html
    
   
   
  成语 
   
   
   
 ```
 ```javascript
 function modelRender(modelName, res) { 
   console.info("model名称" + modelName); 
   console.info(res); 
   if(!res){//失败 
   return {error: '错误'}; 
   } 
   if (modelName == 'data') { //可以对model数据进行修改 
   res.newslist[0].chengyu = res.newslist[0].chengyu + '(修改)'; 
   return res; 
   } 
 } 
 ```
 
model标签作用域
只有model标签的子节点才能获得model数据，不同块model数据相互独立不影响，但是单个页面model名称还是建议不要相同

[model标签测试例子](http://u.720life.cn/g/dc52ae30a155547ad9718b3398501c677377055debecb6475ca6924dfdfd6bed948ded3df100f465d747cacf519b5bf2b2486293591746460b68e21924231dc3)  
[嵌套model测试例子](http://u.720life.cn/g/dc52ae30a155547ad9718b3398501c677377055debecb6475ca6924dfdfd6bed4526779abf49f6c845977fae43c87b41d6dfe3d31278d180ee0f541ad581845e)  
[自定义修改model数据例子](http://u.720life.cn/g/dc52ae30a155547ad9718b3398501c677377055debecb6475ca6924dfdfd6bed7c1b10fda15ca0513c42a6a5178ad08e08d6a4ec4f427e5fd3646173972ab340)  
model请求参数
--------

| Name 	| Type 	| Default | 	Description| 
|--------- | -------- | -------- | --------| 
|url 	|String |	|	发送请求的地址。|
|dataType |	String |	json |	json|
|data |	String 	|	 | 发送到服务器的数据。将自动转换为请求字符串格式。GET 请求中将附加在 URL 后|
|type |	String |	POST 	|请求方式 ("POST" 或 "GET")|

刷新model标签
-----------
可以通过`$.domTemplate.getModel([modelName])`方式获得对应对应`model`，然后调用`reload`方法，其所属页面块模板会自动刷新下
model方法
--------
|Name |	Type 	|Description|
|--------- | -------- | -------- | 
|setParamsData 	|object 	|设置URL请求参数，例如分页参数：{page: page}。|
|reload(options,callback) |	object 	刷新， |appendType=after：返回数据往原来的列表后面拼接；  appendType=before：返回数据往原来的列表前面拼接；   appendType=page：清除原来列表数据，添加返回数据； |

例子
```javascript
$.domTemplate.getModel('list1').setParamsData({page: page}).reload({appendType: 'page'}, function () { 
console.info("加载完成") ;
}); 
```

[刷新model例子1](http://u.720life.cn/g/dc52ae30a155547ad9718b3398501c677377055debecb6475ca6924dfdfd6bed651b0a59f598d4a551f36efd4ee89b42e4042383be8164816293c3ca3945dd80)
[刷新model例子2](http://u.720life.cn/g/dc52ae30a155547ad9718b3398501c677377055debecb6475ca6924dfdfd6bed651b0a59f598d4a551f36efd4ee89b4297d29dbf433b7f279c40fc1c7ee022eb)
[刷新model例子3](http://u.720life.cn/g/dc52ae30a155547ad9718b3398501c677377055debecb6475ca6924dfdfd6bed651b0a59f598d4a551f36efd4ee89b4223bdc0a888a15c19a27e85bb299a855a)

属性标签
-----------
可以把多个DOM标签用逗号分隔，解析后会把对应的标签属性替换
```html
model数据:  
 {src:'http://www.wed114.cn/jiehun/uploads/allimg/160426/39_160426110624_1.jpg',title:'测试标题'}  
模板:  
   
```
渲染结果
```html
   
```
[attr标签例子](http://u.720life.cn/g/dc52ae30a155547ad9718b3398501c677377055debecb6475ca6924dfdfd6bed7fd603f9564833a98328d35e994084cb)

其他属性标签
-----------
引擎除了支持`h-attr`这种方式：还支持以下替换标签写法

|属性 |	引擎标签|
|-----| -------- |
|text |	h-text|
|value |	h-val|
|href |	h-href|
|src |	h-src|
|src |	h-src|
|class |	h-class|
|style |	h-css|
|width |	h-width|
|height |	h-height|
|id |	h-id|
|title |	h-title|
|alt |	h-alt|

如果还需要支持其他标签属性，可以通过`$.domTemplate.registerSupportAttr(attrName)`进行添加。 

html标签
-----------

该标签解析结果会显示在对应标签的html位置
```html
 xxxxx 
```
渲染结果
```html
  个人介绍  
```

删除标签
-----------
`h-remove` 渲染时候会删除有这个标签标识的html

```html
   
  李小璐  
  动态页面需要删除这个节点  
   
```
渲染结果
```html
   
  李小璐  
   
```

if条件标签
-----------

```html
  
  xxx  
  其他内容  
   
```
渲染结果
```html
   
  其他内容  
   
```
 
unless条件标签
-----------

```html
   
  xxx  
  xxx  
   
```
渲染结果
```html
  
  用户ID不等于50  
   
```

switch条件标签
-----------

```html
  
   
   
   
   
```
渲染结果
```html
  
   
   
```
each遍历标签
-----------
`t:each`属性用于迭代循环，语法：`th:each="obj,iterStat:{objList}" `迭代对象可以是`Java.util.List,java.util.Map`,数组等;
`iterStat`称作状态变量，如果没有显示设置状态变量，会默 认给个“变量名+Stat"的状态变量。属性有：
`index`:当前迭代对象的`index`（从0开始计算）
`count`: 当前迭代对象的`index`(从1开始计算)
`size`:被迭代对象的大小
`current`:当前迭代变量
`even/odd`:布尔值，当前循环是否是偶数/奇数（从0开始计算）
`first`:布尔值，当前循环是否是第一个
`last`:布尔值，当前循环是否是最后一个 

```html
  遍历List例子  
   
  李小璐  
   

  遍历map例子  
   
  李小璐  
   

  遍历map例子2  
   
  李小璐  
   

  遍历数组例子  
   
  李小璐 > 
   

  遍历数组例子2  
   
  李小璐  
   
```
渲染结果详细看例子
[遍历list例子](http://u.720life.cn/g/dc52ae30a155547ad9718b3398501c677377055debecb6475ca6924dfdfd6bed44a4cfeff46a9e6257c5e76d34a59592a87a98b385943462886b91aa4fef05e8)
[遍历map例子](http://u.720life.cn/g/dc52ae30a155547ad9718b3398501c677377055debecb6475ca6924dfdfd6bed708b077c53cc92b8e49927a38e2102f64b1592c5070b2cda498c99624bbefca9)
[遍历数组例子](http://u.720life.cn/g/dc52ae30a155547ad9718b3398501c677377055debecb6475ca6924dfdfd6bede64053c4da5d862a6b196e9b7e257c40a10c80600fa46e44007c10a9d8b8d100)
[遍历嵌套list例子](http://u.720life.cn/g/dc52ae30a155547ad9718b3398501c677377055debecb6475ca6924dfdfd6bed9bbf151c49ef8714c913077371124ca3b057af3c316c934a268f202b1389f80e)

自定义标签
-----------
```javascript
 $.domTemplate.registerTag('tagName',function(ctx,name,exp){ }); //tagName 是自定义标签名称，用时要加上前缀，如定义'test'标签，用时h-test="" 
```
用法
```html
   
```
[自定义标签例子](http://u.720life.cn/g/dc52ae30a155547ad9718b3398501c677377055debecb6475ca6924dfdfd6bedb29c565175c96447bb25097aa9aeb63a9c3fa2c482cfbc40609af76bf7e49340)
参数
-----------

|Name |	Type |	 	Description|
|-----------|-----------|-----------|
|ctx 	|Context 	|	上下文，一般会用到 ctx.options、渲染表达式函数：ctx.compile(exp)和模板渲染函数：ctx.tpl(exp)|
|name |string 	|	标签名称|
|exp 	|string 	|	标签值|

字符串拼接运算
-----------
```html
  xxx1  
```
渲染结果
```html
  用户身份:uType-parky_18@163.com  
```

其他算术运算
-----------
```html
  xxx1  
```
渲染结果
```html
  0  
```
自定义函数
-----------
可以通过`$.domTemplate.registerHelper('functionName',function)`添加自定义函数，实例:
```html
  xxx1  
```
渲染结果
```html
  2016-05-30 11:20:42  
```
自定义函数示例
```javascript
 $.domTemplate.registerHelper('toPrefix', function (value) { return 'test:'+value; }); 
```
用法
```html
  xxx1  
```
渲染结果
```html
  test:parky_18@163.com  
```
[自定义函数例子](http://u.720life.cn/g/dc52ae30a155547ad9718b3398501c677377055debecb6475ca6924dfdfd6bed19c1d8fc581377febd587625e4ea0ebab51cdd40fa4a94f8d008ec981efa9365)

其他例子
-----------
[新闻APP](http://u.720life.cn/g/dc52ae30a155547ad9718b3398501c677377055debecb6475ca6924dfdfd6bed57a854f0fa73308e00dd4ce3130739ab)  
[图片懒加载和渲染成功回调例子](http://u.720life.cn/g/dc52ae30a155547ad9718b3398501c677377055debecb6475ca6924dfdfd6beda0f105b92472a90488b1f6f490dd51eadc5b4e860dca75ee075e91a337ac833e)



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6edb59eb59c82c3ca3ecbba1b546656327b204a106da0b467d1782352a32b0e245c261fd7275bf39a20625e17e74a079fc)