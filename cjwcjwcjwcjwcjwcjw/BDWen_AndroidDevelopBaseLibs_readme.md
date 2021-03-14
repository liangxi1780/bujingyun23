安卓开发基础库，包含强大的工具库，recyclerview万能适配器，butterknife，UI库qmui，网络请求OKGO，图片视频选择库，图片加载库，JSON解析库FASTJSON等等在开发中都会用到的库

# 该库所集合的开源库有如下，还有自己做了简单封装的BaseActivity，BaseFragment，不需要的可自行删除

```
dependencies {
    api 'com.android.support:recyclerview-v7:27.1.1'
    //design库
    api 'com.android.support:design:27.1.1'

    //UI库http://qmuiteam.com/android/get-started/
    api 'com.qmuiteam:qmui:1.1.3'

    //recyclerview设配器https://github.com/CymChad/BaseRecyclerViewAdapterHelper
    api 'com.github.CymChad:BaseRecyclerViewAdapterHelper:2.9.40'

    //工具库https://github.com/Blankj/AndroidUtilCode
    api 'com.blankj:utilcode:1.17.3'

    //布局注入库https://github.com/JakeWharton/butterknife
    api 'com.jakewharton:butterknife:8.8.1'
    annotationProcessor 'com.jakewharton:butterknife-compiler:8.8.1'

    //网络请求库https://github.com/jeasonlzy/okhttp-OkGo
    api 'com.lzy.net:okgo:3.0.4'

    //图片加载库
    api 'com.github.bumptech.glide:glide:4.7.1'
    annotationProcessor 'com.github.bumptech.glide:compiler:4.7.1'

    //https://github.com/H07000223/FlycoTabLayout
    api 'com.flyco.tablayout:FlycoTabLayout_Lib:2.1.2@aar'

    //下拉刷新库https://gitee.com/BDWen/SmartRefreshLayout
    compile 'com.scwang.smartrefresh:SmartRefreshLayout:1.0.3'

    //图片视频选择库https://github.com/LuckSiege/PictureSelector
    compile 'com.github.LuckSiege.PictureSelector:picture_library:v2.2.3'

    //fastjson(json解析)https://github.com/alibaba/fastjson/wiki/Quick-Start-CN
    compile 'com.alibaba:fastjson:1.2.9'

}
```


# 使用
### 1.这是一个module，下载后直接在项目中引用
```
compile project(':Base')
```
### 2.在项目的build.gradle中添加下面代码

```
buildscript {
    
    repositories {
        google()
        jcenter()
    }
    dependencies {
        classpath 'com.android.tools.build:gradle:3.0.0'
        classpath 'com.jakewharton:butterknife-gradle-plugin:8.4.0'

        // NOTE: Do not place your application dependencies here; they belong
        // in the individual module build.gradle files
    }
}

allprojects {
    repositories {
        google()
        jcenter()
        maven { url "https://jitpack.io" }
    }
}
```
### 3.最后点击右上角的sync now就可以愉快的使用了


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e81d610c96daa756fa2f98fcc64bb971669238126b077a348bc64f77c34e7580eb7234d6d53422bd94741e6478f450621fdc16e512fc1b3e81510c33310f99ddb)