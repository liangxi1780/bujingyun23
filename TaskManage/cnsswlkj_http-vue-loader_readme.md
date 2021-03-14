# http-vue-loader
Load .vue files directly from your html/js. No node.js environment, no build step.

## examples

`my-component.vue`
```vue
 
     Hello {{who}} 
 

 
module.exports = {
    data: function() {
        return {
            who: 'world'
        }
    }
}
 

 
.hello {
    background-color: #ffe;
}
 
```

`index.html`
```html
 
 
   
      
      
   

   
     
        
     

     
      new Vue({
        el: '#my-app',
        components: {
          'my-component': httpVueLoader('my-component.vue')
        }
      });
     
   
 
```

## More examples
using `httpVueLoader()`  

```html
...
 

    new Vue({
        components: {
            'my-component': httpVueLoader('my-component.vue')
        },
        ...
```

or, using `httpVueLoader.register()`

```html
...
 

    httpVueLoader.register(Vue, 'my-component.vue');

    new Vue({
        components: [
            'my-component'
            ]
        },
        ...
```

or, using `httpVueLoader` as a plugin

```html
...
 

    Vue.use(httpVueLoader);

    new Vue({
        components: {
            'my-component': 'url:my-component.vue'
        },
        ...
```

or, using an array
```
    new Vue({
        components: [
            'url:my-component.vue'
            ]
        },
        ...
```

## Features
* ` `, ` ` and ` ` support the `src` attribute.
* ` ` is supported.
* `module.exports` may be a promise.
* Support of relative urls in ` ` and ` ` sections.
* Support custom CSS, HTML and scripting languages, eg. ` ` (see VueLoader.langProcessor).


## Browser Support

![Chrome](https://raw.github.com/alrra/browser-logos/master/src/chrome/chrome_48x48.png) | ![Firefox](https://raw.github.com/alrra/browser-logos/master/src/firefox/firefox_48x48.png) | ![Safari](https://raw.github.com/alrra/browser-logos/master/src/safari/safari_48x48.png) | ![Opera](https://raw.github.com/alrra/browser-logos/master/src/opera/opera_48x48.png) | ![Edge](https://raw.github.com/alrra/browser-logos/master/src/edge/edge_48x48.png) | ![IE](https://upload.wikimedia.org/wikipedia/commons/thumb/2/2f/Internet_Explorer_10_logo.svg/48px-Internet_Explorer_10_logo.svg.png) |
--- | --- | --- | --- | --- | --- |
Latest ✔ | Latest ✔ | ? | ? | Latest ✔ | 9+ ✔ |


## Requirements
* [Vue.js 2](http://u.720life.cn/g/1c3db3fec6433a3fb191bb48af91f3bb055304712f0641658c814ca15fec0089) ([compiler and runtime](http://u.720life.cn/g/1c3db3fec6433a3fb191bb48af91f3bb7dd6b26acf7a6ff1a200fabb7e0ec310ea605d582c845b3dd3ca92623b2f3792b0552064026db4d99361f2693b68818a9f66383d1b6136831efb296b142abca3)
* [es6-promise](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046de0a0891b495adaf115d84e76b88acfc92b0e485cb3f22767ff2c47d5138739a) (optional, except for IE, Chrome  ` section.  
The language is a simple function that accepts a script source as argument and returns a javascript script source.  

Example - CoffeeScript:

```JavaScript
  
  

 

httpVueLoader.langProcessor.coffee = function(scriptText) {

    return window.CoffeeScript.compile(scriptText, {bare: true});
}

 
```

Then, in you `.vue` file:

```CoffeeScript
...
 

module.exports =
    components: {}
    data: ->
        {}
    computed: {}
    methods: {}

 
...

```


Example - Stylus:

```JavaScript
  
  

 

httpVueLoader.langProcessor.stylus = function(stylusText) {

    return new Promise(function(resolve, reject) {
        
        stylus.render(stylusText.trim(), {}, function(err, css) {

            if (err) reject(err);
            resolve(css);
        });
    })
}

 
```

```stylus
...
 

    border-radius()
        -webkit-border-radius: arguments
        -moz-border-radius: arguments
        border-radius: arguments

    form input
        padding: 5px
        border: 1px solid
        border-radius: 5px

 
...
```

Sass (SCSS) example. Since `sass.compile()` is asynchronous, a promise needs to be returned:

```JavaScript
  
  

 
    httpVueLoader.langProcessor.scss = function (scssText) {
        return new Promise(function(resolve, reject) {
            sass.compile(scssText, function (result) {
                if ( result.status === 0 )
                    resolve(result.text)
                else
                    reject(result)
            });
        });
    }
// ....
```

```scss
...
 
$font-stack:    Helvetica, sans-serif;
$primary-color: #333;

body {
  font: 100% $font-stack;
  color: $primary-color;
}
 
```

## How it works

1. http request the vue file
1. load the vue file in a document fragment
1. process each section (template, script and style)
1. return a promise to Vue.js (async components)
1. then Vue.js compiles and cache the component


## Notes

The aim of http-vue-loader is to quickly test .vue components without any compilation step.  
However, for production, I recommend to use [webpack module bundler](http://u.720life.cn/g/f87b2d3c2d36bc68c43d51982df87eb3653dba4763f9fa7555edd5f63178f4e9) with [vue-loader](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046d161173a0c29f7137798419b0b23cd093d4a7398f3ce248f1f15fc3ac1c3b618), 
[webpack-simple](http://u.720life.cn/g/54145d0471d91890860f7f8463c030466d01a9d4830fa19a8a3f1aab08c023d12d79a2ae5a7956730d0d6f5b8c7c5386f36bde49d6e670d7a608cad5646a8658) is a good minimalist webpack config you should look at.  
BTW, see also [why Vue.js doesn't support templateURL](http://u.720life.cn/g/1c3db3fec6433a3fb191bb48af91f3bbb4a982780652a797c5cafe6420a34b1dff170597aa78e6d2382266565a1737179e32a54f81512919499bb135581613a5).  


## Caveat

Due to the lack of suitable API in Google Chrome and Internet Explorer, syntax errors in the ` ` section are only reported on FireFox.


## Credits

[Franck Freiburger](http://u.720life.cn/g/50ed45bf04376c9e6a8b01bde40c7e919a2c8a89ba2c91a9d254ca38860c94b92f3a5189a4023cb8cf18530e5705349e)



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ea350a6b6f588f63bc83366133f84683f92167f27a0fa91aaf6e9890e42c96cb36d9fa16f7355e06f61b25caf58f97877)