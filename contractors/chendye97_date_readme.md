# demo & api 详见：

http://leecade.github.com/date/


# update:

## 2013.01.07

1. 修正农历近几天的错误

```
月/日 出错
* 2013.1.1   11.20
2013-1-1 星期二 农历 12.19 壬辰年(龙) 壬子月 丁卯日   元旦节

2013-1-11 11.30
2013-1-11 星期五 农历 腊月廿九 壬辰年(龙) 癸丑月 丁丑日  除夕  index.html:413

月 出错
2013-1-12  12.1
2013-1-12 星期六 农历 十三月初一 壬辰年(龙) 癸丑月 戊寅日 

* 2013-2-9 12.29
2013-2-9 星期六 农历 13.29 癸巳年(龙) 甲寅月 丙午日
```

2. 允许对任意日期或日期段的算法结果进行人工干预(埃及日历是人定的, 随时可能改1天)

比如:

1) 修正 2013-1-1 农历 月份 -1

```
conf.date.fixDate: ["2013-1-1=0|-1|0"]
```

2) 多组修正和日期范围(用 ~ 分隔)

```
conf.date.fixDate: ["2013-1-1~2013-1-11=0|-1|1", "2013-1-12~2013-2-9=0|-1|0"]
```


## 2012.9.7

1. Fixed: mac + firefox13 下农历日期显示为 Undefined

原因：对数组索引的浮点数时处理 有差异 [2.0001] ==> [2]

## 2011.9.26:

1. 按jsdoc规范更新注释
2. 扩展G.date.format方法
3. 调整接口，参数省略策略统一为 G.date.format/G.date.lunarTpl/G.date.islTpl 允许省略
4. 获取生肖名拆分为独立接口 G.date.toSx()


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e7d95d99217f55e1a4d308b1d23b091f47003e63109c1f18166b24de8223b61d0b3e47061d9a3782c6d790a35562235fe)