Android L preview example
=========================

### Description

This project is focused on the sample using the API's new preview version of Android-L, use of transitions, shadows etc...,

![Alt text](https://googledrive.com/host/0B62SZ3WRM2R2VHJFNk1JOWNCbHM)


### UI

This app is aimed to use the new Material Design released at the Google I/0 14, to use the `Material` theme on your app, you only 
have to set the parent of your app style to `@android:style/Theme.Material` or `@android:style/Theme.Material.Light` and `@android:style/Theme.Material.DarkActionBar`.

#### Customize the Color Palette of your app

In the `theme.xml` of the `MainActivity`:

```xml
     
     #3F51B5 
     #303F9F 
     #C5CAE9 
     #FF4081 


     
     
         @color/lollipop_theme_default_primary 
         @color/lollipop_theme_default_primary 
         @color/lollipop_theme_default_primary_dark 
         @color/lollipop_theme_default_accent 
         @color/lollipop_theme_default_accent 
         @color/lollipop_theme_default_primary 

         
         @style/MainActionBar 
         @style/MainActionBarThemeOverlay 


         
         true 

         
         true 

         
         true 

         
         false 

         
         @null 
     
```

[Customizing the material theme](http://u.720life.cn/g/58b0fbecc40e23a9a4e7aad91befad0b5a102f077215dd67c5ad5eceaa5bd9ec8e0bbf8a6ddcb12cded3cdd1aec9ba8c0f99b11d5bf9549c14645185210c4152ce67865680cdfbdbde070cfc3ff4846eaa1d12a1163a43784ad7c291a19f2e30af82efcd2f0caf2b9dc97f14c4f1662f892dc4b23480d38e56c0a778e1cf716723a5cbc6b8d1bd3e12849aaff56976a2e6eac717167c03e8ef4730692586faca3b5a9fe5c60173fffb58fe1a82107d84d53fffe1f39fd6a5137bc386d847db198a47a1d7adbcb439af98616f80e0075aa3bf4fe55ed662f726ed6cf07b0cb0eb)  
     
...
```

```java
        // Configure the FAB button
        int size = getResources().getDimensionPixelSize(R.dimen.fab_size);
        Outline outline = new Outline();
        outline.setOval(0, 0, size, size);
        findViewById(R.id.fab).setOutline(outline);
```

### Activity transitions

Now, with Android-L you can specify custom animations for enter and exit transitions, and for transition of shared elements between activities, to do that, first, you have to enable the window content transitions, in my case, at `themes.xml` you can set this values from java code as well.


```xml
     
        ...
         
         true 

         
         true 

         
         true 

         
         false 

         
         @null 
        ...
     
    
```

```java
        // Setup the transition to the detail activity
        ActivityOptions options =  ActivityOptions.makeSceneTransitionAnimation(MainActivity.this, view, "photo" + i);
        startActivity(detailIntent, options.toBundle());
```


### Tools & References:

- [Android Studio](http://u.720life.cn/g/a69e8f5dba5b4106ccc3875c547b1484974969931b795710d9308a0f4883cbf041c52ac96b7bde3e4a8df573e4daf782ed1a65638a239e1afe0f93154eede3d6)
- [Romain Gui - Google I/O 2014 app] (http://u.720life.cn/g/e5f9977be89d621978eb5f8212e5c196b0dfa4f9e6eece1816c541fd28843818694588b9e5cd21221ebe6e5817a34a9584eb5136747eccdc6a5d44e829d23b3f1138f334f961ddf31fba32d166aa357f)
- [Gradle Please](http://u.720life.cn/g/ce73c03b9eb86c57659a2b9525bd22ff110fa22f19750c1a45f5ad7e375529ac)
- [Random User generator api] (http://u.720life.cn/g/e981b2a1a8128229bb322650855be52fedf8328374563b925b1a8338682d9cc5)
- [Gson] (http://u.720life.cn/g/b1f73db7c3bd88ab3d1af6161318928e3d62acd649e382baa1bf5a2516a76b40f9ac3b645a87861cbf6bc69bcd9dea2a)
- [Gabriel Mariotti] (http://u.720life.cn/g/9a80c621c5861cd7ea1341df511ff6b43192502b48efd9a129915c2dcd445d7a6ca4a3b2329aa0922906823fa00004599a9ad1848ebee6df7f75f28de88e6e89)




 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e9a4354881d686ec15c92a365136187616c2c20578e0269570d0302db0849887fdbffc5117c86404dc38db68d6d43a30127123537a284bbfccf18885646a5b480)