### 参考自https://github.com/shanren7/real_time_face_recognition

# real_time_face_recognition
由于不能满足当前的tensorflow版本，以及未能满足设计要求，进行了优化。  
* **采用facenet作为embedding嵌入模型，而非nn4神经网络**
* **使用原facenet代码的compare的思路进行人脸的比较，放弃了knn分类**
* **实现了无需训练分类模型，实时的比较人脸**

## Workflow
1.python3.6  
2.tensorflow=1.9.0(可运行在无gpu版)

## Running
1.从 https://github.com/davidsandberg/facenet 中下载预训练的分类模型，放在model_check_point下  
2.使用pip install requirements.txt安装需要的包，建议在virtualenv环境安装  
3.在目录下新建picture文件，将需要识别的人的图片放入其中，每人放入一张清晰的图片即可  
4.执行python real_time_face_recognize.py  




 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6eb34b01db49527949bd1483a1d54dbb28c6e741fe9f0bbb36c2499954edb1add0230d36b02931f7b309dc4da2eb35ff3c05c61263e75e12638f7bd4627bc2b50a)