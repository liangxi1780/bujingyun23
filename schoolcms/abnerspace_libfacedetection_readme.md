# libfacedetection

This is an open source library for CNN-based face detection in images. The CNN model has been converted to static variables in C source files. The source code does not depend on any other libraries. What you need is just a C++ compiler. You can compile the source code under Windows, Linux, ARM and any platform with a C++ compiler.

SIMD instructions are used to speed up the detection. You can enable AVX2 if you use Intel CPU or NEON for ARM.

The model file has also been provided in directory ./models/.

examples/detect-image.cpp and examples/detect-camera.cpp show how to use the library.

The library was trained by [libfacedetection.train](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046f2c7a59f905aa23ffd5b9116017e4ec9e68e2b06cb7a063a3c7e2217f63b7f3a9978d02bf2ef044a28293bc752828148).

![Examples](/images/cnnresult.png "Detection example")

## How to use the code

You can copy the files in directory src/ into your project,
and compile them as the other files in your project.
The source code is written in standard C/C++.
It should be compiled at any platform which supports C/C++.

Some tips:

  * Please add facedetection_export.h file in the position where you copy your facedetectcnn.h files, add #define FACEDETECTION_EXPORT to  facedetection_export.h file. See: [issues #222](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046f2c7a59f905aa23ffd5b9116017e4ec9d3424a08aab5bbd9770119177baeabcbf278e29ce58800cf953f560489ba1fb9)
  * Please add -O3 to turn on optimizations when you compile the source code using g++.
  * Please choose 'Maximize Speed/-O2' when you compile the source code using Microsoft Visual Studio.
  * You can enable OpenMP to speedup. But the best solution is to call the detection function in different threads.

You can also compile the source code to a static or dynamic library, and then use it in your project.

[How to compile](COMPILE.md)


## CNN-based Face Detection on Windows


| Method             |Time          | FPS         |Time          | FPS         |
|--------------------|--------------|-------------|--------------|-------------|
|                    |  X64         |X64          |  X64         |X64          |
|                    |Single-thread |Single-thread|Multi-thread  |Multi-thread |
|cnn (CPU, 640x480)  |  58.03ms     |  17.23      | 13.85ms      |   72.20     |
|cnn (CPU, 320x240)  |  14.18ms     |  70.51      |  3.38ms      |  296.21     |
|cnn (CPU, 160x120)  |   3.25ms     | 308.15      |  0.82ms      | 1226.56     |
|cnn (CPU, 128x96)   |   2.11ms     | 474.38      |  0.52ms      | 1929.60     |

* Minimal face size ~10x10
* Intel(R) Core(TM) i7-1065G7 CPU @ 1.3GHz

 

## Performance on WIDER Face
Run on default settings: scales=[1.], confidence_threshold=0.3, floating point:
```
AP_easy=0.849, AP_medium=0.816, AP_hard=0.601
```

## Author
* Shiqi Yu,  

## Contributors
All contributors who contribute at GitHub.com are listed [here](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046f2c7a59f905aa23ffd5b9116017e4ec9108a9c3b25a26ac519f5348dd76857cef72c0333962528d546cd220dab3f9132). 

The contributors who were not listed at GitHub.com:
* Jia Wu (吴佳)
* Dong Xu (徐栋)
* Shengyin Wu (伍圣寅)

## Acknowledgment
The work is partly supported by the Science Foundation of Shenzhen (Grant No. 20170504160426188).



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e39f5da8e4a495bd3bba287bc3c042aec349f70453e05ef5e3738a47476a25e1c780686e836903b37dfa6b5f3b4af4af19a4918327ff4beba380f4932f00d4904)