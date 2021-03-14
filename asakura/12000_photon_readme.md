# [Photon](http://u.720life.cn/g/89ad14b15b3b363470d0a3fe56f3688e1fde13cb6c021e39e4ff9bb418975983)

[![Build Status](https://img.shields.io/travis/connors/photon/master.svg)](https://travis-ci.org/connors/photon)

UI toolkit for building desktop apps with Electron.

## Getting started

* Clone the repo with `git clone https://github.com/connors/photon.git`
* [Read the docs](http://u.720life.cn/g/89ad14b15b3b363470d0a3fe56f3688ebd14853ede6272352e5c069de5beefdb) to learn about the components and how to get your new application started

Take note that our master branch is our active, unstable development branch and that if you're looking to download a stable copy of the repo, check the [tagged downloads](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046e49bc2962d2982b0c9b5fa127b8e1d533bbc0d09c3ac0b9011cadd32713bff5b).

### What's included

Within the download you'll find the following directories and files, logically grouping common assets. You'll see something like this:

```
photon/
├── css/
│   ├── photon.css
├── fonts/
│   ├── photon-entypo.eot
│   ├── photon-entypo.svg
│   ├── photon-entypo.ttf
│   └── photon-entypo.woff
└── template-app/
    ├── js/
    │   └── menu.js
    ├── app.js
    ├── index.html
    └── package.json
```

We provide compiled CSS (`photon.*`). We also include the Entypo fonts and a template Electron application for you to quickly get started.

## Documentation

Photon's documentation is built with [Jekyll](http://u.720life.cn/g/41b49956459f45e009beb54ff3039b85070a7312512afd912ae4fcdadbfdf8f7) and publicly hosted on GitHub Pages at  . The docs may also be run locally.

### Running documentation locally

1. If necessary, [install Jekyll](http://u.720life.cn/g/41b49956459f45e009beb54ff3039b85e03b8cf02995133a4e80012723e07bed2abc6068adaa7e2c802541e8db906936) (requires v2.5.x).
  * **Windows users:** Read [this unofficial guide](http://u.720life.cn/g/9a8b66062425babc645cfbfb5fddeca01ddb385fa19e3b364e9fd34a791ee79ae63eab772ff1e4ec65eda58995ed6b17) to get Jekyll up and running without problems.
2. Install the Ruby-based syntax highlighter, [Rouge](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046ea9e4218bece4d01baca1a2dc4fb895d), with `gem install rouge`.
3. From the root `/photon` directory, run `jekyll serve` in the command line.
4. Open   in your browser, and boom!

Learn more about using Jekyll by reading its [documentation](http://u.720life.cn/g/41b49956459f45e009beb54ff3039b85188876f586c189321864e576bd376330).

## Contributing

Please file a GitHub issue to [report a bug](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046e49bc2962d2982b0c9b5fa127b8e1d53083971beeef80cb3b73c3a42490c02e5). When reporting a bug, be sure to follow the [contributor guidelines](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046e49bc2962d2982b0c9b5fa127b8e1d53d2c5a2c8dd542c0292b91e489ff5119db7b035e0aad6b40ffa215be3bf07e341).


## Development

1. Install node dependencies: `npm install`.
2. Open the example app: `npm start`.

Modifying source Sass files? Open a second Terminal tab and run `npm run build` to kick off a build of the compiled `photon.css`.

## Versioning

For transparency into our release cycle and in striving to maintain backward compatibility, Photon is maintained under the Semantic Versioning guidelines. Sometimes we screw up, but we'll adhere to these rules whenever possible.

Releases will be numbered with the following format:

` . . `

And constructed with the following guidelines:

* Breaking backward compatibility **bumps the major** while resetting minor and patch
* New additions without breaking backward compatibility **bumps the minor** while resetting the patch
* Bug fixes and misc changes **bumps only the patch**

For more information on SemVer, please visit  .

## Maintainers

Connor Sears

*  
*  

## License

Copyright @connors. Released under MIT.



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e5bea0ac5cb321b17f5d3f82b9080556034b901ecc7c27371f1e00d098630e09d814c1aecdb0081ff90681e3dc30f5eb0)