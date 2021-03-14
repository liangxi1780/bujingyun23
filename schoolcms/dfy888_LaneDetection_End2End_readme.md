# End-to-end Lane Detection

This repo contains the implementation of our paper [End-to-end Lane Detection through Differentiable Least-Squares Fitting](http://u.720life.cn/g/ef50ff7c3b5c85de9d07d6f28fa05754a01cce459c01dab4bf1e52a2e8429d9d) by Wouter Van Gansbeke, Bert De Brabandere, Davy Neven, Marc Proesmans and Luc Van Gool.

If you find this interesting or relevant for your work, consider citing:
```
@article{wvangansbeke_2019,
  title={End-to-end Lane Detection through Differentiable Least-Squares Fitting},
  author={Van Gansbeke, Wouter and De Brabandere, Bert and Neven, Davy and Proesmans, Marc and Van Gool, Luc},
  journal={arXiv preprint arXiv:1902.00293},
  year={2019}
}
```
## Update
I added a new directory __Backprojection_loss__ which is very similar to the other one. However, now the loss is a regression towards the coordinates in the original perspective instead of a regression in the birds eye view perspective towards the lane-line coefficients. We are primarily interested in the accuracy in this perspecitve after all. It also contains multi-lane detection experiments on the complete dataset of TuSimple (3626 images). 

## License

This software is released under a creative commons license which allows for personal and research use only. For a commercial license please contact the authors. You can view a license summary [here](http://u.720life.cn/g/b77ee7bfee69ac84b98b830822d7c3101745d83bd4a1837b72c6c2d6388fe3d0d9ede201715a4545c4cc3cc2f7c778a9).

## Setup

This repository compares two methods to achieve higher accuracy for lane detection applications. The former is the conventional segmentation approach and the latter will tackle this problem in an end-to-end manner. The segmentation approach depends on the cross-entropy loss in order to learn the road markings by attention. However this approach is not necessarily the most accurate. Since the final line coordinates are desired, a complete end-to-end method should achieve better results.

This end-to-end architecture consist of two parts. The first part is an off the shelf network to predict weight maps. These weights are applied to a mesh grid which are used for the last step. The last step can be considered as the final layer of the network which solves a weighted system of equations to calculate the final curve parameters of the road markings. The amount of weight maps depends on the amount of lane lines the network ought to detect. This means that a direct regression can be performed to the desired curve coordinates. After all, backpropagation through the whole architecture is now possible.

Finally we show results for egolane detection. The implementation proofs that this direct optimization is indeed possible and can achieve better results than the conventional segmentation approach. Moreover, this module can be applied to a broad range of tasks since the first stage of the architecture can be chosen freely. The extention to other domains such as object detection is considered as future work which also shows the effectiveness of this architecture.

## Requirements

I just updated the code to the most recent version of Pytorch (=pytorch 1.1) with python 3.7.
The other required packages are: opencv, scikit-learn, torchvision, numpy, matplotlib, json/ujson and pillow.

## Dataset

For the egolane detection experiment, I used a subset from the [TuSimple](http://u.720life.cn/g/6c8ce04e76de4dec0ef97460854eb2b42b3b9eb55c03b16ef6297c4fe03c4c57) dataset. You can download it [here](http://u.720life.cn/g/3a38f42308c8ee71aa166c0591609e00180f4b51c3f0e4d083b64b9277a2588233ccd948f9f720aee66188402eac005decbac9a4979f7b564e755b66890cf84fe027de16e9a3e6e025d667c51c2f5b6fde0ec41db8b22438da3f882033ea7ab2). You can find the images as well as the ground truth annotations in this folder to save you some work. Automatically 20% of the data will be used for validation. TuSimple provides the user 3 json files with ground truth coordinates of the lane lines. I appended the three files and used the index in this  json file to name a specific image. For example: file "10.jpg" in the data directory corresponds with "10.png" in the ground truth directory and with index 10 in the json files (= label_data_all.json and Curve_parameters.json).

You can download the complete TuSimple dataset from [here](http://u.720life.cn/g/54145d0471d91890860f7f8463c030469ef48b7c5d15bb2c3a69a17c4b92c45e8eede0c9dbf59366cd2f7b11510eead9e8412f91aad124a96e974740f9c26c88).

In the file Labels/Curve_parameters.json, the coefficients of the second degree polynomials are shown for the multiple lane lines in a bird's eye view perspective for the a subset of the data. (three zeros means that the lane line is not present in the image). So, the coefficients for the whole dataset are already computed for you.

## Run Code
To run the code (training phase):

` python main.py --image_dir /path/to/image/folder --gt_dir /path/to/ground_truth/folder --end_to_end True`

Flags:
- Set flag "end_to_end" to True to regress towards the final lane line coefficients directly.
- See `python main.py --help` for more information.

The weight maps will be computed but be aware that the appearance of the weight maps is architecture dependent. Augmenting this method with a line type branch in a shared encoder setup, results in: 

![end_to_end](https://user-images.githubusercontent.com/9694230/51836593-12459400-2301-11e9-9d1b-37cbe936f8cc.gif)

## Results Egolane Detection 

Our network architecture is based on [ERFNet](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046118d9a9a49930641da32d7e1390f4e709e41cac529ffaa4fae4e0c19831e4fa4).


| Method | Model | Area metric | Area 2  loss|
| --- | --- | --- | --- | 
| Segmentation | ERFNet | 1.603e-3 normalized | 2.733e-5  normalized |
| End to end | ERFNet | 1.437e-3 normalized| 1.912e-5 normalized | 
| **Gain** | ERFNet |1.66e-4\*(19.1mx38.2m)/2 1  = **0.06 m 2 ** | 8.21e-6 normalized |

( 1  Based on 3.7 m standard lane width in the US)


## Discussion

Practical discussion for multi lane detection:

- Instance segmentation: We primarily want to focus on our differentiable least squares module from our paper. This module is compatible with whatever method you choose. See it as an extra layer of the network to make lane detection completely end-to-end. Hence, an instance segmentation method can be combined with our method.

- To detect multiple lanes more robustly, the mask in the `Networks/LSQ_layer.py` file can be exploited.

- Continual learning setup: A possibility is to focus first on egolanes and add more lane lines during training. This makes the task more difficult over time. This will improve the convergence, since the features of the first lane lines can help to detect the later ones.

- Pretrainig: When a high number of lane lines are desired to be detected, the supervision could be be too weak (depending on the initialization and the network). Pretraining using a few segmentation labels is a good way to alleviate this problem.

- Proxy segmentation task: You could also combine our method with a proxy segmentation task in a shared encoder architecture. This can have some benefits (i.e. good initialization for the weight maps), although this makes the setup more complex.

## Acknowledgement
This work was supported by Toyota, and was carried out at the TRACE Lab at KU Leuven (Toyota Research on Automated Cars in Europe - Leuven)



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ea2efa92f99d4b9e57f8572706b93e67421c25b633c313d0c332a5af4b813e0ca8763b424a69ecf8f96b1a002026df492f2d9e5b0ecc6ddf7b460a3f4cdf1a239)