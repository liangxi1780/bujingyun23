[![PWC](https://img.shields.io/endpoint.svg?url=https://paperswithcode.com/badge/191111236/semantic-segmentation-on-semantic3d)](https://paperswithcode.com/sota/semantic-segmentation-on-semantic3d?p=191111236)
[![PWC](https://img.shields.io/endpoint.svg?url=https://paperswithcode.com/badge/191111236/3d-semantic-segmentation-on-semantickitti)](https://paperswithcode.com/sota/3d-semantic-segmentation-on-semantickitti?p=191111236)
[![License CC BY-NC-SA 4.0](https://img.shields.io/badge/license-CC4.0-blue.svg)](https://creativecommons.org/licenses/by-nc-sa/4.0/legalcode)

# RandLA-Net: Efficient Semantic Segmentation of Large-Scale Point Clouds (CVPR 2020)

This is the official implementation of **RandLA-Net** (CVPR2020, Oral presentation), a simple and efficient neural architecture for semantic segmentation of large-scale 3D point clouds. For technical details, please refer to:
 
**RandLA-Net: Efficient Semantic Segmentation of Large-Scale Point Clouds**  
[Qingyong Hu](http://u.720life.cn/g/7ca769f184b5536f46c3d7ad79d968e3e58b1f99ea3acf3270dbd295a8b57230abd0314393cc480009880fb0cc78f06a), [Bo Yang*](http://u.720life.cn/g/7180c70ac86840fd826e48160247de9240b86ce92ee977f7e5854228711b648f), [Linhai Xie](http://u.720life.cn/g/7ca769f184b5536f46c3d7ad79d968e3b6b02384c9b639eebc48fbc156a56658d00f2f341c27ac59b3416df8e12ec364), [Stefano Rosa](http://u.720life.cn/g/7ca769f184b5536f46c3d7ad79d968e3ad820fd7c0624fa0de9a3ce237d58660886485f5d62b8f7481673e85460bd001), [Yulan Guo](http://u.720life.cn/g/8e43253ce6908001608199217318b22868be55c24eeaffbd34330e98084d3eb0), [Zhihua Wang](https://www.cs.ox.ac.uk/people/zhihua.wang/), [Niki Trigoni](https://www.cs.ox.ac.uk/people/niki.trigoni/), [Andrew Markham](https://www.cs.ox.ac.uk/people/andrew.markham/).  
**[[Paper](http://u.720life.cn/g/ef50ff7c3b5c85de9d07d6f28fa057548822a88f21b21619d30d549494b14983)] [[Video](http://u.720life.cn/g/e890eb7ffa84f9513a1cd28c3149c56bdef1eff3ebe06c4d2b5f32e1b49c73f1)] [[Blog](http://u.720life.cn/g/85a9f52868358c3208a4b5fd9062e993df07ca44019ca1b5b3c8efb523cc1b550ab2a67f0fff5aac5552c4d2be6cc04a)]**  
 
 
     


	
### (1) Setup
This code has been tested with Python 3.5, Tensorflow 1.11, CUDA 9.0 and cuDNN 7.4.1 on Ubuntu 16.04.
 
- Clone the repository 
```
git clone --depth=1 https://github.com/QingyongHu/RandLA-Net && cd RandLA-Net
```
- Setup python environment
```
conda create -n randlanet python=3.5
source activate randlanet
pip install -r helper_requirements.txt
sh compile_op.sh
```

**Update 03/21/2020, pre-trained models and results are available now.** 
You can download the pre-trained models and results [here](http://u.720life.cn/g/3a38f42308c8ee71aa166c0591609e00a7077e4f2d534815140bc1d16084b944a1b3eb0bb71908f4cae947787b3957b53a26669fe42638dc469e939a21cc3eee7f26342dba97e5936fe17b4c234aa668).
Note that, please specify the model path in the main function (e.g., `main_S3DIS.py`) if you want to use the pre-trained model and have a quick try of our RandLA-Net.

### (2) S3DIS
S3DIS dataset can be found 
 here . 
Download the files named "Stanford3dDataset_v1.2_Aligned_Version.zip". Uncompress the folder and move it to 
`/data/S3DIS`.

- Preparing the dataset:
```
python utils/data_prepare_s3dis.py
```
- Start 6-fold cross validation:
```
sh jobs_6_fold_cv_s3dis.sh
```
- Move all the generated results (*.ply) in `/test` folder to `/data/S3DIS/results`, calculate the final mean IoU results:
```
python utils/6_fold_cv.py
```

Quantitative results of different approaches on S3DIS dataset (6-fold cross-validation):

![a](./figs/S3DIS_table.png)

Qualitative results of our RandLA-Net:

| ![2](./figs/S3DIS_area2.gif)   | ![z](./figs/S3DIS_area3.gif) |
| ------------------------------ | ---------------------------- |



### (3) Semantic3D
7zip is required to uncompress the raw data in this dataset, to install p7zip:
```
sudo apt-get install p7zip-full
```
- Download and extract the dataset. First, please specify the path of the dataset by changing the `BASE_DIR` in "download_semantic3d.sh"    
```
sh utils/download_semantic3d.sh
```
- Preparing the dataset:
```
python utils/data_prepare_semantic3d.py
```
- Start training:
```
python main_Semantic3D.py --mode train --gpu 0
```
- Evaluation:
```
python main_Semantic3D.py --mode test --gpu 0
```
Quantitative results of different approaches on Semantic3D (reduced-8):

![a](./figs/Semantic3D_table.png)

Qualitative results of our RandLA-Net:

| ![z](./figs/Semantic3D-1.gif)    | ![z](./figs/Semantic3D-2.gif)   |
| -------------------------------- | ------------------------------- |



**Note:** 
- Preferably with more than 64G RAM to process this dataset due to the large volume of point cloud


### (4) SemanticKITTI

SemanticKITTI dataset can be found  here . Download the files
 related to semantic segmentation and extract everything into the same folder. Uncompress the folder and move it to 
`/data/semantic_kitti/dataset`.
 
- Preparing the dataset:
```
python utils/data_prepare_semantickitti.py
```

- Start training:
```
python main_SemanticKITTI.py --mode train --gpu 0
```

- Evaluation:
```
sh jobs_test_semantickitti.sh
```

Quantitative results of different approaches on SemanticKITTI dataset:

![s](./figs/SemanticKITTI_table.png)

Qualitative results of our RandLA-Net:

![zzz](./figs/SemanticKITTI-2.gif)    


### (5) Demo

       


### Citation
If you find our work useful in your research, please consider citing:

	@article{hu2019randla,
	  title={RandLA-Net: Efficient Semantic Segmentation of Large-Scale Point Clouds},
	  author={Hu, Qingyong and Yang, Bo and Xie, Linhai and Rosa, Stefano and Guo, Yulan and Wang, Zhihua and Trigoni, Niki and Markham, Andrew},
	  journal={Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition},
	  year={2020}
	}


### Acknowledgment
-  Part of our code refers to  nanoflann  library and the the recent work  KPConv .
-  We use  blender  to make the video demo.


### License
Licensed under the CC BY-NC-SA 4.0 license, see [LICENSE](./LICENSE).


### Updates
* 21/03/2020: Updating all experimental results
* 21/03/2020: Adding pretrained models and results
* 02/03/2020: Code available!
* 15/11/2019: Initial release！



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e768a74dc49ef917c4b90a9f58319183099b347f41da15a5d6a301a4e10fbb29c155164a1f2263437fd822a51138dd902)