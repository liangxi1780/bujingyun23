**English | [简体中文](Readme_zh.md)**

     
 Live/VOD P2P Engine for Flutter 
 
   
 

## Features
- Support iOS and Android platform
- Support live and VOD streams over HLS protocol(m3u8)
- Support encrypted HLS stream
- Support cache to avoid repeating the download of TS file
- Very easy to integrate with an existing flutter project
- Support any flutter player
- Efficient scheduling policies to enhance the performance of P2P streaming
- Highly configurable
- Use IP database to group up peers by ISP and regions

## Screenshot
   
 
 
 
   
 
 
   

## Environment Configuration
See [documentation](http://u.720life.cn/g/d3ed257b7d5852e65ffe22afcb927bd8c068e9b0a32804bf85a940a326f7ea100556ef21688ed04065be413e8d597b24)

## Example
```dart
import 'package:flutter/material.dart';
import 'package:video_player/video_player.dart';
import 'package:cdnbye/cdnbye.dart';

// Init p2p engine
_initEngine();

// Start playing video
_loadVideo();

_initEngine() async {
    await Cdnbye.init(
      YOUR_TOKEN,
      config: P2pConfig.byDefault()
    );
}

_loadVideo() async {
    var url = YOUR_STREAM_URL;
    url = await Cdnbye.parseStreamURL(url);           // Parse your stream url
    player = VideoPlayerController.network(url);
    player.play();
}
```

## Obtain Token
See [here](http://u.720life.cn/g/d3ed257b7d5852e65ffe22afcb927bd83db37eaf04a08177c26a3f9e22194309cc8fa9983be72e2369906ebaabb38fc3f131c9ad23e3ce65570c622c14ffe234)

## Consloe
Register your AppId at https://oms.cdnbye.com, where you can view p2p-related information.

## Issue & Feature Request
- If you found a bug, open an issue.
- If you have a feature request, open an issue.

## Related Projects
- [hlsjs-p2p-engine](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046c5f6c551c5ac167ae2130c94c2966ce66ead959523a5f6cf1097cb40765d7568) - Web Video Delivery Technology with No Plugins.
- [ios-p2p-engine](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046d07135bc54330a8831011013f02a79805137e3707bd1a44e9d7888b35d47c7af) -  iOS Video P2P Engine for Any Player.
- [android-p2p-engine](http://u.720life.cn/g/54145d0471d91890860f7f8463c030460d43f7b1fba71d27d22593672d9ab99d03762e386cf151a9b3e97942883517d4) -  iOS Video P2P Engine for Any Player.

## FAQ
We have collected some [frequently asked questions](http://u.720life.cn/g/d3ed257b7d5852e65ffe22afcb927bd8bc868300108bf6ab9f2247fd4fa7bbab). Before reporting an issue, please search if the FAQ has the answer to your problem.

## Contact Us
Email：service@cdnbye.com



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e367818719e3e1ad6d122e5ca1951c2f6d6cfb92749dd32616c703219996c28a337435c16fd6d18441ad31562f13869614268e4ef9bbd3fbc9ddf1dede81adb40)