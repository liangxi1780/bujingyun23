# RetrofitUrlManager
[ ![Jcenter](https://img.shields.io/badge/Jcenter-v1.4.0-brightgreen.svg?style=flat-square) ](https://bintray.com/jessyancoding/maven/retrofit-url-manager/1.4.0/link)
[ ![Build Status](https://travis-ci.org/JessYanCoding/RetrofitUrlManager.svg?branch=master) ](https://travis-ci.org/JessYanCoding/RetrofitUrlManager)
[ ![Android Arsenal](https://img.shields.io/badge/Android%20Arsenal-RetrofitUrlManager-brightgreen.svg?style=flat-square) ](https://android-arsenal.com/details/1/6007)
[ ![API](https://img.shields.io/badge/API-9%2B-blue.svg?style=flat-square) ](https://developer.android.com/about/versions/android-2.3.html)
[ ![License](http://img.shields.io/badge/License-Apache%202.0-blue.svg?style=flat-square) ](http://www.apache.org/licenses/LICENSE-2.0)
[ ![Author](https://img.shields.io/badge/Author-JessYan-orange.svg?style=flat-square) ](https://www.jianshu.com/u/1d0c0bc634db)
[ ![QQ-Group](https://img.shields.io/badge/QQ%E7%BE%A4-455850365%20%7C%20301733278-orange.svg?style=flat-square) ](https://shang.qq.com/wpa/qunwpa?idkey=7e59e59145e6c7c68932ace10f52790636451f01d1ecadb6a652b1df234df753)

## Let Retrofit support multiple baseUrl and can be change the baseUrl at runtime.

[中文说明](README-zh.md)

## Overview
![overview](art/overview.gif)

## Notice
[**Framework analysis 1**](http://u.720life.cn/g/edab4f07812b57c7ea69fa7b67a55e9e60e02a9bd7b39ba180ea515f2bd47237732c3713242049f4b3c47f7c3d40cf7f)

[**Framework analysis 2**](http://u.720life.cn/g/8a0e6e781ca1335d5641e0f9d5e96ab9df53ec71eb91b17223a3b641d1d6205ce4fb55afff6c86747d0db9209537a4d2)

[**More complete sample**](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046ca54ad6f2e0fdef014e30c128c67d9a2abe960c67c4c8b41929e5f4a21207c14)

## Download
``` gradle
 implementation 'me.jessyan:retrofit-url-manager:1.4.0'
```

## Usage
### Initialize
``` java
 // When building OkHttpClient, the OkHttpClient.Builder() is passed to the with() method to initialize the configuration
 OkHttpClient = RetrofitUrlManager.getInstance().with(new OkHttpClient.Builder())
                .build();
```

### Step 1
``` java
 public interface ApiService {
     @Headers({"Domain-Name: douban"}) // Add the Domain-Name header
     @GET("/v2/book/{id}")
     Observable  getBook(@Path("id") int id);
}

```

### Step 2
``` java
 // You can change BaseUrl at any time while App is running (The interface that declared the Domain-Name header)
 RetrofitUrlManager.getInstance().putDomain("douban", "https://api.douban.com");
```

### If you want to change the global BaseUrl:
```java
 // BaseUrl configured in the Domain-Name header will override BaseUrl in the global setting
 RetrofitUrlManager.getInstance().setGlobalDomain("your BaseUrl");

```

## About Me
* **Email**:  
* **Home**:  
* **掘金**:  
* **简书**:  

## License
```
 Copyright 2017, jessyan

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

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e35c2691431860a1473c5a3fda19e7af0f8cffaf9927e9dadaf500f12cc168153bcdaf9f5c8c8bb42fa08fc45fd9bfb0e3becf1494d4594e5a3b1888e4aabb6b6)