three.js
========

[![Latest NPM release][npm-badge]][npm-badge-url]
[![License][license-badge]][license-badge-url]
[![Dependencies][dependencies-badge]][dependencies-badge-url]
[![Dev Dependencies][devDependencies-badge]][devDependencies-badge-url]
[![Build Status](https://travis-ci.org/mrdoob/three.js.svg?branch=dev)](https://travis-ci.org/mrdoob/three.js)

#### JavaScript 3D library ####

The aim of the project is to create an easy to use, lightweight, 3D library. The library provides &lt;canvas&gt;, &lt;svg&gt;, CSS3D and WebGL renderers.

[Examples](http://u.720life.cn/g/966b41e49ef95e3b9815d603dd7e89c6a23251f0341b83c65dd7ea83473bf8fb)  &mdash;
[Documentation](http://u.720life.cn/g/966b41e49ef95e3b9815d603dd7e89c6809c0840dbdd323f5c8a5a06266e1fc4)  &mdash;
[Wiki](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046f9eaa7f02baf2c97d75b89cbb0e0177ed54ca38bed3de1c6ca26b6e4eb1bf120)  &mdash;
[Migrating](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046f9eaa7f02baf2c97d75b89cbb0e0177e7dcaff5f1e320ec783e6124855304e95a3f098f4ba71dcbb74c62ab9375b6930)  &mdash;
[Questions](http://u.720life.cn/g/ddb1c8aa997182cb1a4af16f7df394520a2863231ad8d7352308cd295ccf0ae9dee0c00eaa461abb91ee8fcf1094e2cb5781e7e0309ebce5b7555cd03981916d)  &mdash;
[Forum](http://u.720life.cn/g/60634847e115fbca3ab3ef25b33bebff3f35170b4193500f4497fd71adb8c7fa)  &mdash;
[Gitter](http://u.720life.cn/g/11e95d0ed8d2826912e12fe1dc3f342114a7997d9def365c061f48e97dc1911826fd9f0e434293a8a92de39e9f5af857)  &mdash;
[Slack](http://u.720life.cn/g/bcc0c8b9cda3d2f8499b01708643f07fb149b5c35638dc2227af8c559e30e5781bde163682451861a7048aae2aa42a1e) 

### Usage ###

Download the [minified library](http://u.720life.cn/g/966b41e49ef95e3b9815d603dd7e89c6b3cfad03d6806c1ef68c7c55c2207180692de6a2721ae6f77e1975532bfbabe6)  and include it in your HTML, or install and import it as a [module](http://u.720life.cn/g/966b41e49ef95e3b9815d603dd7e89c63d5d689dad748747543de4e202b2bcfae72bf76030a19a6051671a81174e8906be92fb1298af00304662fbda96dd9b5fea9cb177296a6c2b9e581d321c5db096 
Alternatively see [how to build the library yourself](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046f9eaa7f02baf2c97d75b89cbb0e0177e5c4015279ee02d925b3d072b7b27781c7de9140c0e8810ad32f431bc3a8a6d40 

```html
  
```

This code creates a scene, a camera, and a geometric cube, and it adds the cube to the scene. It then creates a `WebGL` renderer for the scene and camera, and it adds that viewport to the document.body element. Finally, it animates the cube within the scene for the camera.

```javascript
var camera, scene, renderer;
var geometry, material, mesh;

init();
animate();

function init() {

	camera = new THREE.PerspectiveCamera( 70, window.innerWidth / window.innerHeight, 0.01, 10 );
	camera.position.z = 1;

	scene = new THREE.Scene();

	geometry = new THREE.BoxGeometry( 0.2, 0.2, 0.2 );
	material = new THREE.MeshNormalMaterial();

	mesh = new THREE.Mesh( geometry, material );
	scene.add( mesh );

	renderer = new THREE.WebGLRenderer( { antialias: true } );
	renderer.setSize( window.innerWidth, window.innerHeight );
	document.body.appendChild( renderer.domElement );

}

function animate() {

	requestAnimationFrame( animate );

	mesh.rotation.x += 0.01;
	mesh.rotation.y += 0.02;

	renderer.render( scene, camera );

}
```

If everything went well you should see [this](http://u.720life.cn/g/3366bf22323b3ec0f128836fc66d4ddc64fd258607aab4c6f6a6e3fd8258199a 

### Change log ###

[releases](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046f9eaa7f02baf2c97d75b89cbb0e0177e4b79b9b2e16f1283fa57db24407bff26) 


[npm-badge]: https://img.shields.io/npm/v/three.svg
[npm-badge-url]: https://www.npmjs.com/package/three
[license-badge]: https://img.shields.io/npm/l/three.svg
[license-badge-url]: ./LICENSE
[dependencies-badge]: https://img.shields.io/david/mrdoob/three.js.svg
[dependencies-badge-url]: https://david-dm.org/mrdoob/three.js
[devDependencies-badge]: https://img.shields.io/david/dev/mrdoob/three.js.svg
[devDependencies-badge-url]: https://david-dm.org/mrdoob/three.js#info=devDependencies



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)