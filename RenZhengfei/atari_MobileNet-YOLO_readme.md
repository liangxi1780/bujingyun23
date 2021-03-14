## MobileNet-YOLO Caffe

A caffe implementation of MobileNet-YOLO detection network , train on 07+12 , test on VOC2007

Network|mAP|Resolution|Download|NetScope|Inference time (GTX 1080)|Inference time (i5-7500)
:---:|:---:|:---:|:---:|:---:|:---:|:---:
MobileNetV2-YOLOv3|70.7|352|[caffemodel](models/mobilenetv2_voc/yolo_lite)|[graph](http://u.720life.cn/g/15260e995d37f776813c1ff4ae01d57af8d6d8892cebe90e2ff2e9c892b82e756f1d1695ae3b216c42ef992a231da8d4c3cb1cf1943fcd7a6c888bdd5d403fb23ba6043c4ea0ae3697f104dd1b4df440)|[6.65 ms](benchmark/test.log)|217 ms

* inference time was log from [script](benchmark/test_yolov3_lite.sh) , does not include pre-processing 
* the [benchmark](/benchmark) of cpu performance on Tencent/ncnn  framework
* the deploy model was made by [merge_bn.py](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304604f36e9da0d398e300d42260683314892684a678db94988083d67cc352ec67533e6859139dd0e93d4d403e9baf5380b25d3bac97e23e3a7d6207bc86fa427398), set eps = your prototxt batchnorm eps
* old models please see [here](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046e50b9d3fd8d72905463998c9da2e4f28c396a392f030eafd36eb13d67f5b13881bced65174d7c782763e5063802feb18b590f20ec0e5c55c9fe2b2e743d7caab5bb6707b32dc04dcbc6018de6ddae342)

This project also support ssd framework , and here lists the difference from ssd caffe

* Multi-scale training , you can select input resoluton when inference
* Modified from last update caffe (2018)
* Support multi-task model 
* [pelee + driverable map](data/bdd100k)

## Update

1. CODE UPDATED FOR OPENCV 3
2. Channel pruning

### CNN Analyzer

Use this [tool](http://u.720life.cn/g/997e1ca830aa32106a75baeb95f03ebf113974cd19715222b1d8ab8c267f61cc060e2e7c04959abf57cdc4c345608d35cfaf59dc32a689f340ccf9f17c74e6c4) to compare macc and param , train on 07+12 , test on VOC2007

network|mAP|resolution|macc|param|pruned
:---:|:---:|:---:|:---:|:---:|:---:|
MobileNetV2-YOLOv3|0.707|352|1.22G|4.05M|N|
MobileNetV2-YOLOv3|0.702|352|1.01G|2.88M|Y|
[Pelee-SSD](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304604f36e9da0d398e300d42260683314899cfeaa239c05958433e96eb0e530df30)|0.709|304|1.2G|5.42M|N|
[Mobilenet-SSD](http://u.720life.cn/g/54145d0471d91890860f7f8463c030467f5265af9165ee92a9731d83130a55ace2fd57663b1bc549152e9de26c68b87e)|0.68|300|1.21G|5.43M|N|
[MobilenetV2-SSD-lite](models/mobilenetv2_voc/ssd_lite)|0.709|336|1.10G|[5.2M](http://u.720life.cn/g/3a38f42308c8ee71aa166c0591609e00a7077e4f2d534815140bc1d16084b94493e7f339786a3abf55dfe76ddaf3ac51dc606b751c371edf868160b30897440778f026bd64bed6cc408ef26e54101539)|N|

* MobileNetV2-YOLOv3 and MobilenetV2-SSD-lite were not offcial model

### Coverted TensorRT models

[TensorRT-Yolov3-models](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046b5f9061fbdcf64c4450feb328f9d5d9ae3f1cd31ea3bcabdda097d84ed03d402b06f07a141ff0eeb1ac957965fd0e09a)

[Pelee-Driverable_Maps](http://u.720life.cn/g/e890eb7ffa84f9513a1cd28c3149c56b8b165e11332b73f69f9a6f3624a3e576), run 89 ms on [jetson nano](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304678034b00a66cf3125e08d7bba51d511a3ad56ae3ccd7e604ae1e87f8129d7273) , [running project](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046c2b8497c26467293889265b15ccad4698294e4f250b2612ff9029c1f2f479804)

### YOLO Segmentation

[How to use](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046e50b9d3fd8d72905463998c9da2e4f28b4935811823427fa76e1b0c4885524f398d80e064f4a6dd40b5561b6b39a7eadc043e9c2478a70d20b3227ccff68da37)

## Windows Version

[Caffe-YOLOv3-Windows](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046649c08e2b49a227528498436d1d5252ff9b156dd01f0732cfc4ccca8079308bf)

### Oringinal darknet-yolov3

[Converter](models/darknet_yolov3) 

test on coco_minival_lmdb (IOU 0.5)

Network|mAP|Resolution|Download|NetScope|
:---:|:---:|:---:|:---:|:---:
yolov3|54.2|416|[caffemodel](http://u.720life.cn/g/3a38f42308c8ee71aa166c0591609e00e8fe1f509cf6d05420512ea7c3bd9e1c6d25b67facb86bc6fca02ea211392dca75b00291c4ff117ca21a32efaff592abd2e8b0a1581929eb3bf1bdd09d185d592135e0239af5f5a4eb461b1ab90d9828)|[graph]http://ethereon.github.io/netscope/#/gist/59c75a50e5b91d6dd80a879df3cfaf55
yolov3-spp|59.8|608|[caffemodel](http://u.720life.cn/g/3a38f42308c8ee71aa166c0591609e00e8fe1f509cf6d05420512ea7c3bd9e1cee9e399c72b020bfea6a86221097063326ab7de163f3a537cb2cb02a82ef595d6e0a082358ad0ca31e3ce85271f39dca56716d2832c1f1437a8d7f06e677aec3)|[graph]http://ethereon.github.io/netscope/#/gist/71edbfacf4d39c56f2d82cbcb739ae38


### Model VisulizationTool

Supported on [Netron](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046c57a6ba9cf72a721f72e9da38afa016b3de6857097be1a86e2e4ebcbdfae3c23) , [browser](http://u.720life.cn/g/4f2c85410d4923d55c803a8e51173f4e367dd27986084d78db7f9f9067e343a2d9e3a2586bf12995e76279826c11e272) version

### Build , Run and Training

See [wiki](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046e50b9d3fd8d72905463998c9da2e4f285efeb6bc21a547d9c223b628d87ea687)

See [docker](http://u.720life.cn/g/ce46a7789a867c84732a8edd85365befad16160b17ffa0c46f014ea60a703edfc85128a56bef90d558a4b4efd2680cc3)

## License and Citation


Please cite MobileNet-YOLO in your publications if it helps your research:

    @article{MobileNet-YOLO,
      Author = {eric612 , Avisonic , ELAN},
      Year = {2018}
    }
    
## Reference

> https://github.com/weiliu89/caffe/tree/ssd

> https://pjreddie.com/darknet/yolo/

> https://github.com/chuanqi305/MobileNet-SSD

> https://github.com/gklz1982/caffe-yolov2

> https://github.com/yonghenglh6/DepthwiseConvolution

> https://github.com/alexgkendall/caffe-segnet

> https://github.com/BVLC/caffe/pull/6384/commits/4d2400e7ae692b25f034f02ff8e8cd3621725f5c

> https://www.cityscapes-dataset.com/

> https://github.com/TuSimple/tusimple-benchmark/wiki

> https://github.com/Robert-JunWang/Pelee

> https://github.com/hujie-frank/SENet

> https://github.com/lusenkong/Caffemodel_Compress

Cudnn convolution

> https://github.com/chuanqi305/MobileNetv2-SSDLite/tree/master/src



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ed3555a58aa98f12b8a13896f1a055d529a020fbda3932026f1b57bd7372ea91192e29846e558c4fd533cf57e3977478b)