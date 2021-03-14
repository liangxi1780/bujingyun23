# 四位验证码CNN识别

## 1.参考
[1] [街道多位数字CNN识别，神经网络架构参考](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304639beef16ecdf45e04ce01c1b607f4d6ca31b2b1a02ea0b610d0dda4d24f49be4)

[2] [关于CNN的详细解释，深度学习入门必备](http://u.720life.cn/g/df11a8773b601ea6763063801f3d742ea7237d76f3eeaf677a818cdc9ce1337bcae8b745766f63a52ef4939286a36c503ca5069bc77a1a5ed33ac850fce470818af39dbf1f6aee58fc60f4a59c4548e1)


[3] [验证码生成参考类](http://u.720life.cn/g/5c954f4cd4204fb6c09a7e58aa70844da2b730da0ec5621a6553057e9cafa790c45b42c06d4669b4b970c5f8d7c93d5db0d87148098525ffdab8720e5d3542308873a125037281935bee775d7f1e3ba99187161ad83e100ba43cc4a560121f870626097a7352d38f7cb5f87a3e042dda290181edfd1d4469eb907d60670532b6)

## 2.支持
[1] Python3.6.1 or >=3.5

[2] TensorFlow 1.2

[3] numpy

## 3.简介
通过训练CNN（卷积神经网络）对4位验证码识别，其中字符有0-9a-zA-Z共计62种，但是预测结果不区分大小写，所以最终预测结果为36种。验证码由多个字体、颜色、干扰线随机生成。

## 4.项目结构
[1] 整体结构
>model.py 整个神经网络结构

>code_utils.py 将字符转换为一维数组以及一维数组转换为字符的工具类

>image_utils.py 读取图片，处理图片数据的工具类

>train.py 主程序类，其中包括参数设置以及整个神经网络训练流程控制

>test.py 提取大量的测试label测试神经网络的最终效果

[2] 以下为缺少文件夹：

>[test-images 所有测试验证码图片在这个文件夹](http://u.720life.cn/g/d47e402704915d3bea7686bcd5bdba93ae469007a8a176e8823dffd1514b2588 ) 密码:9g3i

>[train-images 所有训练验证码图片在这个文件夹](http://u.720life.cn/g/d47e402704915d3bea7686bcd5bdba93d16653034f5942420c9f0c0e8ffcf276) 密码:obit

## 5.结果

以下是对100万张训练验证码进行训练，20万张不参与训练的测试验证码测试出的结果

一般的验证码系统都会去掉类似的字符（例如：i, l, o, 1, 0...），为了更全面的测试，所以我选择将这些难以识别的字符也添加进去测试，可以看出有这些难以辨别的字符时，连人类也很难去完全预测正确（下图，第一行为预测值，第二行为真实值）

![](http://git.oschina.net/kdldbq/verification-decoder/raw/master/result/train_1w.jpg)

### 训练60万次时的结果：

![](http://git.oschina.net/kdldbq/verification-decoder/raw/master/result/60w_loss.png)

![](http://git.oschina.net/kdldbq/verification-decoder/raw/master/result/60w_output.png)

```
最终结果： 四个字符同时正确率: 90.02%		单个字符正确率: 97.42%
```

*说明：本项目仅用于学习，勿用于网络攻击及验证码暴力破解


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ea82ded4fa97fa3ff9a56c90ce5b14912efbadba9e493212cddb17c1c3118a20874dda7e7a66a3f5b3729829d1e5b259dd2d35ce5e4589989b970e0e64813b665)