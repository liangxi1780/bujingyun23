# Zeu.js

![Build Status](https://travis-ci.org/shzlw/zeu.svg?branch=master)

Zeu.js is JavaScript library featuring a collection of prebuilt visualization components for building real-time TV dashboard, monitoring UI and IoT web interface.

## Demo

[My Command Center](http://u.720life.cn/g/54753324e73906261532edaac736d51cdfba3d4cb909582469c981c660c3cb3b192acb1e8a57c8e034234466c1225ed825ec0a9e00d330716f616ceaa73ebda0)

## Installation

From lib
```html
  
```

From npm
```
npm install zeu
```

From CDN
```
https://unpkg.com/zeu/lib/zeu.min.js
```

## Usage

#### General

Use a div as the base to create the component.
  - Each component has its own recommended size. 
  - The scale changes based on the height of the outer div.

```html
  
```

#### FPS

Default fps is 60 for components using canvas.

```javascript
zeu.Settings.fps = 60;
```

#### Components

| Component | Example |
| --------- | ------- |   
| [Bar Meter](http://u.720life.cn/g/54753324e73906261532edaac736d51cdfba3d4cb909582469c981c660c3cb3b230036e6d8eae1a5c40967b9600e23b3e5f96f347c59885579661ccfa1ba158d) | |
| [Blink Text](http://u.720life.cn/g/54753324e73906261532edaac736d51cdfba3d4cb909582469c981c660c3cb3b1c200a1672f3b5e6aa1477c2666473ef28989eac0fdceaff8289dc43658679c3) | |
| [Digital Clock](http://u.720life.cn/g/54753324e73906261532edaac736d51cdfba3d4cb909582469c981c660c3cb3b04c3f9ea90f6b6564c427f8f8b040be7e521fe5e1eca22ca254587d7d9ccf0cb) | |
| [Double Circle](http://u.720life.cn/g/54753324e73906261532edaac736d51cdfba3d4cb909582469c981c660c3cb3b7eb1e98a6d355c87b49174637719a848a97f3428dd766d9fb0f585de7aad79da) | |

#### Bar Meter ([Example](http://u.720life.cn/g/54753324e73906261532edaac736d51cdfba3d4cb909582469c981c660c3cb3b230036e6d8eae1a5c40967b9600e23b3e5f96f347c59885579661ccfa1ba158d)

```html
  
```
```javascript
var barMeter = new zeu.BarMeter(
  document.getElementById('bar-meter'), {
    min: 0,
    max: 100,
    value: 80,
    dashColor: 'white',
    barColor: 'red',
    speed: 10
  });

barMeter.value = 60;
barMeter.dashColor = 'green';
barMeter.barColor = 'blue';
```

#### Blink Text ([Example](http://u.720life.cn/g/54753324e73906261532edaac736d51cdfba3d4cb909582469c981c660c3cb3b1c200a1672f3b5e6aa1477c2666473ef28989eac0fdceaff8289dc43658679c3)

```html
  
```
```javascript
var binkText = new zeu.BlinkText(
  document.getElementById('blink-text'), {
    interval: 300,
    blinkCss: 'color: white; background-color: blue;'
  });

// Turn on the blink
binkText.blink();

binkText.blinkCss = 'color: white; background-color: green;';
binkText.interval = 2000;
binkText.blink('NEW BLINK TEXT');  

// Turn off the blink
binkText.unblink();
```

#### Digital Clock ([Example](http://u.720life.cn/g/54753324e73906261532edaac736d51cdfba3d4cb909582469c981c660c3cb3b04c3f9ea90f6b6564c427f8f8b040be7e521fe5e1eca22ca254587d7d9ccf0cb)

```html
  
```
```javascript
var digitalClock = new zeu.DigitalClcok(
  document.getElementById('digital-clock'), {
    barWidth: 8,
    barHeight : 30,
    space: 8,
    hourOffset: 5,
    dashColor: '#000',
    numberColor: 'blue'
  }
);

digitalClock.numberColor = '#ff0000';
digitalClock.dashColor = '#000';
```

#### Double Circle ([Example](http://u.720life.cn/g/54753324e73906261532edaac736d51cdfba3d4cb909582469c981c660c3cb3b7eb1e98a6d355c87b49174637719a848a97f3428dd766d9fb0f585de7aad79da)

```html
  
```
```javascript
// Circle in dots
var doubleCircleWithDots = new zeu.DoubleCircle(
  document.getElementById('double-circle-in-dots'), {
    isDot: true,
    dots: 30,
    outer: {
      color: 'red',
      radius: 80,
      speed: 5
    },
    inner: {
      color: 'blue',
      radius: 70,
      speed: 3
    },
    fontColor: 'green',
    text: 'MIDDLE',
    font: '30px Arial'
  });

// Circle in line
var doubleCircleInLine = new zeu.DoubleCircle(
  document.getElementById('double-circle-in-line'), {
    isDot: false,
    lineWidth: 10,
    outer: {
      color: 'red',
      radius: 90,
      speed: 0.5
    },
    inner: {
      color: 'blue',
      radius: 70,
      speed: 0.2
    },
    fontColor: 'green',
    text: 'MIDDLE',
    font: 'italic bold 30px Arial'
  });

  doubleCircleInLine.fontColor = 'red';
  doubleCircleInLine.text = 'CHANGE!';
```

#### Heartbeat ([Example](http://u.720life.cn/g/54753324e73906261532edaac736d51cdfba3d4cb909582469c981c660c3cb3b1099bb68b17be1e49525b9381b95590a9778754c4a6ab11786ba9dc598d0742f)

```html
  
```
```javascript
var heartbeat = new zeu.Heartbeat(
  document.getElementById('heartbeat'), {
    lineColor: 'red',
    fontColor: 'grey'
  });

heartbeat.lineColor = 'blue';
heartbeat.fontColor = 'green';

// Start a beat
heartbeat.beat();

// Start a beat every one second
setInterval(function() {
  heartbeat.beat();
}, 1000);
```

#### Message Queue ([Example](http://u.720life.cn/g/54753324e73906261532edaac736d51cdfba3d4cb909582469c981c660c3cb3b66dc66436ecbbea1fff9150bf1bd7f05d56a914b7b7749f726bb92f9dab13be2)

```html
  
```
```javascript
var messageQueue = new zeu.MessageQueue(
  document.getElementById('message-queue'), {
    barWidth: 60,
    space: 20,
    barColor: 'red',
    maxQueueCapacity: 10
  });

messageQueue.barColor = '#008000';

// Push a message
messageQueue.push();

// Pop a message
messageQueue.pop();
```

#### Round Fan ([Example](http://u.720life.cn/g/54753324e73906261532edaac736d51cdfba3d4cb909582469c981c660c3cb3b93bc2e0b501d577767079cd7aa5e915dabad89a9d7237e900b1334637531ac82)

```html
  
```
```javascript
var roundFan = new zeu.RoundFan(
  document.getElementById('round-fan'), {
    fanColor: 'blue',
    centerColor: 'blue',
    speed: 1
  });
roundFan.speed = 5;
roundFan.fanColor = 'red';
roundFan.centerColor = 'green';

// Turn off the fan
roundFan.off();

// Turn on the fan
roundFan.on();
```

#### Scroll Panel ([Example](http://u.720life.cn/g/54753324e73906261532edaac736d51cdfba3d4cb909582469c981c660c3cb3b55a9dadfca920e96c24b5f33a10501c4034bb2af90499d0b3da25258f6333fcf)

```html
  
```
```javascript
var scrollPanel1 = new zeu.ScrollPanel(
  document.getElementById('scroll-panel'), {
    isUp: true
  });

// Push a html element
var message = document.createElement('div');
message.innerHTML = 'value';
message.style.cssText = 'margin: 10px; padding: 10px; color: white; background-color: green;';
scrollPanel1.push(message);

// Push a simple text
var css = 'margin: 3px; padding: 3px; color: white; background-color: green;';
scrollPanel2.pushText('value', css);
```

#### Volume Meter ([Example](http://u.720life.cn/g/54753324e73906261532edaac736d51cdfba3d4cb909582469c981c660c3cb3b36105e1324208e40c142ff9aa2bb979704b8cf0994d522c779ac5a3acd3ac308)

```html
  
```
```javascript
var volumeMeter = new zeu.VolumeMeter(
  document.getElementById('volume-meter'), {
    min: 0,
    max: 200,
    fillColor: 'green',
    fontColor: 'black',
    lineColor: 'black',
    lineWidth: 5
  });

volumeMeter.fillColor = 'red';
volumeMeter.fontColor = 'green';
volumeMeter.value = 100;
```

#### Warning Dialog ([Example](http://u.720life.cn/g/54753324e73906261532edaac736d51cdfba3d4cb909582469c981c660c3cb3b20ac995f2594b318e772e9bb0cbda803c187cf79ef1a3785762f39414557a4ef)

```javascript
var warningDialog = new zeu.WarningDialog({ 
  interval: 5000,
  reason: 'TEST'
});

warningDialog.reason = 'NEW WARNING MESSAGE';
warningDialog.interval = 2000;

// Display the dialog
warningDialog.blink();

// Hide the dialog
warningDialog.unblink();
```

## License

[MIT](http://u.720life.cn/g/ba059582536a397f7c573b87c8bea647045b0ef049248233b6f76e909e70200fe7048b25e29c8bab79aeff32ea74556a)


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e309f15504de1f5078e2d2d0bc4ef8666bb90fc26401b3c304baccceb6fc8b1ebe446974eedfb66225c03e8928b636058)