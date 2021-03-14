**About PyTorch 1.2.0**
  * Now the master branch supports PyTorch 1.2.0 by default.
  * Due to the serious version problem (especially torch.utils.data.dataloader), MDSR functions are temporarily disabled. If you have to train/evaluate the MDSR model, please use legacy branches.

# EDSR-PyTorch

**About PyTorch 1.1.0**
  * There have been minor changes with the 1.1.0 update. Now we support PyTorch 1.1.0 by default, and please use the legacy branch if you prefer older version.

![](/figs/main.png)

This repository is an official PyTorch implementation of the paper **"Enhanced Deep Residual Networks for Single Image Super-Resolution"** from **CVPRW 2017, 2nd NTIRE**.
You can find the original code and more information from [here](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304698c4af085f5638feb365a47ddc11a058765b210cf3b562287071ba5b12ea1ecc).

If you find our work useful in your research or publication, please cite our work:

[1] Bee Lim, Sanghyun Son, Heewon Kim, Seungjun Nah, and Kyoung Mu Lee, **"Enhanced Deep Residual Networks for Single Image Super-Resolution,"**  2nd NTIRE: New Trends in Image Restoration and Enhancement workshop and challenge on image super-resolution in conjunction with **CVPR 2017**.   [[PDF](http://u.720life.cn/g/577cd4b2d7ef7d399cb67064e43f84df9b5ca1d884abc1efc636b6ad1debb9afd6609bbf7b2d6d0dd307c3cf171d305676648d31b653031956f78e55bdeff5ef6f9df25cfb7cef510c5607c75415b3fc78ca189ae029ca1047405e09dec79c364a77830679153d91ecef569dba596e72b4d5c0d25b743526a956bd13ca31d122)] [[arXiv](http://u.720life.cn/g/ef50ff7c3b5c85de9d07d6f28fa0575478f1d3ebab994a7cc0ad5bf00391f684)] [[Slide](http://u.720life.cn/g/51fe35ccfa24a89b1ec2d68c4c1c57f4a0c4b52f12a360532210a4745039efad6900632ac7e5f541ac133123d39699290840498ee2cc66b0950080993801cbb3).pptx
```
@InProceedings{Lim_2017_CVPR_Workshops,
  author = {Lim, Bee and Son, Sanghyun and Kim, Heewon and Nah, Seungjun and Lee, Kyoung Mu},
  title = {Enhanced Deep Residual Networks for Single Image Super-Resolution},
  booktitle = {The IEEE Conference on Computer Vision and Pattern Recognition (CVPR) Workshops},
  month = {July},
  year = {2017}
}
```
We provide scripts for reproducing all the results from our paper. You can train your model from scratch, or use a pre-trained model to enlarge your images.

**Differences between Torch version**
* Codes are much more compact. (Removed all unnecessary parts.)
* Models are smaller. (About half.)
* Slightly better performances.
* Training and evaluation requires less memory.
* Python-based.

## Dependencies
* Python 3.6
* PyTorch >= 1.0.0
* numpy
* skimage
* **imageio**
* matplotlib
* tqdm
* cv2 >= 3.xx (Only if you want to use video input/output)

## Code
Clone this repository into any place you want.
```bash
git clone https://github.com/thstkdgus35/EDSR-PyTorch
cd EDSR-PyTorch
```

## Quickstart (Demo)
You can test our super-resolution algorithm with your images. Place your images in ``test`` folder. (like ``test/ ``) We support **png** and **jpeg** files.

Run the script in ``src`` folder. Before you run the demo, please uncomment the appropriate line in ```demo.sh``` that you want to execute.
```bash
cd src       # You are now in */EDSR-PyTorch/src
sh demo.sh
```

You can find the result images from ```experiment/test/results``` folder.

| Model | Scale | File name (.pt) | Parameters | ****PSNR** |
|  ---  |  ---  | ---       | ---        | ---  |
| **EDSR** | 2 | EDSR_baseline_x2 | 1.37 M | 34.61 dB |
| | | *EDSR_x2 | 40.7 M | 35.03 dB |
| | 3 | EDSR_baseline_x3 | 1.55 M | 30.92 dB |
| | | *EDSR_x3 | 43.7 M | 31.26 dB |
| | 4 | EDSR_baseline_x4 | 1.52 M | 28.95 dB |
| | | *EDSR_x4 | 43.1 M | 29.25 dB |
| **MDSR** | 2 | MDSR_baseline | 3.23 M | 34.63 dB |
| | | *MDSR | 7.95 M| 34.92 dB |
| | 3 | MDSR_baseline | | 30.94 dB |
| | | *MDSR | | 31.22 dB |
| | 4 | MDSR_baseline | | 28.97 dB |
| | | *MDSR | | 29.24 dB |

*Baseline models are in ``experiment/model``. Please download our final models from [here](http://u.720life.cn/g/51fe35ccfa24a89b1ec2d68c4c1c57f4a0c4b52f12a360532210a4745039efad8dd609f343bdd588b8c9757ff9823b0378fe368c2a20c75bff5e590d3646a032) (542MB)
**We measured PSNR using DIV2K 0801 ~ 0900, RGB channels, without self-ensemble. (scale + 2) pixels from the image boundary are ignored.

You can evaluate your models with widely-used benchmark datasets:

[Set5 - Bevilacqua et al. BMVC 2012](http://u.720life.cn/g/26bfdb888e2e888091ae8ef0cd15c2353560406b9572cd7cc3f501eb47e4129a971f35a8dd742284d0bfe01afcc4f4e280715faf886586d64b01909b1fafd0ab),

[Set14 - Zeyde et al. LNCS 2010](http://u.720life.cn/g/d72954bcd0c43e872cfb84cc946f6d0c68c864516ffa665dcd998b8bc47810040772d4d040149846299e2ca861ba6b5cf5110d2e00e266947dd91d41da62df9b),

[B100 - Martin et al. ICCV 2001](http://u.720life.cn/g/2575034c673e1f403f4a4dcf305f3c77eaa4a38c5ea594776abbc4275fdb78f110748f48cfad11bdcaf0d2037d7281a90d744958b632817ae603203f5d9e7e09),

[Urban100 - Huang et al. CVPR 2015](http://u.720life.cn/g/d72954bcd0c43e872cfb84cc946f6d0cf1801bd7437edf056f4f331bb453c53397c76864d2dd95c1fe95abeb46a2e2bf880390a0e786abebc2b7953411e11d9b).

For these datasets, we first convert the result images to YCbCr color space and evaluate PSNR on the Y channel only. You can download [benchmark datasets](http://u.720life.cn/g/51fe35ccfa24a89b1ec2d68c4c1c57f4a0c4b52f12a360532210a4745039efad621488aaaa29ffa949c8effb337d9d4d) (250MB). Set ``--dir_data  `` to evaluate the EDSR and MDSR with the benchmarks.

You can download some results from [here](http://u.720life.cn/g/51fe35ccfa24a89b1ec2d68c4c1c57f4a0c4b52f12a360532210a4745039efad25a75dc1672fff40f7a156a7711fa637f0eec9fab0eada1675b74997e23ecb1b).
The link contains **EDSR+_baseline_x4** and **EDSR+_x4**.
Otherwise, you can easily generate result images with ``demo.sh`` scripts.

## How to train EDSR and MDSR
We used [DIV2K](http://u.720life.cn/g/d518791066927ec6940c247f22623a659d61d2ecf6000b4d9fd7690789dac7dc8fa639febf21cb5e491b16c423099edd3867d17be0c4f7dcda43f46e4b0f339ba72c047f7a80a114c6a6df5bf81c7803) dataset to train our model. Please download it from [here](http://u.720life.cn/g/51fe35ccfa24a89b1ec2d68c4c1c57f4a0c4b52f12a360532210a4745039efad909fa58029f9f205b72237e72c4f01ab) (7.1GB).

Unpack the tar file to any place you want. Then, change the ```dir_data``` argument in ```src/option.py``` to the place where DIV2K images are located.

We recommend you to pre-process the images before training. This step will decode all **png** files and save them as binaries. Use ``--ext sep_reset`` argument on your first run. You can skip the decoding part and use saved binaries with ``--ext sep`` argument.

If you have enough RAM (>= 32GB), you can use ``--ext bin`` argument to pack all DIV2K images in one binary file.

You can train EDSR and MDSR by yourself. All scripts are provided in the ``src/demo.sh``. Note that EDSR (x3, x4) requires pre-trained EDSR (x2). You can ignore this constraint by removing ```--pre_train  ``` argument.

```bash
cd src       # You are now in */EDSR-PyTorch/src
sh demo.sh
```

**Update log**
* Jan 04, 2018
  * Many parts are re-written. You cannot use previous scripts and models directly.
  * Pre-trained MDSR is temporarily disabled.
  * Training details are included.

* Jan 09, 2018
  * Missing files are included (```src/data/MyImage.py```).
  * Some links are fixed.

* Jan 16, 2018
  * Memory efficient forward function is implemented.
  * Add --chop_forward argument to your script to enable it.
  * Basically, this function first split a large image to small patches. Those images are merged after super-resolution. I checked this function with 12GB memory, 4000 x 2000 input image in scale 4. (Therefore, the output will be 16000 x 8000.)

* Feb 21, 2018
  * Fixed the problem when loading pre-trained multi-GPU model.
  * Added pre-trained scale 2 baseline model.
  * This code now only saves the best-performing model by default. For MDSR, 'the best' can be ambiguous. Use --save_models argument to keep all the intermediate models.
  * PyTorch 0.3.1 changed their implementation of DataLoader function. Therefore, I also changed my implementation of MSDataLoader. You can find it on feature/dataloader branch.

* Feb 23, 2018
  * Now PyTorch 0.3.1 is a default. Use legacy/0.3.0 branch if you use the old version.
  * With a new ``src/data/DIV2K.py`` code, one can easily create new data class for super-resolution.
  * New binary data pack. (Please remove the ``DIV2K_decoded`` folder from your dataset if you have.)
  * With ``--ext bin``, this code will automatically generate and saves the binary data pack that corresponds to previous ``DIV2K_decoded``. (This requires huge RAM (~45GB, Swap can be used.), so please be careful.)
  * If you cannot make the binary pack, use the default setting (``--ext img``).

  * Fixed a bug that PSNR in the log and PSNR calculated from the saved images does not match.
  * Now saved images have better quality! (PSNR is ~0.1dB higher than the original code.)
  * Added performance comparison between Torch7 model and PyTorch models.

* Mar 5, 2018
  * All baseline models are uploaded.
  * Now supports half-precision at test time. Use ``--precision half``  to enable it. This does not degrade the output images.

* Mar 11, 2018
  * Fixed some typos in the code and script.
  * Now --ext img is default setting. Although we recommend you to use --ext bin when training, please use --ext img when you use --test_only.
  * Skip_batch operation is implemented. Use --skip_threshold argument to skip the batch that you want to ignore. Although this function is not exactly the same with that of Torch7 version, it will work as you expected.

* Mar 20, 2018
  * Use ``--ext sep-reset`` to pre-decode large png files. Those decoded files will be saved to the same directory with DIV2K png files. After the first run, you can use ``--ext sep`` to save time.
  * Now supports various benchmark datasets. For example, try ``--data_test Set5`` to test your model on the Set5 images.
  * Changed the behavior of skip_batch.

* Mar 29, 2018
  * We now provide all models from our paper.
  * We also provide ``MDSR_baseline_jpeg`` model that suppresses JPEG artifacts in the original low-resolution image. Please use it if you have any trouble.
  * ``MyImage`` dataset is changed to ``Demo`` dataset. Also, it works more efficient than before.
  * Some codes and script are re-written.

* Apr 9, 2018
  * VGG and Adversarial loss is implemented based on [SRGAN](http://u.720life.cn/g/577cd4b2d7ef7d399cb67064e43f84df9b5ca1d884abc1efc636b6ad1debb9af94772efad79656aceec22b067f23cfe0bb5494f2917227540d5192b5e1f04033bcee3ec23a70d93cee29bca99b1167cd3a6d4b23137085cdef2c50a5758a2bd072d60837e70cffa854e7a7a6a7c6cda3). [WGAN](http://u.720life.cn/g/ef50ff7c3b5c85de9d07d6f28fa057541ce5a22ffe59d3f62df8840f5dc55aaf) and [gradient penalty](http://u.720life.cn/g/ef50ff7c3b5c85de9d07d6f28fa05754393fa638bec25463b2889c0eae2a04a6) are also implemented, but they are not tested yet.
  * Many codes are refactored. If there exists a bug, please report it.
  * [D-DBPN](http://u.720life.cn/g/ef50ff7c3b5c85de9d07d6f28fa05754bb00ffd53bcecd68b4185fb61e63a474) is implemented. The default setting is D-DBPN-L.

* Apr 26, 2018
  * Compatible with PyTorch 0.4.0
  * Please use the legacy/0.3.1 branch if you are using the old version of PyTorch.
  * Minor bug fixes

* July 22, 2018
  * Thanks for recent commits that contains RDN and RCAN. Please see ``code/demo.sh`` to train/test those models.
  * Now the dataloader is much stable than the previous version. Please erase ``DIV2K/bin`` folder that is created before this commit. Also, please avoid using ``--ext bin`` argument. Our code will automatically pre-decode png images before training. If you do not have enough spaces(~10GB) in your disk, we recommend ``--ext img``(But SLOW!).

* Oct 18, 2018
  * with ``--pre_train download``, pretrained models will be automatically downloaded from the server.
  * Supports video input/output (inference only). Try with ``--data_test video --dir_demo [video file directory]``.

* About PyTorch 1.0.0
  * We support PyTorch 1.0.0. If you prefer the previous versions of PyTorch, use legacy branches.
  * ``--ext bin`` is not supported. Also, please erase your bin files with ``--ext sep-reset``. Once you successfully build those bin files, you can remove ``-reset`` from the argument.



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ed5aede1a981bb7fec5d159e055e7a8b0d3a9b5811a339cbf178b7cbb934685694caa86fe333d9a07d495251c4b368002)