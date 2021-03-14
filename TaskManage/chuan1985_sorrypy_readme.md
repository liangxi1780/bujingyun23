# sorrypy

`sorry有钱真的可以为所欲为`

## 说明

[sorry](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046029ccb8566c157b2a534c69252db1574)是一款很有意思的应用，源自于`sorry有钱真的可以为所欲为`这个梗。
亮点是可以换自己的梗生成gif。
可惜部署环境是ubuntu+ruby，我就重制了个全平台的python重置版博大家一笑。
荣誉首先属于[xtyxtyx](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046c0bd2a41af42d33ae39342508577e365)

__[Hardy兄弟](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046033c8997a194942c990a6e7eb61c29f5)的[NodeJs版:node-sorry]https://github.com/q809198545/node-sorry

`sorry客户真的可以为所欲为`样例：

![](static/cache/sorry-703a480ff26b72c4b2d2cc195b765f35.gif)

## 部署
1. 下载安装[python3](http://u.720life.cn/g/74e7b7c595201f48e3f4da7562c1a8265391d71b10b58cef78feb3ff65d1b8966dc22455cc7c97d787bf148175bbaa2b)
2. cmd命令行安装必须包
`
pip install flask pillow imageio ffmpeg-python moviepy
`
当然也可以
`
pip install -r req.txt
`
3. 安装ffmpeg
[ffmepg官网](http://u.720life.cn/g/08a8721494911cd8408a11af9e278b23720a1c27d619ab32a9624d939a4f3726)下载安装ffmepg并加入path。
检验ffmpeg安装
```
ffmpeg -version
```
尽量使用3.4以上版本，低版本可能会`无法生成`或者`生成无字幕gif`。
4. cmd中运行
```
python app.py
```
5. 浏览器打开
[http://127.0.0.1:8000/](http://u.720life.cn/g/8bd8603eb20ab01233f1f6fdd61cc4fd9fa76974b0e732d1efeff6aca7f952da)
然后你就可以为所欲为了~~~

### CentOS7下ffmpeg安装
```
wget https://ffmpeg.org/releases/ffmpeg-3.4.2.tar.bz2
yum -y install bzip2
yum -y install yasm
yum -y install libass libass-devel
tar -xf ffmpeg-3.4.2.tar.bz2
cd ffmpeg-3.4.2
./configure --enable-libass
make
make install
```
### Windows下ffmpeg安装
方便起见，已直接将最新版ffmpeg.exe放入项目根目录，所以无需下载。
如果需要全局使用ffmpeg，可参考[这篇文章](http://u.720life.cn/g/ce3f6174933242f367d8a4cd3fa79ded4eb974fdc7bc47d45917d583a4e06d235e2bd65785363148227797fe7c9e383d8e23adb5b93b38cd2a100fec39b8bf84)

## 适配新Gif
目前，想要适配新的gif,需要改动3个文件（修改前建议备份）
```
templates/sorry/index.html
static/sorry/template.mp4
static/sorry/template.tpl
```
其中
```
index.html  按照句子的多少删掉或者增加 即可
template.mp4   替换成新视频
template.tpl   替换成新的字幕模板
```

### 字幕模板template.tpl
首先使用aegisub为模板视频创建字幕，保存为sorry.template.ass

>[aegisub教程](http://u.720life.cn/g/3356c5ec92373703d98a93187ff778793b680e22f6dcb2acbee1cc0e74e97d4e7bdc3d5d07596788dcf73038b4d34c00)

![图片](https://dn-coding-net-production-pp.qbox.me/56a213df-9ff7-41e0-9b6c-96b1f0fe2cb6.png)

然后把文本替换成模板字符串 ```{{ sentences[n] }}``` 懒得换图了哈，以这个字符串为准

![图片](https://dn-coding-net-production-pp.qbox.me/6b07bc65-c3d7-4251-aad2-bd7b05af9102.png)

最后保存为template.tpl

现在这个网站就可以制作新的gif了

## Note
欢迎 `star` ~ `fork` ~~

[Github](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046fe849219d30359b5e4cabf4405a4e4a70618576e526244653f3478e6c092516e) & [码云](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e70b319e51e271b87934e114f93993d417f88a871d6dd220fc648b7b470b784ac)



## TODO
- [ ] 加入锁机制限制并发
- [ ] 自动生成页面



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e105b633744678980e21b640decc829a7fea6f8e5b97dc2ecf135a3c299c213af0318a221655aaebf8c7db3383e62e792)