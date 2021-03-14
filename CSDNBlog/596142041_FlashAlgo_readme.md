# FlashAlgo

## Development Setup
Skip any step where a compatible tool already exists

1. Install [Python 2.7.9](http://u.720life.cn/g/74e7b7c595201f48e3f4da7562c1a8265391d71b10b58cef78feb3ff65d1b8966dc22455cc7c97d787bf148175bbaa2b) and make sure it's added to path
2. Install [Git](http://u.720life.cn/g/0699e533b96232c5e210af6ab5668134ed44df5470ba28d42680a763bb9722c5) and make sure it's added to path
3. Install [Keil MDK-ARM](http://u.720life.cn/g/05be8b665dd31cba14c251ab6c51d09012ce581695db9ff4d0046423bf68e0bd3dfc7cf7c4428a30e2652a4289d611ad)
4. Install virtualenv in python

```
> git clone https://github.com/mbedmicro/FlashAlgo
> pip install virtualenv
> virtualenv venv
>
```

## Develop
1. Update tools and generate project files. This should be done everytime you pull new changes

```
> "venv/Scripts/activate"
> pip install -r requirements.txt
> progen generate -t uvision
> "venv/Scripts/deactivate"
```


```
> cd tools
> launch_uvision.bat

```
Now open the project file for the desired target in \projectfiles\uvision\ \

To change the RAM base address to something other than the default value of 0x20000000, add the argument  --blob_start 0x[RAM ADDRESS] in Projects...Options...User...After Build/Rebuild section of the uVision project.


## Adding a new project
For adding new targets start from template and use these docs...

## Contribute
Check out the issue tracker.

##ToDo
- Create a test
- Document how to use
- Document how to contribute



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e3eb25ff5818a4fd2692bc25ea430095edbf3c980077968affc6da18ce5b40edf7075058a0ff16c6be73cb68d2867516c)