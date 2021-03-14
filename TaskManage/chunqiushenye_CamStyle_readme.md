# Camera Style Adaptation for Person Re-identification
================================================================

Code for Camera Style Adaptation for Person Re-identification (CVPR 2018). 

### Preparation

#### Requirements: Python=3.6 and Pytorch>=0.3.0

1. Install [Pytorch](http://u.720life.cn/g/acb692653d5b505b3f3987784eb6593d2ef80283ce279a731a00f737fe517334)

2. Download dataset
   
   - Market-1501   [[BaiduYun]](http://u.720life.cn/g/d47e402704915d3bea7686bcd5bdba93fe95ee67c913c277fffc6e17883fe366) [[GoogleDriver]](http://u.720life.cn/g/3a38f42308c8ee71aa166c0591609e00e8fe1f509cf6d05420512ea7c3bd9e1ca0a0ae4f91a2f5ae6049966ebf7a3a3534dc4d079ad6fe12aca38695b282b43d8465ad054a1e86f532ef954bc6be9a1f)
   
   - DukeMTMC-reID   [[BaiduYun]](http://u.720life.cn/g/d47e402704915d3bea7686bcd5bdba932ee4e20f525ca767e3e407b72572271b0ac84246add2d8eb3e83da0a8c83fb96) (password: chu1) [[GoogleDriver]](http://u.720life.cn/g/3a38f42308c8ee71aa166c0591609e00e8fe1f509cf6d05420512ea7c3bd9e1c3765360eff0becb2f1582dca9f21b6e3646e3cb1db247970b2fc65f6129a7588a3428927d81ece0a6fe244a2511c8b30)
   
   - Move them to 'CamStyle/data/market (or duke)'
   

3. Download CamStyle Images
   
   - Market-1501-Camstyle [[GoogleDriver]](http://u.720life.cn/g/3a38f42308c8ee71aa166c0591609e00a7077e4f2d534815140bc1d16084b94405400658e4973452b7d6d856464195ef811e877e96a97d1e6c7e114167390620779a2972342c34e40cd40905c0f1fec1)
   
   - DukeMTMC-reID-CamStyle  [[GoogleDriver]](http://u.720life.cn/g/3a38f42308c8ee71aa166c0591609e00a7077e4f2d534815140bc1d16084b944ddaa0bacea207d428bffcd63f56e6c838594687600ac73edff92df9bfd2c90f0f2dca0a1ce742cb8cc9d9f8e0ec7a101)
   
   - Move them to 'CamStyle/data/market (or duke)/bounding_box_train_camstyle'


### CamStyle Generation
You can generate CamStyle imgaes with [CycleGAN-for-CamStyle](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046aabfc4bda227cff2e9af6f46b25bb7e437bf673cd659c39550f753cdc3674999297b8876d52964e50c2b8273c4ca3d3bea6eba2d931b64676c885b27b847cd8a)


### Training and test re-ID model

1. IDE
  ```Shell
  # For Market-1501
  python main.py -d market --logs-dir logs/market-ide
  # For Duke
  python main.py -d duke --logs-dir logs/duke-ide
  ```
2. IDE + CamStyle
  ```Shell
  # For Market-1501
  python main.py -d market --logs-dir logs/market-ide-camstyle --camstyle 46
  # For Duke
  python main.py -d duke --logs-dir logs/duke-ide--camstyle --camstyle 46
  ```
  
3. IDE + CamStyle + Random Erasing[4]
  ```Shell
  # For Market-1501
  python main.py -d market --logs-dir logs/market-ide-camstyle-re --camstyle 46 --re 0.5
  # For Duke
  python main.py -d duke --logs-dir logs/duke-ide--camstyle-re --camstyle 46 --re 0.5
  ```

4. IDE + CamStyle + Random Erasing[4] + re-ranking[3]
  ```Shell
  # For Market-1501
  python main.py -d market --logs-dir logs/market-ide-camstyle-re --camstyle 46 --re 0.5 --rerank
  # For Duke
  python main.py -d duke --logs-dir logs/duke-ide--camstyle-re --camstyle 46 --re 0.5 --rerank
  ```
  
### Results

 
    
        
       Market-1501 
       Duke 
    
    
       Methods 
       Rank-1 
       mAP 
       Rank-1 
       mAP 
    
    
       IDE 
       85.6 
       65.8 
       72.3 
       51.8 
    
    
       IDE+CamStyle 
       88.1 
       68.7 
       75.2 
       53.4 
    
    
       IDE+CamStyle+Random Erasing 
       89.4 
       71.5 
       78.3 
       57.6 
    
 


### References

- [1] Our code is conducted based on [open-reid](http://u.720life.cn/g/54145d0471d91890860f7f8463c030467189961273e698ca29eccbaf27097c96216c0cdd34f6ecb52e5abe8a10acd103)

- [2] Unpaired Image-to-Image Translation using Cycle-Consistent Adversarial Networks, ICCV 2017

- [3] Re-ranking Person Re-identification with k-reciprocal Encoding. CVPR 2017.

- [4] Random Erasing Data Augmentation. Arxiv 2017.




### Citation

If you find this code useful in your research, please consider citing:

    @inproceedings{zhong2018camera,
    title={Camera Style Adaptation for Person Re-identification},
    author={Zhong, Zhun and Zheng, Liang and Zheng, Zhedong and Li, Shaozi and Yang, Yi},
    booktitle={CVPR},
    year={2018}
    }

    
### Contact me

If you have any questions about this code, please do not hesitate to contact me.

[Zhun Zhong](http://u.720life.cn/g/821f6a2b5bc9f232db4f923df88129aea1a0841ae11c30f52295f9a2a7fead5f)



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e834e59a5343aee9e7654f75c5a7fd75341887dfc4f8c4e34733646df599c016d5aebea0aab4530972d7570bccceb2f1c)