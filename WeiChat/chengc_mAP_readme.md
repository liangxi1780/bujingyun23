# mAP (mean Average Precision)

[![GitHub stars](https://img.shields.io/github/stars/Cartucho/mAP.svg?style=social&label=Stars)](https://github.com/Cartucho/mAP)

This code will evaluate the performance of your neural net for object recognition.

 
   
 

In practice, a **higher mAP** value indicates a **better performance** of your neural net, given your ground-truth and set of classes.

## Table of contents

- [Explanation](#explanation)
- [Prerequisites](#prerequisites)
- [Quick start](#quick-start)
- [Running the code](#running-the-code)
- [Authors](#authors)

## Explanation
The performance of your neural net will be judged using the mAP criterium defined in the [PASCAL VOC 2012 competition](http://u.720life.cn/g/ac5c2e8eaf2d57cc281aa2bb56ce95fd21a35882a1206e6427762ade4946dd46d94b4544d787e7e6b2cfec1c2ce71e4c). We simply adapted the [official Matlab code](http://u.720life.cn/g/ac5c2e8eaf2d57cc281aa2bb56ce95fd21a35882a1206e6427762ade4946dd46291aedf8dc956cd50a575d6a62f294a1681c0db7b7cccd5d4eda76eda48f9e83) into Python (in our tests they both give the same results).

First (**1.**), we calculate the Average Precision (AP), for each of the classes present in the ground-truth. Finally (**2.**), we calculate the mAP (mean Average Precision) value.

#### 1. Calculate AP

For each class:

First, your neural net **detection-results** are sorted by decreasing confidence and are assigned to **ground-truth objects**. We have "a match" when they share the **same label and an IoU >= 0.5** (Intersection over Union greater than 50%). This "match" is considered a true positive if that ground-truth object has not been already used (to avoid multiple detections of the same object). 

 

Using this criterium, we calculate the precision/recall curve. E.g:

 

Then we compute a version of the measured precision/recall curve with **precision monotonically decreasing** (shown in light red), by setting the precision for recall `r` to the maximum precision obtained for any recall `r' > r`.

Finally, we compute the AP as the **area under this curve** (shown in light blue) by numerical integration.
No approximation is involved since the curve is piecewise constant.

#### 2. Calculate mAP

We calculate the mean of all the AP's, resulting in an mAP value from 0 to 100%. E.g:

 

 

## Prerequisites

You need to install:
- [Python](http://u.720life.cn/g/74e7b7c595201f48e3f4da7562c1a8265391d71b10b58cef78feb3ff65d1b8966dc22455cc7c97d787bf148175bbaa2b)

Optional:
- **plot** the results by [installing Matplotlib](http://u.720life.cn/g/45ed8da52b23a4eb3078a6b2c05ed124d3e06eeb3251ba19838fe5f02168d79d41e510f30e08b06b0b427f4845ca2068) - Linux, macOS and Windows:
    1. `python -mpip install -U pip`  
    2.  `python -mpip install -U matplotlib`
-  show **animation** by installing [OpenCV](http://u.720life.cn/g/25c6ec599554e791edfb864b96d06126aca9758ca1d18b906ae5b188239d888b):
    1. `python -mpip install -U pip`
    2. `python -mpip install -U opencv-python`  

## Quick-start
To start using the mAP you need to clone the repo:

```
git clone https://github.com/Cartucho/mAP
```

## Running the code

Step by step:

  1. [Create the ground-truth files](#create-the-ground-truth-files)
  2. Copy the ground-truth files into the folder **input/ground-truth/**
  3. [Create the detection-results files](#create-the-detection-results-files)
  4. Copy the detection-results files into the folder **input/detection-results/**
  5. Run the code:
         ```
         python main.py
         ```

Optional (if you want to see the **animation**):

  6. Insert the images into the folder **input/images-optional/**


#### PASCAL VOC, Darkflow and YOLO users

In the [scripts/extra](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046bc4c59c57d237fc4523e19d48a71de8b8599979f58b17c96b6a0ee1adafc43b4bd8ebd6ca90f00f9f49f0f5702a9fad7) folder you can find additional scripts to convert **PASCAL VOC**, **darkflow** and **YOLO** files into the required format.

#### Create the ground-truth files

- Create a separate ground-truth text file for each image.
- Use **matching names** for the files (e.g. image: "image_1.jpg", ground-truth: "image_1.txt").
- In these files, each line should be in the following format:
    ```
              [ ]
    ```
- The `difficult` parameter is optional, use it if you want the calculation to ignore a specific detection.
- E.g. "image_1.txt":
    ```
    tvmonitor 2 10 173 238
    book 439 157 556 241
    book 437 246 518 351 difficult
    pottedplant 272 190 316 259
    ```

#### Create the detection-results files

- Create a separate detection-results text file for each image.
- Use **matching names** for the files (e.g. image: "image_1.jpg", detection-results: "image_1.txt").
- In these files, each line should be in the following format:
    ```
               
    ```
- E.g. "image_1.txt":
    ```
    tvmonitor 0.471781 0 13 174 244
    cup 0.414941 274 226 301 265
    book 0.460851 429 219 528 247
    chair 0.292345 0 199 88 436
    book 0.269833 433 260 506 336
    ```
## Authors:
* **João Cartucho** - Please give me your feedback: to.cartucho@gmail.com

    Feel free to contribute

    [![GitHub contributors](https://img.shields.io/github/contributors/Cartucho/mAP.svg)](https://github.com/Cartucho/mAP/graphs/contributors)



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e220a38df796964b99b0175b9e22de1b75929ad24535dc76d68675a237b677946164822fbbed164a17ad43b8c1ba7c50f)