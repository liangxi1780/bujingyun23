# LayaAir is an open-source 2D/3D engine

LayaAir use WebGL1.0/WebGL2.0 as graphic API and written by TypeScript. LayaAir is designed for high performance games and support TypeScript, JavaScript and ActionScript 3.0 programming language. Develop once and publish for multi-target platform (HTML5, Android, iOS, Wechat Mini-Game,QQ Mini-Game,BaiDu Mini-Game,XiaoMi Mini-Game,OPPO Mini-Game,VIVO Mini-Game,Bilibili Mini-Game,Alibaba Mini-Game, Facebook Instant Game).

## LayaAir features

- High performance

LayaAir use GPU graphic API(WebGL1.0/WebGL2.0). 
LayaAir is design to performance first.

- Light weight and easy to use

Except performance,LayaAir architecture aim to be simple and easy to use, openness and small size. It's a 2D/3D engine can run very well for HTML5 platform.

- Multi language development support

You can build your game from TypeScript,JavaScript and ActionScript3.0(Will be discard in the future).

- Multi target platform support

LayaAir can directly build HTML5 and many "Mini-Game platform",LayaAir can also extend native platform app with LayaNative, a complete development solution for LayaAir engine to target native Apps, such as iOS or Android. LayaNative uses LayaPlayer as the core runtime and uses reflection function to provide developers with a secondary development. You also can use this function to handle docking market on your native applications. And it also provides developers with testApp and build tools to package and publish your project.

- Mature ecosystem for design development and tool flow

[LayaAirIDE](http://u.720life.cn/g/ecde45d751a48289006e2629155ae00c0b0eea80d08d066437d0587c2ce2bd3ab90cd5562a2a515664c1772a2d73ac74aeeee227807648ece2cfba4427885f21) provides 2D development tools and visual editor. Clear workflow make, ergonomic, designed development efficiency.Support code development,UI and Scene Editor,Particle Editor,Animation Editor,Physical Editor,Presupposition,Build Platform Packaging,Code confusion, compression and so on.

[Unity Plugin](http://u.720life.cn/g/ecde45d751a48289006e2629155ae00c0b0eea80d08d066437d0587c2ce2bd3ab90cd5562a2a515664c1772a2d73ac74aeeee227807648ece2cfba4427885f21) provides 3D resource and scene editor and export with Unity, Compatibility support for commonly used unity funtion such as : Animtor,MeshRender,MeshFilter,ParticleSystem,Light,TrailRender,Lightingmap,Physics. Can let Unity project easier migration to LayaAir or directly use Unity as the 3D Editor.

- Open-source and free

Our official Layabox Github with complete engine source version, free of charge, including commercial usage.

## general features overview

- 2D

  Vector Renderer, Atlas Texture, HTML Text, Bitmap Fonts, Mask, Filter, Animation, Timeline, UI, ParticleSystem, SkeletonAnimation, Physics, etc..
  
- 3D

  Camera, Mesh, ParticleSystem, Multiple Light, SkyRender ,Animation , PhysicBaseRendering, Shadow, Custom Shader, Trail effect, PixelLine, Physics, Fog, StaticBatch, DynamicBatch, PostProcess etc...

## Beginner usage

#### TS version

```ts
    ///  
    class Sprite_DisplayImage{

        constructor(){
            Laya.init(550, 400);
            Laya.stage.scaleMode = "showall";

            var ape = new Laya.Sprite();
            //Loading our monkey
            ape.loadImage("res/apes/monkey2.png");

            Laya.stage.addChild(ape);
        }
    }
    new Sprite_DisplayImage();
```

#### JS version

```js
    Laya.init(550, 400);
    Laya.stage.scaleMode = "showall";

    var ape = new Laya.Sprite();
    //Loading our monkey
    ape.loadImage("res/apes/monkey2.png");

    Laya.stage.addChild(ape);
```

## API Document

- https://layaair.ldc.layabox.com/api2

## Tutorial Document

- https://ldc2.layabox.com/doc/

## Samples Demo

- https://layaair2.ldc2.layabox.com/demo2/

## Business Case 

- https://www.layabox.com/gamelist/

## Offical Community

- http://ask.layabox.com/



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e88cbea1c85de6d70e1bb4b82f774b51ede59ca454e38f44e17c96b6f37133649bb87a5c60ca0bd3f843248c340f306f8)