ViewAnimator
=======

[![API](https://img.shields.io/badge/API-9%2B-green.svg)](https://github.com/florent37/ViewAnimator/tree/master)
[![Android Arsenal](https://img.shields.io/badge/Android%20Arsenal-ViewAnimator-brightgreen.svg?style=flat)](http://android-arsenal.com/details/1/2942)

A fluent Android animation library !

[![png](https://raw.githubusercontent.com/florent37/ViewAnimator/master/montain_small.jpg)](https://github.com/florent37/ViewAnimator)

#Usage

Animate multiple view from one method

```java
ViewAnimator
       .animate(image)
       .translationY(-1000, 0)
       .alpha(0,1)
           
       .andAnimate(text)
       .dp().translationX(-20, 0)
       .interpolator(new DecelerateInterpolator())
       .duration(2000)

       .thenAnimate(image)
       .scale(1f,0.5f,1f)
       .interpolator(new AccelerateInterpolator())
       .duration(1000)

       .start();
       
```

[![gif](https://j.gifs.com/ERlBzW.gif)](https://youtu.be/ZHw8MfOM1Eg)

Without ViewAnimator

```java
AnimatorSet animatorSet = new AnimatorSet();
animatorSet.playTogether(
  ObjectAnimator.ofFloat(image,"translationY",-1000,0),
  ObjectAnimator.ofFloat(image,"alpha",0,1),
  ObjectAnimator.ofFloat(text,"translationX",-200,0)
);
animatorSet.setInterpolator(new DescelerateInterpolator());
animatorSet.setDuration(2000);
animatorSet.addListener(new AnimatorListenerAdapter(){
    @Override public void onAnimationEnd(Animator animation) {

      AnimatorSet animatorSet2 = new AnimatorSet();
      animatorSet2.playTogether(
          ObjectAnimator.ofFloat(image,"scaleX",1f,0.5f,1f),
          ObjectAnimator.ofFloat(image,"scaleY",1f,0.5f,1f)
      );
      animatorSet2.setInterpolator(new AccelerateInterpolator());
      animatorSet2.setDuration(1000);
      animatorSet2.start();

    }
});
animatorSet.start();
```

#More

[![gif](https://j.gifs.com/XD6R4V.gif)](https://youtu.be/Qlj40Y6ChSM)

Add same animation on multiples view
```java
ViewAnimator
       .animate(image,text)
       .scale(0,1)

       .start();
```

Add listeners
```java
ViewAnimator
       .animate(image)
       .scale(0,1)

       .onStart(() -> {})
       .onStop(() -> {})

       .start();

```

Use DP values
```java
ViewAnimator
       .animate(image)
           .dp().translationY(-200, 0)
       .start();
```

Animate Height / Width
```java
ViewAnimator
       .animate(view)
           .waitForHeight() //wait until a ViewTreeObserver notification
           .dp().width(100,200)
           .dp().height(50,100)
       .start();
```

Color animations
```java
ViewAnimator
       .animate(view)
            .textColor(Color.BLACK,Color.GREEN)
            .backgroundColor(Color.WHITE,Color.BLACK)
       .start();
```

Rotation animations
```java
ViewAnimator
       .animate(view)
            .rotation(360)
       .start();
```

Custom animations
```java
ViewAnimator
       .animate(text)
           .custom(new AnimationListener.Update () {
               @Override public void update(TextView view, float value) {
                   view.setText(String.format("%.02f",value));
               }
           }, 0, 1)
       .start();
```

Enhanced animations (Thanks [AndroidViewAnimations](http://u.720life.cn/g/54145d0471d91890860f7f8463c030465833829a238aa6bf2a6a629f24ec47c2616a11440c6384e0e7686e1a7b2bed06a46471f22483c9ae0190d67eb306d159),[NiftyDialogEffects]https://github.com/sd6352051/NiftyDialogEffects   
![screenshots](/EnhancedAnimations.gif)   
```java
.shake();
.bounce().interpolator(new BounceInterpolator());
.bounceIn();
.bounceOut();
.flash();
.flipHorizontal();
.flipVertical();
.wave();
.tada();
.rubber();
.pulse();
.standUp();
.swing();
.wobble();
.zoomIn();
.zoomOut();
.rollIn();
.rollOut();
.fadeIn();
.fadeOut();
.fall();
.newsPaper();
.slit();
.slideLeftIn();
.slideRightIn();
.slideTopIn();
.slideBottomIn();
.path(...);
.svgPath(...);
```

Path animations (Read http://blog.csdn.net/tianjian4592/article/details/47067161)   
```java
    final int[] START_POINT = new int[]{ 300, 270 };
    final int[] BOTTOM_POINT = new int[]{ 300, 400 };
    final int[] LEFT_CONTROL_POINT = new int[]{ 450, 200 };
    final int[] RIGHT_CONTROL_POINT = new int[]{ 150, 200 };
    Path path = new Path();
    path.moveTo(START_POINT[0], START_POINT[1]);
    path.quadTo(RIGHT_CONTROL_POINT[0], RIGHT_CONTROL_POINT[1], BOTTOM_POINT[0], BOTTOM_POINT[1]);
    path.quadTo(LEFT_CONTROL_POINT[0], LEFT_CONTROL_POINT[1], START_POINT[0], START_POINT[1]);
    path.close();
    ViewAnimator.animate(view).path(path).repeatCount(ViewAnimator.INFINITE).start();
```

SVG path animations (Read http://www.w3school.com.cn/svg/svg_path.asp)   
```html
 
     
    
```
```java
    final String SVG_PATH = "M 42.266949,70.444915 C 87.351695,30.995763 104.25847,28.177966 104.25847,28.177966 l 87.3517,36.631356 8.45339,14.088983 L 166.25,104.25847 50.720339,140.88983 c 0,0 -45.0847458,180.33898 -39.449153,194.42797 5.635594,14.08898 67.627119,183.15678 67.627119,183.15678 l 16.90678,81.7161 c 0,0 98.622885,19.72457 115.529665,22.54237 16.90678,2.8178 70.44491,-22.54237 78.8983,-33.81356 8.45339,-11.27118 76.08051,-107.07627 33.81356,-126.80085 -42.26695,-19.72457 -132.43644,-56.35593 -132.43644,-56.35593 0,0 -33.81356,-73.26271 -19.72458,-73.26271 14.08899,0 132.43644,73.26271 138.07204,33.81356 5.63559,-39.44915 19.72457,-169.0678 19.72457,-169.0678 0,0 28.17797,-25.36017 -28.17796,-19.72457 -56.35593,5.63559 -95.80509,11.27118 -95.80509,11.27118 l 42.26695,-87.35169 8.45339,-28.177968";
    ViewAnimator
    .animate(view)
    .svgPath(SVG_PATH)
    .repeatMode(ViewAnimator.REVERSE)
    .repeatCount(2)
    .start();
```

#Download

Add into your **build.gradle**

[![Download](https://api.bintray.com/packages/florent37/maven/ViewAnimator/images/download.svg)](https://bintray.com/florent37/maven/ViewAnimator/_latestVersion)

```groovy
compile 'com.github.florent37:viewanimator:1.0.2@aar'
compile 'com.nineoldandroids:library:2.4.0'
```

#Community

Looking for contributors, feel free to fork !

#Credits

Author: Florent Champigny   
Contributor: [李玉江(liyujiang)](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304694a542e8210ed3171fc5d0e6da3d3834f84a9b4f74f5a886ea3ff1697a2e88e2)   

 
   
 
 
   
 
 
   
 

#License

    Copyright 2015 florent37, Inc.

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ef5636e8f0f8cef4a5a34d5111ac76ac8ec2395d175af8fec5565667849bd7f21f69fe020511fd2614e4913f4995a7aca)