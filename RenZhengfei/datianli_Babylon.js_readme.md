# Babylon.js

Getting started? Play directly with the Babylon.js API using our [playground](http://u.720life.cn/g/16044ef89a722a139462bb61e3047a5d75bf7eed7d1b647363e7264a24ba62921c4de1c05a1526e1cd9634e020e3b9c9). It also contains a lot of samples to learn how to use it.

[![npm version](https://badge.fury.io/js/babylonjs.svg)](https://badge.fury.io/js/babylonjs)
[![Build Status](https://dev.azure.com/babylonjs/ContinousIntegration/_apis/build/status/CI?branchName=master)](https://dev.azure.com/babylonjs/ContinousIntegration/_build/latest?definitionId=1&branchName=master)
[![Average time to resolve an issue](http://isitmaintained.com/badge/resolution/BabylonJS/Babylon.js.svg)](http://isitmaintained.com/project/BabylonJS/Babylon.js "Average time to resolve an issue")
[![Percentage of issues still open](https://isitmaintained.com/badge/open/babylonJS/babylon.js.svg)](https://isitmaintained.com/project/babylonJS/babylon.js "Percentage of issues still open")
[![Build Size](https://img.badgesize.io/BabylonJS/Babylon.js/master/dist/preview%20release/babylon.js.svg?compression=gzip)](https://img.badgesize.io/BabylonJS/Babylon.js/master/dist/preview%20release/babylon.js.svg?compression=gzip)
[![Twitter](https://img.shields.io/twitter/follow/babylonjs.svg?style=social&label=Follow)](https://twitter.com/intent/follow?screen_name=babylonjs)

**Any questions?** Here is our official [forum](http://u.720life.cn/g/48809939ca6d2a05b6d96ab0fb1c64a3e336e285d1e4f76f0805baee71c2d040).

## CDN

-  
-  

Additional references can be found on   where `xxx` is the folder structure you can find in the /dist folder like  

For the preview release, use the following URLs:

-  
-  

Additional references can be found on   where xxx is the folder structure you can find in the /dist/preview release folder like  

## npm

BabylonJS and its modules are published on npm with full typing support. To install, use:

```text
npm install babylonjs --save
```

This will allow you to import BabylonJS entirely using:

```javascript
import * as BABYLON from 'babylonjs';
```

or individual classes using:

```javascript
import { Scene, Engine } from 'babylonjs';
```

If using TypeScript, don't forget to add 'babylonjs' to 'types' in `tsconfig.json`:

```json
    ...
    "types": [
        "babylonjs",
        "anotherAwesomeDependency"
    ],
    ...
```

To add a module, install the respective package. A list of extra packages and their installation instructions can be found on the [babylonjs user on npm](http://u.720life.cn/g/920c024f0b8c5aa5e32c4f88af4e6c96b540c46c6bb38d85f259158396791a61).

## Usage

See [Getting Started](http://u.720life.cn/g/4bc861bdb965b1f87ab6d2049bbeb2d9a3475fa41dff38af13bc35663f56934faecc6c4d16e9553f282fd08039e20ee6):

```javascript
// Get the canvas DOM element
var canvas = document.getElementById('renderCanvas');
// Load the 3D engine
var engine = new BABYLON.Engine(canvas, true, {preserveDrawingBuffer: true, stencil: true});
// CreateScene function that creates and return the scene
var createScene = function(){
    // Create a basic BJS Scene object
    var scene = new BABYLON.Scene(engine);
    // Create a FreeCamera, and set its position to {x: 0, y: 5, z: -10}
    var camera = new BABYLON.FreeCamera('camera1', new BABYLON.Vector3(0, 5, -10), scene);
    // Target the camera to scene origin
    camera.setTarget(BABYLON.Vector3.Zero());
    // Attach the camera to the canvas
    camera.attachControl(canvas, false);
    // Create a basic light, aiming 0, 1, 0 - meaning, to the sky
    var light = new BABYLON.HemisphericLight('light1', new BABYLON.Vector3(0, 1, 0), scene);
    // Create a built-in "sphere" shape; its constructor takes 6 params: name, segment, diameter, scene, updatable, sideOrientation
    var sphere = BABYLON.Mesh.CreateSphere('sphere1', 16, 2, scene, false, BABYLON.Mesh.FRONTSIDE);
    // Move the sphere upward 1/2 of its height
    sphere.position.y = 1;
    // Create a built-in "ground" shape; its constructor takes 6 params : name, width, height, subdivision, scene, updatable
    var ground = BABYLON.Mesh.CreateGround('ground1', 6, 6, 2, scene, false);
    // Return the created scene
    return scene;
}
// call the createScene function
var scene = createScene();
// run the render loop
engine.runRenderLoop(function(){
    scene.render();
});
// the canvas/window resize event handler
window.addEventListener('resize', function(){
    engine.resize();
});
```

## Preview release

Preview version of **4.0** can be found [here](http://u.720life.cn/g/54145d0471d91890860f7f8463c030461aab25cc3a6a69dc59b07bb5f1659f7d9782ff9cf2f452862564041b3f58d9273d83fb31da4576cb2d524f648fe8a2307e0bf5b7ebe91e86de2e7328e3c352c0).
If you want to contribute, please read our [contribution guidelines](http://u.720life.cn/g/54145d0471d91890860f7f8463c030461aab25cc3a6a69dc59b07bb5f1659f7dc173cf2c22d1bec81d31181fa6c0ab3af90eec2f689e732896602ff527b2774c666edb8654784af19402ad27528b67b0) first.

## Documentation

- [Documentation](http://u.720life.cn/g/4bc861bdb965b1f87ab6d2049bbeb2d94b71fb8681510c02d977313755761f48)
- [Examples](http://u.720life.cn/g/4bc861bdb965b1f87ab6d2049bbeb2d964ee643c9f020c49b159d529dc5e0410ee9d47ed2ece716d9a2702953a31415c)

## Contributing
Please see the [Contributing Guidelines](./contributing.md)

## Useful links

- Official web site: [www.babylonjs.com](http://u.720life.cn/g/d64b2bb24e4eb8fa5440920211cdbc2550d7d6803457200e42882a7ee6fd5e01)
- Online [playground](http://u.720life.cn/g/16044ef89a722a139462bb61e3047a5d75bf7eed7d1b647363e7264a24ba62921c4de1c05a1526e1cd9634e020e3b9c9) to learn by experimentating
- Online [sandbox](http://u.720life.cn/g/d64b2bb24e4eb8fa5440920211cdbc2549db21d258f50be45a8d3040c83a5d53d88f0a04abe95208fd75761e020d2cdf) where you can test your .babylon and glTF scenes with a simple drag'n'drop
- Online [shader creation tool](http://u.720life.cn/g/d64b2bb24e4eb8fa5440920211cdbc25875ff701a3d31be2a3ee91f74c418181) where you can learn how to create GLSL shaders
- 3DS Max [exporter](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304691608bdfa95c373cbd35643e26fc316ac0958f309fa6137da207527041a4ac46408d9deae42060620deaadb66e0f5c98) can be used to generate a .babylon file from 3DS Max
- Maya [exporter](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304691608bdfa95c373cbd35643e26fc316ac0958f309fa6137da207527041a4ac465a026fd923f46cf095e43d778fb9f57c) can be used to generate a .babylon file from 3DS Max
- Blender [exporter](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304691608bdfa95c373cbd35643e26fc316ac0958f309fa6137da207527041a4ac46d3f0ac9739af28683fab12f4b5d6a15e) can be used to generate a .babylon file from Blender 3d
- Unity 5[ (deprecated) exporter](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304691608bdfa95c373cbd35643e26fc316ac0958f309fa6137da207527041a4ac46e4dd22b4a2601ba16bc6074d40fcaea0) can be used to export your geometries from Unity 5 scene editor(animations are supported)
- [glTF Tools](http://u.720life.cn/g/54145d0471d91890860f7f8463c030469987c036692b1402ee1ce03691abd56d2da4d44953800e0cbf72df56fcc5c3ec) by KhronosGroup

## Features

To get a complete list of supported features, please visit our [website](http://u.720life.cn/g/d64b2bb24e4eb8fa5440920211cdbc251f83d25bf46f21ace223bc762efb53693e7cca9dbe13329203fb1ee12404e5e0).

## Build

Babylon.js is automatically built using [Gulp](http://u.720life.cn/g/924b3569ce37cbb0fe920ec83cf6876f3a23c4f1ba88f6198cf88ef8d5ed02b2). For further instructions see the readme at [/Tools/Gulp](http://u.720life.cn/g/54145d0471d91890860f7f8463c030461aab25cc3a6a69dc59b07bb5f1659f7d9782ff9cf2f452862564041b3f58d927003bd91773f75afca5712ea51493337b).



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6eb10da6ca96f176ecd6f34fc8a2bf61a7337612721a99a8a349a9ff5d1471404cc82e30562f319692f2167e46a3a40bfc)