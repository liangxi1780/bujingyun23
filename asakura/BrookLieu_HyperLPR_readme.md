![logo_t](./demo_images/logo.png)

## HyperLPR   高性能开源中文车牌识别框架

#### [![1](https://badge.fury.io/py/hyperlpr.svg "title")](https://pypi.org/project/hyperlpr/)[![1](https://img.shields.io/pypi/pyversions/hyperlpr.svg "title")](https://pypi.org/project/hyperlpr/)

### 一键安装

`pip install hyperlpr`

###### 支持python3,支持Windows  Mac Linux 树莓派等。
###### 720p cpu real-time (st on MBP r15 2.2GHz haswell).


#### 快速上手

```python
#导入包
from hyperlpr import *
#导入OpenCV库
import cv2
#读入图片
image = cv2.imread("demo.jpg")
#识别结果
print(HyperLPR_PlateRecogntion(image))
```

#### 相关资源

- [python配置教程](http://u.720life.cn/g/8a0e6e781ca1335d5641e0f9d5e96ab9ff881679920118454a1c411a3b75de8990af05a3108b5a2cd9b73b026906f681)
- [相关技术博客](http://u.720life.cn/g/5997fd1f539dfbe7c9c67736234755a4c8b97d29bf7321761c55becf7f7b1d7273e5e1d2b18a2f6927e1b984402cff383ee591bea4567383217ee4a5af920a37)技术文章会在接下来的几个月的时间内连续更新
- [带UI界面的工程](http://u.720life.cn/g/d47e402704915d3bea7686bcd5bdba9397e5cc97182d622895e1fc4d25b65e8e)感谢群内小伙伴的工作
- [端到端(多标签分类)训练代码](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046caf66e50af027da722c4d7d2732e6e8507689f344f741a065c2ad537d8b6c37f)感谢群内小伙伴的工作
- [端到端(CTC)训练代码](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046a6fc0f2174137a457b7c46bc9f39e7b7462843819285a268759f7cee974e173b)感谢群内小伙伴工作

### 更新

- 可通过pip一键安装、更新的新的识别模型、倾斜车牌校正算法、定位算法。(2018.08.11)


- 提交新的端到端识别模型，进一步提高识别准确率(2018.08.03)
- [增加PHP车牌识别工程@coleflowers](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046b0cec1dca91470da798eb6690cde376d8df14c296e05f0b7dcdae6e17d33316ce51bc5da3aa5ec97069af36e48e76dae) (2018.06.20)
- 添加的新的Python 序列模型-识别率大幅提高(尤其汉字)(2018.3.12)
- 添加了HyperLPR Lite 仅仅需160 行代码即可实现车牌识别(2018.3.12)
- 提供精确定位的车牌矩形框(2018.3.12)

- 增加了端到端模型的cpp实现(Linux)(2018.1.31)
- 感谢 sundyCoder [Android 字符分割版本](http://u.720life.cn/g/54145d0471d91890860f7f8463c030460dadbca415984708bc129f83992aa50a14f0e7f0fed135a44a62007a02ea9061) 

- 增加字符分割[训练代码和字符分割介绍](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046b0cec1dca91470da798eb6690cde376d9e3a8b99432b9f8c1d5ebf5d94128156)2018.1.
- 更新了Android实现，大幅提高准确率和速度 (骁龙835 (*720*x*1280*)  ~50ms )(2017.12.27)
- 添加了IOS版本的实现（感谢[xiaojun123456](http://u.720life.cn/g/54145d0471d91890860f7f8463c030469ead1a84f97f80c65ad0e1d4ac0321de)的工作）
- 添加端到端的序列识别模型识别率大幅度提升,使得无需分割字符即可识别,识别速度提高20% (2017.11.17)
- 新增的端到端模型可以识别新能源车牌、教练车牌、白色警用车牌、武警车牌 (2017.11.17)
- 更新Windows版本的Visual Studio 2015 工程（2017.11.15）
- 增加cpp版本,目前仅支持标准蓝牌(需要依赖OpenCV 3.3) (2017.10.28)

### TODO

- 支持多种车牌以及双层
- 支持大角度车牌
- deep learning based 实时检测模型
- 轻量级识别模型
### 特性

- 速度快 720p,单核 Intel 2.2G CPU (MaBook Pro 2015)平均识别时间低于100ms
- 基于端到端的车牌识别无需进行字符分割
- 识别率高,卡口场景准确率在95%-97%左右
- 轻量,总代码量不超1k行

### 模型资源说明

- cascade.xml  检测模型 - 目前效果最好的cascade检测模型
- cascade_lbp.xml  召回率效果较好，但其错检太多
- char_chi_sim.h5 Keras模型-可识别34类数字和大写英文字  使用14W样本训练 
- char_rec.h5 Keras模型-可识别34类数字和大写英文字  使用7W样本训练 
- ocr_plate_all_w_rnn_2.h5 基于CNN的序列模型
- ocr_plate_all_gru.h5 基于GRU的序列模型从OCR模型修改，效果目前最好但速度较慢，需要20ms。
- plate_type.h5 用于车牌颜色判断的模型
- model12.h5 左右边界回归模型

### 注意事项:

- Win工程中若需要使用静态库，需单独编译
- 本项目的C++实现和Python实现无任何关联，都为单独实现
- 在编译C++工程的时候必须要使用OpenCV 3.3(DNN 库)，否则无法编译 

### Python 依赖

- Keras (>2.0.0)
- Theano(>0.9) or Tensorflow(>1.1.x)
- Numpy (>1.10)
- Scipy (0.19.1)
- OpenCV(>3.0)
- Scikit-image (0.13.0)
- PIL

### CPP 依赖

- Opencv 3.3 以上版本

### Linux/Mac 编译

- 仅需要的依赖OpenCV 3.3 (需要DNN框架)

```bash
cd Prj-Linux
mkdir build 
cd build
cmake ../
sudo make -j 
```

### CPP demo

```cpp
#include "../include/Pipeline.h"
int main(){
    pr::PipelinePR prc("model/cascade.xml",
                      "model/HorizonalFinemapping.prototxt","model/HorizonalFinemapping.caffemodel",
                      "model/Segmentation.prototxt","model/Segmentation.caffemodel",
                      "model/CharacterRecognization.prototxt","model/CharacterRecognization.caffemodel",
                       "model/SegmentationFree.prototxt","model/SegmentationFree.caffemodel"
                    );
  //定义模型文件

    cv::Mat image = cv::imread("/Users/yujinke/ClionProjects/cpp_ocr_demo/test.png");
    std::vector  res = prc.RunPiplineAsImage(image,pr::SEGMENTATION_FREE_METHOD);
  //使用端到端模型模型进行识别 识别结果将会保存在res里面
 
    for(auto st:res) {
        if(st.confidence>0.75) {
            std::cout << st.getPlateName() << " " << st.confidence << std::endl;
          //输出识别结果 、识别置信度
            cv::Rect region = st.getPlateRect();
          //获取车牌位置
 cv::rectangle(image,cv::Point(region.x,region.y),cv::Point(region.x+region.width,region.y+region.height),cv::Scalar(255,255,0),2);
          //画出车牌位置
          
        }
    }

    cv::imshow("image",image);
    cv::waitKey(0);
    return 0 ;
}
```

###  

### 可识别和待支持的车牌的类型

- [X] 单行蓝牌
- [X] 单行黄牌
- [X] 新能源车牌
- [X] 白色警用车牌
- [X] 使馆/港澳车牌
- [X] 教练车牌
- [ ] 武警车牌
- [ ] 民航车牌
- [ ] 双层黄牌
- [ ] 双层武警
- [ ] 双层军牌
- [ ] 双层农用车牌
- [ ] 双层个性化车牌

###### Note:由于训练的时候样本存在一些不均衡的问题,一些特殊车牌存在一定识别率低下的问题，如(使馆/港澳车牌)，会在后续的版本进行改进。

### 测试样例

![image](./demo_images/demo1.png)

![image](./demo_images/demo2.jpg)

#### Android示例

![android](./demo_images/android.png)

### 识别测试APP

- 体验 Android APP：[https://fir.im/HyperLPR](http://u.720life.cn/g/f8b3e1a861428a8afcad22f9322d8efaa28bc3b3aa6f95d62156b66b47058a56) (根据图片尺寸调整程序中的尺度，提高准确率)

#### 获取帮助

- HyperLPR讨论QQ群1: 673071218, 群2: 746123554 ,加前请备注HyperLPR交流。

### 作者和贡献者信息：

##### 作者昵称不分前后

- Jack Yu 作者(jack-yu-business@foxmail.com / https://github.com/szad670401)
- lsy17096535 整理(http://u.720life.cn/g/54145d0471d91890860f7f8463c0304676fb30ff2a7d1efbcfa173a6ba4712c1)
- xiaojun123456 IOS贡献(http://u.720life.cn/g/54145d0471d91890860f7f8463c030469ead1a84f97f80c65ad0e1d4ac0321de)
- sundyCoder Android第三方贡献(http://u.720life.cn/g/54145d0471d91890860f7f8463c030464f5e6f4e49f5415baebee304883b056f)
- coleflowers php贡献(@coleflowers)
- Free&Easy 资源贡献 
- 海豚嘎嘎 LBP cascade检测器训练

### 感谢码云为我们提供代码托管：https://gitee.com/zeusees/HyperLPR


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e865aae11018d1088feba6b0ffe33f7f7282e0f5d3744b9e00d78145408ad1436e73c8c3e2ee47907a1eb797fe7ed1308)