# CameraCardCropDemo
一个卡片（证件）拍照裁剪框架。

## Gradle

```
compile 'me.zhouzhuo810.cameracardcrop:camera-card-crop:1.0.3'
```

## Features

- Support Android 6.0 permissions.

## What does it look like ?

![image1](https://github.com/zhouzhuo810/CameraCardCropDemo/blob/master/cameracrop2.png)

![image1](https://github.com/zhouzhuo810/CameraCardCropDemo/blob/master/cameracrop1.png)


## Notice

```
card

---------------------
|       width       |
|                   |
|                   |height
|                   |
---------------------
phone
------------------------------------
|                                   |
|                                   |
|                                   |
|                                   |
|                                   |
|      mask                         |
|                                   |
|                width              |
|    ------------------------       |
|    |                       |      |
|    |                height |      | screen height
|    |         rect          |      |
|    |                       |      |
|    ------------------------       |
|                                   |
|                                   |
|                                   |
|                                   |
|                                   |
|            screen width           |
-------------------------------------
CameraConfig.RATIO_WIDTH = card's width
CameraConfig.RATIO_HEIGHT = card's height
CameraConfig.PERCENT_WIDTH = rect'swidth / screen's width
```

## Usage

### step 1. Add Activity in your AndroidManifest.xml file.

```xml
     
     
```

### step 2. Add permissions in your AndroidManifest.xml file.

```xml
     
     
     

     
     
```

### step 3. Example for use.

```java
    public void takePhoto(View v) {
        Intent intent = new Intent(MainActivity.this, CropActivity.class);
        intent.putExtra(CameraConfig.RATIO_WIDTH, 855);
        intent.putExtra(CameraConfig.RATIO_HEIGHT, 541);
        intent.putExtra(CameraConfig.PERCENT_WIDTH, 0.8f);
        intent.putExtra(CameraConfig.MASK_COLOR, 0x2f000000);
        intent.putExtra(CameraConfig.RECT_CORNER_COLOR, 0xff00ff00);
        intent.putExtra(CameraConfig.TEXT_COLOR, 0xffffffff);
        intent.putExtra(CameraConfig.HINT_TEXT, "请将方框对准证件拍照");
        intent.putExtra(CameraConfig.IMAGE_PATH, Environment.getExternalStorageDirectory().getAbsolutePath()+"/CameraCardCrop/"+System.currentTimeMillis()+".jpg");
        startActivityForResult(intent, 0x01);
    }

    @Override
    protected void onActivityResult(int requestCode, int resultCode, Intent data) {
        super.onActivityResult(requestCode, resultCode, data);
        if (resultCode == RESULT_OK) {
            if (requestCode == 0x01) {
                String path = data.getStringExtra(CameraConfig.IMAGE_PATH);
                ivPic.setImageURI(Uri.parse("file://"+path));
            }
        }
    }

```

## Log

- 1.0.3 Fix camera.cancelAutoFocus() Exception after camera.release().
- 1.0.2 Fix flashlight not support bugs.
- 1.0.1 Revise layout size.

## License

```
Copyright © zhouzhuo810

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
```



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e9197ff3e4b1f10e3ac2c9c4b3117d8a6a280d10b17ade934a9881e4f68170caec6fb414985157314b916cb20aa9e87a6)