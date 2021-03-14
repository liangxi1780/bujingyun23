# CVFundamentals
  - computer vision fundamentals 
  - https://gitee.com/anjiang2020_admin/CCV2/blob/master/README.md
  - week1 
```
CV核心基础WEEK1 :  基本图像处理
https://gitee.com/anjiang2020_admin/CCV2/tree/master/week1
Pipeline:
0.职业规划
1.Computer Vision 的由来
2.计算机如何看到图像
3.计算机处理图像的方式，方法

作业：
   1 用滤波操作给图片去除噪声，
     选做：将自己的logo水印打到经过滤波后的照片上。
   目的：感受滤波操作的作用，用数字上的滤波操作模拟老照片真实镜头的滤波功能。
   参考步骤：
   1 拿到老师给定的图片：week1/week1_homework.png。
   2 对图片进行滤波操作。参考week1/week1_class_code_after_class.py
   3 修改滤波核的数值和滤波核的大小，调整出最好的效果。
   4 制作自己的logo水印的照片
   5 将水印添加到图片上。参考week1/week1_class_code_after_class.py
```
 - week2[https://gitee.com/anjiang2020_admin/CCV2/tree/master/week2]
```
 CV核心基础WEEK2 ：认识计算机视觉
 Pipeline:
 1.    从图像处理到计算机视觉
 2.    计算机视觉的两个步骤
 3.    计算机视觉第一步：图像描述子

 作业：
  
  编写计算机视觉的第0版程序。
  步骤
  1 生成10张图片，对应0,1,2,3,4,5,6,7,8,9.
  2 对这10张图片提取特征x。
  3 用一个判别器f(x)来决策输出结果y。
    这个判别器达到作用：
    当x是 “0”图片对应的特征时，y=f(x)=0
    当x是 “1”图片对应的特征时，y=f(x)=1
    当x是 “2”图片对应的特征时，y=f(x)=2
    当x是 “3”图片对应的特征时，y=f(x)=3
    当x是 “4”图片对应的特征时，y=f(x)=4
    当x是 “5”图片对应的特征时，y=f(x)=5
    当x是 “6”图片对应的特征时，y=f(x)=6
    当x是 “7”图片对应的特征时，y=f(x)=7
    当x是 “8”图片对应的特征时，y=f(x)=8
    当x是 “9”图片对应的特征时，y=f(x)=9
 4 参考代码:week2/recognize_computer_vision.py

```

   - week3[https://gitee.com/anjiang2020_admin/CCV2]
```
CV核心基础WEEK3 ：经典机器学习（一）
Pipeline:
1    监督学习与非监督学习
2    第一个可训练的监督学习模型：线性回归模型的3类解法
3    使用线性模型，解决字符分类问题
4    逻辑回归模型

作业：
编写计算机视觉的第1版程序：用线性回归模型，解决数字图片分类问题，
可选要求：用pytorch 的auto_grad功能。

步骤：
  1 生成10张图片，对应0,1,2,3,4,5,6,7,8,9.
  2 对这10张图片提取特征x。
  3 用一个线性判别器f(x)来决策输出结果y。
  4 判别器的训练要使用梯度下降法，写代码的时候要用到pytorch 的auto_grad功能。
 达到作用：
    当x是 “0”图片对应的特征时，y=f(x)=0
    ...
    当x是 “9”图片对应的特征时，y=f(x)=9
可参考代码：
  /week3/recognize_computer_vision_linear_model.py,线性模型解决图片识别问题课程代码
  /week3/how_to_use_auto_grad.py,测试pytorch auto_grad使用方法
  /week3/data_display.ipynb 数据显示
  /week3/week2作业答案课堂讲解.ipynb
  /week3/auto_grad使用时的注意事项.ipynb
  /week3/auto_grad形式的梯度下降.ipynb
  /week3/running_jupyter.pdf,jupyter运行命令
  jupyter常用效率快捷键：https://zhuanlan.zhihu.com/p/143919082
``````



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6efc42dc4b7d6ffda404b9466047fd5e2d868ecb92171ccfb0edb9eac2e24e4895b154ba21e1f6c611a29854b9b0407073)