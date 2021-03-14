Android-Bootstrap
=================
Android Bootstrap is an Android library which provides custom views styled according to the
 [Twitter Bootstrap Specification](http://u.720life.cn/g/e23be2821e5181a1a46a005bc6e93d9dc1c8dad0ef41593aa593e12a30fc455b). This allows you to spend more time
  on development rather than trying to get a consistent theme across your app, especially if you are already familiar with the Bootstrap Framework.
  
Quick Start
===========
 [![Maven Central](https://maven-badges.herokuapp.com/maven-central/com.beardedhen/androidbootstrap/badge.svg)](https://maven-badges.herokuapp.com/maven-central/com.beardedhen/androidbootstrap)
 [![CircleCI](https://circleci.com/gh/Bearded-Hen/Android-Bootstrap/tree/develop.svg?style=shield)](https://circleci.com/gh/Bearded-Hen/Android-Bootstrap/tree/develop)
    
 
 Add the following dependency to your build.gradle, ensuring you replace 'X.X.X' with the latest version on the button above:
 
 ```java
 dependencies {
    compile 'com.beardedhen:androidbootstrap:{X.X.X}'
 }
 ```
 
 You should also override your application class with the following:
 
 ```java
 public class SampleApplication extends Application {
     @Override public void onCreate() {
         super.onCreate();
         TypefaceProvider.registerDefaultIconSets();
     }
 }
 ```
 
 You should then checkout the library and investigate the sample code, which covers most of the features.
 The sample app is also available on [Google Play](http://u.720life.cn/g/b77c9812b4c231c9db5ffbe20c7ac4514598fe0c0eef619f1c2864cffe959e0ac4bfabb522b5eac23c168265b1e7fafa52eb5b2c05beaa4b24e1f725f01ba43b143984e7700767cb0e6490d256fc1061eee40e6d9f4c7335ece56c5f991f0994).
 
Support
==============
If you have a question about how to use the project, please ask a question on [StackOverflow](http://u.720life.cn/g/ddb1c8aa997182cb1a4af16f7df394520a2863231ad8d7352308cd295ccf0ae9cc764b76854ee8ddaed2703cae8990062c111cd33d13d2fdeda7753bc7c1d07b828433fc902d566b99f3863042ba4e8d), using the tag **android-bootstrap-widgets**.

If you think you have found a bug in the library, you should [create a new issue](http://u.720life.cn/g/54145d0471d91890860f7f8463c030468aa98575443bfb644aca556773550214ec4759b5fd9899c0d390b835504a93747223854a7483750fdc981c04180f2dd9) instead.
 
Javadoc
============
The javadoc for the project is hosted on [Github](http://u.720life.cn/g/8087d48a1a88c6c9fdb606b8988a190a2a5dd3e762b94d794d96d048cc73c7b7760918b0449c5530648a20f03e235171).

Examples
============

### BootstrapButton
A button that supports Glyph icons, and is themeable using Bootstrap Brands.
   ```xml
 
```
 

###BootstrapButtonGroup
Allows BootstrapButtons to be grouped together and their attributes controlled en masse.
   ```xml
 
     
     
 
```
 


### AwesomeTextView
A text widget that displays Glyph icons, and is themeable using Bootstrap Brands.
   ```xml
 
```
 

###BootstrapProgressBar
Displays progress in a bar from 0-100, and animates updates to the current progress.
   ```xml
 
```
 

### BootstrapProgressBarGroup
Allows BootstrapProgressBars to be group together to have the effect of  stacked progress bar .
   ```xml
         

             

             

             
```
 

###BootstrapLabel
Displays non-clickable text in a widget similar to the BootstrapButton, sizable using H1-H6 elements.
   ```xml
 
```
 

### BootstrapEditText
Allows editing of text in a widget themed using BootstrapBrand.
   ```xml
 
```
 

###BootstrapCircleThumbnail
Displays images in a center-cropped Circular View, themed with BootstrapBrand.
   ```xml
 
```
 

### BootstrapThumbnail
Displays images in a rectangular View, themed with BootstrapBrand.
   ```xml
 
```
 

###BootstrapWell
Displays a view in a themed container.

```xml
 

         
     
```
 


###BootstrapDropDown
Displays a view with dropdown options, supplied by an array of strings.

```xml
 
```
 

 Custom Styles
============
Custom styles can be applied to any of the views in this library by creating a class which implements
BootstrapBrand, and setting it on the View. Please see the sample code of BootstrapButton for more detail.

 ```java

     class CustomBootstrapStyle implements BootstrapBrand {
         // specify desired colors here
     }

     BootstrapButton btn = new BootstrapButton(context);
     btn.setBootstrapBrand(new CustomBootstrapStyle(this);
 ```




Contributing
============
Contributions are very welcome! There are 3 main ways you can help out:

1. Add more Icon Typefaces, using the instructions [here](http://u.720life.cn/g/54145d0471d91890860f7f8463c030468aa98575443bfb644aca556773550214ec4759b5fd9899c0d390b835504a9374ede6ae978e444219a6aa06364fac8d44be9011c479ee653c788ff75c5b212e12)
2. Help implement views which are present in the  [Twitter Bootstrap Specification](http://u.720life.cn/g/e23be2821e5181a1a46a005bc6e93d9dc1c8dad0ef41593aa593e12a30fc455b) but are not yet in this library.
3. Raise an issue if you see a bug or are unsure on how something works, or even better - send a pull-request with a fix!

Versioning
==========
This project uses [Semantic Versioning](http://u.720life.cn/g/73cc764475678a131c8c04bf7ecaf2f9b3df6eef37d23622ec7cbefc327c2e6c). There are several breaking changes in V2.X of the library, including:

- AwesomeTextView replaces FontAwesomeText
- Various altered method signatures/attributes for views
- Global BootstrapBrand/BootstrapSize attributes replace view-specific enums

Please consider what effect these changes might have on your app before upgrading!

Contact
=======
If you have any questions, issues, or just want to let us know where you're using Android Bootstrap
 tweet us at [@BeardedHen](http://u.720life.cn/g/5ea88169c4a0fbd169233d52478d54fe154bf02cb4de539d0000998d060ffbba), email support@beardedhen.com,
  or head over to our [website](http://u.720life.cn/g/a23fec4e0e9a2113531a01bf857d3a0ca7cb9bb2c6da5f3d315f3a1910b1634a) to see more of our creations.

Hall of Fame
======
Checkout [AppBrain](http://u.720life.cn/g/451e6ee67fdbef49a3a5eecf952b460c75fb3fed1a7212f933a6adf0fecc939ead08d4ba99393f3bd7c6a9e878630a46f85ac922c32c35ae13e62855e16570baa6c3b4768d85b7e590607b5c56573afa34c6a0bb3eb20227ef7fe4b4f762736b) to see some of the apps which use Android Bootstrap!




 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ea72a5392b96fa6459d0c4beeaf5c4d07dbe94e6d556502f8fa33895d94a2ea360bbcd01f03175d6c82f492101e142a6a)