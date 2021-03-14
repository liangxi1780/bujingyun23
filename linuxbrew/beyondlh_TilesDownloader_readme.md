#TilesDownloader

# QQ交流群: 106802648

> 百度地图用这个: GMapProviders.BaiduMap
> 谷歌地图无偏移: GMapProviders.GoogleSatelliteMap
> 谷歌地图有偏移: GMapProviders.GoogleChinaSatelliteMap

## 百度地图核心代码就3个

> BaiduMapProvider.cs
> BaiduProjection.cs
> BaiduSateliteMapProvider.cs

# [打开看看](http://u.720life.cn/g/5c954f4cd4204fb6c09a7e58aa70844daa66b9f9b3e209b6e8200ebdc8d31cb58e30187516d52242edb70f84220d8d437376188add3fcae54a64f1cfeb0eaded30689ef449f0211fa17b48f85ce56da2aa21810904136329df9147ac3043083dd2de85cf6c8a0c55850c3727d8ac756e30d5891dc18e76b1d50217afe03c2d87109a11a1b1bcb7f9c97ae52d4d6455e6433a03f878341ca7d9be7c9c790f871856434b9e343dac87f9bb12f499dea83c0a0f3cfca38b16f6f137b68ba372a442)

# 谷歌地图无偏移有2个有效的URL分别是(无偏移)

> URL1. http://mt1.google.cn/vt/lyrs=s&hl=en&x={0}&y={1}&z={2}
> URL2. http://khm1.google.com/kh/v={version}&hl=en&x={0}&y={1}&z={2}
>
> 例如1: http://mt1.google.cn/vt/lyrs=s&hl=en&x=105378&y=56408&z=17     例如2: http://khm1.google.com/kh/v=699&hl=en&x=105378&y=56408&z=17    PS: 地址1 自动获取最新的谷歌影像(无偏移)
> PS: 地址2 首先要通过 http://ditu.google.cn/maps/api/js?sensor=false&language=zh-cn 这个网址获取最新的地图版本
>     例如获取的json字符串里的https://khms1.google.com/kh?v=699\u0026hl=zh-CN\u0026gl=CN\u0026
>     最新的地图版本就是699 再把版本填写到URL2的v=后面就可以了
>     地址2 比 地址1 的优势在于可以获取历史版本的谷歌影像 被墙的几率少一点

# [谷歌地图下载脚本](http://u.720life.cn/g/54145d0471d91890860f7f8463c030464cfdd8e3906abe57b4ec911b1f85e7647651c7cd6276cc9a6495677022aed2e9)
> 1. 谷歌地图下载脚本可以批量快速下载谷歌地图
> 2. 并且可以直接导入ArcMAP里浏览
> 3. 可以将零散的瓦片封装成ArcServer的紧凑型bundle文件
> 4. 想了解更多使用方法在QQ群里讨论







 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6eb6c20654c07aa63b7e67da90714ee6e87b944593cf16209dc9217c7396500209d1c26651c5a1c7964445a5fcd26ccb6a)