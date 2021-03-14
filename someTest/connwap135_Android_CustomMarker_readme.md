本工程为基于高德地图Android SDK进行封装，实现了三种定义的Marker样式，包括根据2012年各省人口年龄结构数据绘制统计饼图、柱状图以及显示详细信息的例子

##前述：

- [高德官方网站申请key](http://u.720life.cn/g/ab116bb2d8f3340d89c298a1bc6cb3466d0bbe4888e8e82461edc76a6839b7a9e9729560bf6030c59a6bc889c5e5d2ca47b0323225425edf0db5575ff3e8c45f).
- 阅读[参考手册](http://u.720life.cn/g/295f23dffdcd9cda0d5ae893d5e6978bf2cd0010f53746780beac1fe60adf8dc2c485e9f4d248693f9d1b87a1e390e0134184643ec95d8ca93bce8a149067e83).
- 工程基于3D地图2.2.1版本，[基本介绍](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046deedcf12e58111e399b5acc64e77a169d807bb83b0d58326cf71805e8bef3bc2).

##效果图如下：

 * ![Screenshot](https://raw.githubusercontent.com/amapapi/Android_CustomMarker_lib/master/resources/%E9%A5%BC%E5%9B%BE.png)
 * ![Screenshot](https://raw.githubusercontent.com/amapapi/Android_CustomMarker_lib/master/resources/%E6%9F%B1%E7%8A%B6%E5%9B%BE.png)
 * ![Screenshot](https://raw.githubusercontent.com/amapapi/Android_CustomMarker_lib/master/resources/%E4%BF%A1%E6%81%AF%E5%9B%BE.png)

 ##版本更新1.0.0 

 提供了基本的饼图，柱状图和详细显示的Marker样式的绘制
 
 ##下载资源：
 
* [markerlibrary.jar](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046deedcf12e58111e399b5acc64e77a1698c0ae7dd3933c2d6dbe4ad9f6e34265ef4e5b19a609cd9eb727cabbffbeaf68a200b5307b6136de3899b1d89ce15e38167ad8775f877ae4750e5fa6b7d160fce) (library)
* [实例应用](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046deedcf12e58111e399b5acc64e77a1698c0ae7dd3933c2d6dbe4ad9f6e34265ef4e5b19a609cd9eb727cabbffbeaf68a78979523cd7dc4d8ceb7b35d8c06ed44c4bf0242018951cb8575452286be9055) (apk)
* 扫一扫下载应用

![Screenshot](https://raw.githubusercontent.com/qiyy/Android_CustomMarker_lib/master/resources/%E4%BA%8C%E7%BB%B4%E7%A0%81.png)  

 
## 使用方法：
 
+ 1:搭建高德地图 AndroidSDK工程方法见：**[配置方法](http://u.720life.cn/g/f5fbf1788b17d825362c29f15299ab41b4a733121e3b05612e0c6fa2b4008c03dc7d96bb9f68d719305acf3eac099f7c301058ac92b4135613d3bf1b5c993093)**
+  2:接口使用

* 绘制饼图接口

``` java
//获取饼图
				MarkerOptions markerOptions = MarkerOptionsFactory
						.createPieChartMarkerOptions(getApplicationContext(),
								ConstantUtils.latlngs[i],
								ConstantUtils.AGEData[i], colors, 50);
```
								
* 绘制柱状图接口	

``` java							
//获取柱状图
				MarkerOptions markerOptions = MarkerOptionsFactory
						.createBarChartMarkerOptions(getApplicationContext(),
								ConstantUtils.latlngs[i],
								ConstantUtils.AGEData[i], colors, 100);
```	

* 绘制详细信息图接口：

``` java
	MarkerOptions markerOptions = MarkerOptionsFactory
						.createInfoWindowMarkerOptions(getApplicationContext(),
								ConstantUtils.latlngs[i],
								ConstantUtils.names[i],
								ConstantUtils.contents[i], drawable,contentDrawable);	
```									
								


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e7a3a1bfd53aefa9207bf080723edcfaeec4234eb55291ff126a68b48722ca80ef385af5db3c8fbc3af5439909401a5d549d47f73fabc45d08ec15a0afa57ae21)