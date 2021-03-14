#yii2-ext
扩展了yii的功能，主要的扩展点有`ActiveRecord`，基于Web的`Controller`。

## BaseActiveRecord

### 子数据
1. 应用场景，不需要索引，零碎可有可无的数据。
2. 字段名由`FIELD_SUBDATA`确定，默认是`subData`。
3. 数据格式：`json`，字段类型`varchar`，最好是大一点的`varchar`。
4. 使用：设置子数据：`setSubData( $key, $val )`，获取子数据：`getSubData( $key, $default = null )`。
5. 所有的这些操作只有在`subData`字段在表中真实存在的时候才有效。

### 时间字段自动更新
- 应用场景，当更新一条记录的时候，最后更新时间字段需要也跟着更新的时候。
- 字段：`CREATED_AT`和`UPDATED_AT`，常量指定，默认是`created_at`和`updated_at`。
- 字段类型：int。
- 使用：在插入新记录时，`CREATED_AT`和`UPDATED_AT`自动赋值为当前时间，当更新记录时`UPDATED_AT`赋值为当前时间。
- 默认这个功能时开启的，想关闭该功能只要将实例变量`$timestamps`，设为`false`。

### 字段赋值（`setAttributes`和`setAttribute`）方法进行了覆盖
- 当赋值的属性是字符串类型的时候，自动执行了`trim`函数。

## BaseWebController

### Action支持所有形式的方法名写法
yii2默认的action方法名只能是 action{Name} 首字母大写其他全都是小写的，现在可以支持所有类型的写法，比如`actionIndex`，`actionSelectName`，`actionIndex-V1`等。

### `render`,`renderPartial`,`renderAjax`视图渲染方法
- `$view`参数默认值为空。
- 当`$view`参数为空时，自动使用当前`action`的`id`作为`$view`名。


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ed8364873b6f974af6f1ba9eca616188e697ef5e7ee265c5e5b4818836274f5698c63f3eac482611aeb48824b76a3cc49)