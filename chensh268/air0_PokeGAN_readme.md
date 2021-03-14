# PokeGAN

**Goal: Trying to use a GAN to produce new Pokemon**

This is actually much more complicated than I had originally thought, but I have gotten some results! Not sure if they can be classified as Pokemon, but they are something. Next time, I will be implementing my own GAN from scratch to hopefully reach much better results, especially with RGB images.


### Data (Pokemon images)
I scraped all the Pokemon images from an online Pokemon [Pokedex](http://u.720life.cn/g/e1fb4420590d1f4cd96bf4b178838f9fbe9cd7b051c5e8a4b9b5ba399ccc8c66), which allowed for indexing of the Pokemon by number instead of just by name, which made it much easier to get the data. All images are saved within the [Pokemon](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046de92b65b9e9b3a5411fc3f672755764621da89e37e3d440b428fe4e4b1c7d330122b10698fec4a3d79fd0298c57da4a1) folder, for easier access. Due to the small number of available Pokemon (~900), there really is not much data available, thus something simple I did was to do some image augmentation, where I ended up with a few thousand images. This is still no where near the amount used for example in MNIST, but it helped.


### Code
The code is based on implementations from Hyeonwoo Kang's [GAN repo](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046ee0e6437b0807514435a7a657e1c63bdd634d5c8d9c74265962921622ced6c2c57c6a41ad7c7bd660aaf1f6b34a218be), which I modified for the Pokemon, and to run on Jupyter Notebook, for easier testing/modification.


### First Attempt
In this first attempt, I tried to use 128x128 RGB images of Pokemon, and without tweaking any of the original GAN parameters as of Kang's implementation. However I cannot understand exactly what is making it generate images which seem to be missaligned between the RGB layers. I believe that this is happening within the model due to input shape differences between my inputs and the ones used by Kang, which would also explain the bad training, and thus no real generation.
     

### Final Results (most pokemon like)
There were a lot of different attempts made at training with RGB images, with different input sizes, learning rates, network dimensions, however most results were quite terrible, thus I turned the images to grayscale, to flatten their shape. Using the grayscale images, another whole lot of tests were made, where the following are the best results, where some of the images actually look like Pokemon, or at least have features (body curvatures, wings, arms, tails) which resamble a Pokemon.
    
 
 



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ee1564d7c62d9c2540e8a78a6711ab4b91bfaf3b0f540ce7e867b043bdc473698b7110ba87b7cbfe2bd9232d4ee14e52a)