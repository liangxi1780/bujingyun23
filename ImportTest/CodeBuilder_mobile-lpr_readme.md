  
 
 

# mobile-lpr
Mobile-LPR 是一个面向移动端的准商业级车牌识别库，以NCNN作为推理后端，使用DNN作为算法核心，支持多种车牌检测算法，支持车牌识别和车牌颜色识别。

## 特点

- 超轻量，核心库只依赖NCNN，并且对模型量化进行支持
- 多检测，支持SSD,MTCNN,LFFD等目标检测算法
- 精度高，LFFD目标检测在CCPD检测AP达到98.9，车牌识别达到99.95%， 综合识别率超过99%
- 易使用，只需要10行代码即可完成车牌识别
- 易扩展，可快速扩展各类检测算法

## 算法流程
![算法流程](image/flow.jpg)
## 构建及安装
1. 下载源码
```sh
git clone https://gitee.com/CodeBuilder/mobile-lpr.git
```
2. 准备环境
- 安装opencv4.0及以上， freetype库
- 安装cmake3.0以上版本，支持c++11的c++编译器，如gcc-6.3

3. 编译安装
```sh
mkdir build
cd build
cmake ..
make install
```

## 使用及样例
1.使用MTCNN检测
- 代码样例
```cpp
void test_mtcnn_plate(){
    pr::fix_mtcnn_detector("../../models/float", pr::mtcnn_float_detector);
    pr::PlateDetector detector = pr::IPlateDetector::create_plate_detector(pr::mtcnn_float_detector);

    pr::fix_lpr_recognizer("../../models/float", pr::float_lpr_recognizer);
    pr::LPRRecognizer lpr =  pr::float_lpr_recognizer.create_recognizer();
    Mat img = imread("../../image/plate.png");

    ncnn::Mat sample = ncnn::Mat::from_pixels(img.data, ncnn::Mat::PIXEL_BGR, img.cols, img.rows);
    std::vector  objects;
    detector->plate_detect(sample, objects);
    lpr->decode_plate_infos(objects);

    for (auto pi : objects)
    {
        cout   objects;
    detector->plate_detect(sample, objects);
    lpr->decode_plate_infos(objects);

    for (auto pi : objects)
    {
        cout   objects;
    detector->plate_detect(sample, objects);
    lpr->decode_plate_infos(objects);

    for (auto pi : objects)
    {
        cout   objects;
    detector->plate_detect(sample, objects);
    lpr->decode_plate_infos(objects);

    for (auto pi : objects)
    {
        cout << "plate_no: " << pi.plate_color << pi.plate_no << " box:" << pi.bbox.xmin << ","
             << pi.bbox.ymin << "," << pi.bbox.xmax << "," << pi.bbox.ymax << "," << pi.bbox.score << endl;
    }
}

```

- 效果示例:

![量化后模型车牌识别](image/quantize-mtcnn-plate.png)

## 后续工作
- 添加更优的算法支持
- 优化模型，支持更多的车牌类型，目前支持普通车牌识别，欢迎各位大神提供更好的模型
- 优化模型，更高的精度
- 添加Android 使用实例
- 性能评估

## 参考
1. [light-LPR](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046e1bd961d62ad329f696336a7bb3cda798b6e445c7f2070154bc3f9bc64069d4a) 本项目的模型大部分来自与此
2. [NCNN](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046b66f7510fef170a35e575499ebad4f36) 使用NCNN作为后端推理
3. [LFFD](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046564e9eb0eac2cd5438f569cb6f94b606ac300a60d9cab2437830c6835b558917d49242698ecc4b53194204d0271e6fa08576a8315be1e9e12f25fd501b209de3) LFFD的模型及实现
4. [CCPD](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046077945eabb931e513f2cdad9411782a346df0ab23429adc9b475367f40159642) 中国车牌数据集，达到200万样本
5. [HyperLPR](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046b0cec1dca91470da798eb6690cde376d985c969df9d90b4d37883cc0705384db) 一个开源的车牌识别框架


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6eef708b72d171abbf3ea9aa460e46f71337aea561e6f53b94cd7c0d2c4f156a18f7693cd282cba0d483360ccf3708345a)