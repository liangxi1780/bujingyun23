# Lottie for Web, [Android](http://u.720life.cn/g/54145d0471d91890860f7f8463c030460d45ac8b2a4f0f6d6e146dc17d356a2a5b91894829598d30c5a537eea8f141d8  [iOS](http://u.720life.cn/g/54145d0471d91890860f7f8463c030460d45ac8b2a4f0f6d6e146dc17d356a2a03bcb800bbeea4290f94b3f5bb4812f6  [React Native](http://u.720life.cn/g/54145d0471d91890860f7f8463c030460d45ac8b2a4f0f6d6e146dc17d356a2a534f5f09a40460ff292c61ebbaf1f9b3  and [Windows](http://u.720life.cn/g/a5f3a088af39887133638b89002b6043a97b8d5638b67f21b7fce7b54ba26a55) 

Lottie is a mobile library for Web,  and iOS that parses [Adobe After Effects](http://u.720life.cn/g/33a66496da697b2ff049fee03ca0b1917fbf29e4f33d42427e2db12d5a9a6b64af667ac9ca8bddb019f240a77a4cc313)  animations exported as json with [Bodymovin](http://u.720life.cn/g/54145d0471d91890860f7f8463c030460d45ac8b2a4f0f6d6e146dc17d356a2aeb5bb2e6b2ac037e4fa9ff464e509a4f)  and renders them natively on mobile!

For the first time, designers can create **and ship** beautiful animations without an engineer painstakingly recreating it by hand. They say a picture is worth 1,000 words so here are 13,000:



# View documentation, FAQ, help, examples, and more at [airbnb.io/lottie](http://u.720life.cn/g/6d563d09ad0079e975b69586273f66bf554bbeb78033ebed7ef191fe86e6647e) 



![Example1](gifs/Example1.gif)


![Example2](gifs/Example2.gif)


![Example3](gifs/Example3.gif)


![Community](gifs/Community%202_3.gif)


![Example4](gifs/Example4.gif)


# Plugin installation

### Option 1 (Recommended):
**Download it from from aescripts + aeplugins:**
http://aescripts.com/bodymovin/

### Option 2:
**Or get it from the adobe store**
https://creative.adobe.com/addons/products/12557
CC 2014 and up.

## Other installation options:

### Option 3:
- download the ZIP from the repo.
- Extract content and get the .zxp file from '/build/extension'
- Use the [ZXP installer](http://u.720life.cn/g/e2aca6f0f4b85ac2222e96049d4723912a3d00fcd5050720761807d53cc9c99438003bfa27c567f474108e6bfbf587b2)  from aescripts.com.

### Option 4:
- Close After Effects 
- Extract the zipped file on `build/extension/bodymovin.zxp` to the adobe CEP folder: 
WINDOWS: 
`C:\Program Files (x86)\Common Files\Adobe\CEP\extensions or` 
`C:\ \AppData\Roaming\Adobe\CEP\extensions` 
MAC: 
`/Library/Application\ Support/Adobe/CEP/extensions/bodymovin` 
(you can open the terminal and type: 
`$ cp -R YOURUNZIPEDFOLDERPATH/extension /Library/Application\ Support/Adobe/CEP/extensions/bodymovin` 
then type: 
`$ ls /Library/Application\ Support/Adobe/CEP/extensions/bodymovin` 
to make sure it was copied correctly type) 

- Edit the registry key: 
WINDOWS: 
open the registry key `HKEY_CURRENT_USER/Software/Adobe/CSXS.6` and add a key named `PlayerDebugMode`, of type String, and value `1`. 
MAC: 
open the file `~/Library/Preferences/com.adobe.CSXS.6.plist` and add a row with key `PlayerDebugMode`, of type String, and value `1`. 

### Option 5:

Install the zxp manually following the instructions here:
https://helpx.adobe.com/x-productkb/global/installingextensionsandaddons.html
Skip directly to "Install third-party extensions"

### Option 6:

Install with [Homebrew](http://u.720life.cn/g/b2db0a16d95527f01d827ca5f3c60d04b3822b8427a2456d0f92dc748f2836dead1ca19a6a84be4bf262e2631d4d530960af3949ab89340ab077bfa52ae6a7c1ed8fcb32c85f181788e85e6789d29515 
```bash
brew tap danielbayley/adobe
brew cask install lottie
```

### After installing
- **Windows:** Go to Edit > Preferences > General > and check on "Allow Scripts to Write Files and Access Network"
- **Mac:** Go to Adobe After Effects > Preferences > General > and check on "Allow Scripts to Write Files and Access Network"

# HTML player installation
```bash
# with npm
npm install lottie-web

# with bower
bower install bodymovin
```
Or you can use the script file from here:
https://cdnjs.com/libraries/bodymovin
Or get it directly from the AE plugin clicking on Get Player

# Demo
[See a basic implementation here.](http://u.720life.cn/g/cb6ada9bef1b5139d6b2db303bd410c4330e40ac4b91667b2755f1c24c369221d1ef9c825edfea8360ec4b3cbadd2ffa)   

# Examples
[See examples on codepen.](http://u.720life.cn/g/2f308c9f94db49f6405bba0cdf9a246056da4381f48e7c8a5cbe1004d540bfe495f7aab0abad9c06f35b8a9e325a4af2)   

## How it works
[Here's](http://u.720life.cn/g/2bc656cc69a0e9056dae2ced9f817b904482df030ded26d1cdde0a20fff90c40dc732f430555f25137e6c70fa060ad26)  a video tutorial explaining how to export a basic animation and load it in an html page  
### After Effects
- Open your AE project and select the bodymovin extension on Window > Extensions > bodymovin
- A Panel will open with a Compositions tab listing all of your Project Compositions.
- Select the composition you want to export.
- Select a Destination Folder.
- Click Render
- look for the exported json file (if you had images or AI layers on your animation, there will be an images folder with the exported files)

### HTML
- get the lottie.js file from the build/player/ folder for the latest build
- include the .js file on your html (remember to gzip it for production)
```html
  
```
You can call lottie.loadAnimation() to start an animation.
It takes an object as a unique param with:
- animationData: an Object with the exported animation data.
- path: the relative path to the animation object. (animationData and path are mutually exclusive)
- loop: true / false / number
- autoplay: true / false it will start playing as soon as it is ready
- name: animation name for future reference
- renderer: 'svg' / 'canvas' / 'html' to set the renderer
- container: the dom element on which to render the animation


It returns the animation instance you can control with play, pause, setSpeed, etc.

```js
lottie.loadAnimation({
  container: element, // the dom element that will contain the animation
  renderer: 'svg',
  loop: true,
  autoplay: true,
  path: 'data.json' // the path to the animation json
});
```

#### Composition Settings:
Check this wiki page for an explanation for each setting.
https://github.com/airbnb/lottie-web/wiki/Composition-Settings

## Usage
Animation instances have these main methods:
### play

***
### stop

***
### pause

***
### setLocationHref(href)
- `href`: usually pass as `location.href`. Its useful when you experience mask issue in safari where your url does not have `#` symbol.

***
### setSpeed(speed)
- `speed`: 1 is normal speed.

***
### goToAndStop(value, isFrame)
- `value`: numeric value.
- `isFrame`: defines if first argument is a time based value or a frame based (default false).

***
### goToAndPlay(value, isFrame)
- `value`: numeric value.
- `isFrame`: defines if first argument is a time based value or a frame based (default false).

***
### setDirection(direction)
- `direction`: 1 is forward, -1 is reverse.

***
### playSegments(segments, forceFlag)
- `segments`: array. Can contain 2 numeric values that will be used as first and last frame of the animation. Or can contain a sequence of arrays each with 2 numeric values.
- `forceFlag`: boolean. If set to false, it will wait until the current segment is complete. If true, it will update values immediately.
***
### setSubframe(useSubFrames)
- `useSubFrames`:  If false, it will respect the original AE fps. If true, it will update on every requestAnimationFrame with intermediate values. Default is true.
***
### destroy()
***
### getDuration(inFrames)
- `inFrames`:  If true, returns duration in frames, if false, in seconds.
***

### Additional methods:
- updateTextDocumentData -- updates a text layer's data
[More Info](http://u.720life.cn/g/54145d0471d91890860f7f8463c030460d45ac8b2a4f0f6d6e146dc17d356a2ae2e865aa5c62c41f3f818cc047800cf171f90520dc1ec2016f87e3022d3a485af692a1caaa4e85931e2da2e9db93598d) 
***

### Lottie has 8 global methods that will affect all animations:
**lottie.play()** -- with 1 optional parameter **name** to target a specific animation  
**lottie.stop()** -- with 1 optional parameter **name** to target a specific animation  
**lottie.setSpeed()** -- first argument speed (1 is normal speed) -- with 1 optional parameter **name** to target a specific animation  
**lottie.setDirection()** -- first argument direction (1 is normal direction.) -- with 1 optional parameter **name** to target a specific animation  
**lottie.searchAnimations()** -- looks for elements with class "lottie" or "bodymovin"  
**lottie.loadAnimation()** -- Explained above. returns an animation instance to control individually.  
**lottie.destroy()** -- To destroy and release resources. The DOM element will be emptied. 
**lottie.registerAnimation()** -- you can register an element directly with registerAnimation. It must have the "data-animation-path" attribute pointing at the data.json url 
**lottie.setQuality()** -- default 'high', set 'high','medium','low', or a number > 1 to improve player performance. In some animations as low as 2 won't show any difference. 

## Events
- onComplete
- onLoopComplete
- onEnterFrame
- onSegmentStart

you can also use addEventListener with the following events:
- complete
- loopComplete
- enterFrame
- segmentStart
- config_ready (when initial config is done)
- data_ready (when all parts of the animation have been loaded)
- data_failed (when part of the animation can not be loaded)
- loaded_images (when all image loads have either succeeded or errored)
- DOMLoaded (when elements have been added to the DOM)
- destroy

#### Other loading options
- if you want to use an existing canvas to draw, you can pass an extra object: 'rendererSettings' with the following configuration:
```js
lottie.loadAnimation({
  container: element, // the dom element
  renderer: 'svg',
  loop: true,
  autoplay: true,
  animationData: animationData, // the animation data
  rendererSettings: {
    context: canvasContext, // the canvas context
    scaleMode: 'noScale',
    clearCanvas: false,
    progressiveLoad: false, // Boolean, only svg renderer, loads dom elements when needed. Might speed up initialization for large number of elements.
    hideOnTransparent: true, //Boolean, only svg renderer, hides elements when opacity reaches 0 (defaults to true)
    className: 'some-css-class-name'
  }
});
```
Doing this you will have to handle the canvas clearing after each frame
 
Another way to load animations is adding specific attributes to a dom element.
You have to include a div and set it's class to "lottie".
If you do it before page load, it will automatically search for all tags with the class "lottie".
Or you can call `lottie.searchAnimations()` after page load and it will search all elements with the class "lottie".
 
- Add the data.json to a folder relative to the html
- Create a div that will contain the animation.
- **Required**
  - A class called "lottie"
  - A "data-animation-path" attribute with relative path to the data.json
- **Optional**
  - A "data-anim-loop" attribute
  - A "data-name" attribute to specify a name to target play controls specifically

**Example**

```html
   
```



## Preview
You can preview or take an svg snapshot of the animation to use as poster. After you render your animation, you can take a snapshot of any frame in the animation and save it to your disk. I recommend to pass the svg through an svg optimizer like https://jakearchibald.github.io/svgomg/ and play around with their settings. 

## Recommendations

### Files
If you have any images or AI layers that you haven't converted to shapes (I recommend that you convert them, so they get exported as vectors, right click each layer and do: "Create shapes from Vector Layers"), they will be saved to an images folder relative to the destination json folder.
Beware not to overwrite an existing folder on that same location.


### Performance
This is real time rendering. Although it is pretty optimized, it always helps if you keep your AE project to what is necessary 
More optimizations are on their way, but try not to use huge shapes in AE only to mask a small part of it. 
Too many nodes will also affect performance.

### Help
If you have any animations that don't work or want me to export them, don't hesitate to write.  
I'm really interested in seeing what kind of problems the plugin has.  
my email is **hernantorrisi@gmail.com**


## AE Feature Support
- The script supports precomps, shapes, solids, images, null objects, texts
- It supports masks and inverted masks. Maybe other modes will come but it has a huge performance hit.
- It supports time remapping
- The script supports shapes, rectangles, ellipses and stars.
- Expressions. Check the wiki page for [more info.](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046d15d7d135cc25395e955f8802373614b42837151d4bfd379735c61ed4ef69e7b8263b10a4dcab16bdf7c109f34b9f6b1) 
- Not supported: image sequences, videos and audio are not supported
- **No  negative layer stretching**! No idea why, but stretching a layer messes with all the data.

## Development
`npm install` or `bower install` first
`npm start`

## Notes
- If you want to modify the parser or the player, there are some gulp commands that can simplify the task
- look at the great animations exported on codepen [See examples on codepen.](http://u.720life.cn/g/2f308c9f94db49f6405bba0cdf9a246056da4381f48e7c8a5cbe1004d540bfe495f7aab0abad9c06f35b8a9e325a4af2) 
- gzipping the animation jsons and the player have a huge reduction on the filesize. I recommend doing it if you use it for a project.

## Issues
- For missing mask in Safari browser, please anim.setLocationHref(locationHref) before animation is generated. It usually caused by usage of base tag in html. (see above for description of setLocationHref)



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)