# 教你用Java来玩答题(百万英雄/冲刺大会等)

# MillionHero
今日头条的百万英雄答题助手 

《百万英雄》是一档全民知识互动游戏，在《百万英雄》里每场12道题目全部回答正确的人，将瓜分奖金。
游戏模式
  
  一共12道题，全部答对就可以平分奖金

如果可以把直播中的问题和答案提取出来，然后百度，然后统计一下哪个更相关，就可以辅助你答题了。
当然也可以直接把百度出来题目和答案都展示出来。本文用的第一种简单粗暴。

# 运行展示

![](1516095737427.gif)
# 工具介绍
* JAVA8
* Android 手机
* Adb 驱动
* TessOCR

# 原理说明

1. 将手机点击到直播界面（在这里我们先打开一张图片）；
2. 用Adb 工具获取当前手机截图
3. 用OCR进行图像识别，提取文字；
4. 将文字中的问题和答案提取出来；
5. 使用搜索工具并打开网页
6. 计算问题和答案的相似度，此处调用百度的Nlp接口或者采用PMI的方式
> 该公式的依据来自于维基百科:
      https://en.wikipedia.org/wiki/Pointwise_mutual_information
      
# 使用步骤
  相关软件工具安装和使用步骤请参考  [Android操作步骤](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046fb91dbde393717b23aa7bfb826bfcbe01c9c1d94095155769eeae6848ee90d249a14a28b130aa0ad4dda2cc6dea81dbb2032ad1efa013c47eae59758dd9e2c7f0d2643f2aa3ba92ec3000d94714dac51)

  
>PS:注意程序中的adb驱动目录要更换成自己的目录
  
  > 我的屏幕是1920*1080，如果是别的分辨率，暂时需要修改一下代码中的图片参数等。
    


# FAQ
+  详见 [Wiki-FAQ](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046fb91dbde393717b23aa7bfb826bfcbe069c09784d7ed519c6dd5700252d17753)
# 更新日志
+  详见 [changelog](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046fb91dbde393717b23aa7bfb826bfcbe02b8c55c8bdae51212616dfa14d133dbdc8550711d449110132625feb6aefec793a0a43b3d535529623e31d123eaf7a2a)
# 开发者列表
+  详见 [contributors](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046fb91dbde393717b23aa7bfb826bfcbe0aa2a45adc1ec80ddc991802c90fb073b8524c62fb873ddd0d91d5bc76833cd9d)
# TODO
+  可以增加一个图形化界面，分别对题目和答案进行搜索并进行展示。 

# QQ交流
+  283616637（500人）



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ec8d9b1836a5966c472845d8b6d38e9fc674cbadbeeebca81820e0e8588f3777b092c39159a7a8d04a794f215e2972a9b)