![Semantic](http://www.semantic-ui.com/images/logo.png)

# Semantic UI

Semantic is a highly-themable UI framework with intuitive naming conventions built around common usage.

Key Features
* 50+ UI Elements
* 3000 + CSS Variables
* 3 Levels of Variable Inheritance (Similar to SublimeText)
* Built using EM values for responsive design

> Semantic UI is now at 1.0, be sure to check out our [release notes](http://u.720life.cn/g/54145d0471d91890860f7f8463c030468ab25669c6254e8b40e62adbbdafa07d2ef96adce29bb2d1ba24ba7be424ca357c9c0f8370c841f3c102637a3043580650ea879518b47daf1b9a1c52d6e88b58f466e1beb456caa90a5ba668ca8b672f71f073085134d5579df7b022bf7083c3) for changes from the pre-release.

## International

* **Chinese** A Chinese mirror site is available at [http://www.semantic-ui.cn](http:/www.semantic-ui.cn)
* **Right-to-Left (RTL)** - An RTL version can be created using our build tools by selecting `rtl` from the install script
* **Translation** - To help translate see the [Wiki Guide](http://u.720life.cn/g/54145d0471d91890860f7f8463c030468ab25669c6254e8b40e62adbbdafa07d4281bf6d46b862ba9e97d4d65ed7232db449405f974e03776bc24496c4af590b56bee2cba787821da15cc0812245ef63) for translations 

## Release Schedule

Semantic follows a weekly schedule for feature updates. To see what changes are scheduled for upcoming releases, be sure to visit the [release milestone](http://u.720life.cn/g/54145d0471d91890860f7f8463c030468ab25669c6254e8b40e62adbbdafa07d1fcbeb36d4cde778f655ae158be740b315628f58c196bf45077288a853feb847) page.

## Community Support

* **Want to learn about Semantic?** [Request an Invite](http://u.720life.cn/g/bc35754af1853eb0b7eeef887ec84d673a19c0baf7bd767a65a0e92b228868f83946476676366e5a786a9cac4fd2aa0b63e699f6a3da971b4f305731437ef8fdfc17b59cb5f8e292fbe0ef0ca097d56c55eb7fb2b0adb249a54aa2679ec07128e6cfaa083a57c92fe25f6639f251c9b0) to join [our Slack chatroom](http://u.720life.cn/g/c97f02460b89f689a2c09bd8c816df66e527a703334d04927a86075eeb79e735) for support and project discussions
* **Have a bug?** Make a test case by forking this [jsfiddle](http://u.720life.cn/g/48fbe19ea70a310b4fc2902725284b3cbbd9a627e55303e952a9b9f9918ee1a7), then submit a [bug on GitHub](http://u.720life.cn/g/54145d0471d91890860f7f8463c030468ab25669c6254e8b40e62adbbdafa07d4e32dea999ca19181657703f45603b6beb6515fae855a37ebbf1b5473577774f)
* **Having issues with your code?** Submit a question on [StackOverflow](http://u.720life.cn/g/ef1090dc713ebc366f3fec33c36e27efaaa3460ec1749cf5e44c445815a2baa2) or ask our [Google Group](http://u.720life.cn/g/941693b557d072bb769494a6a61fcd979ee9fee4d4fd0c2a6b8a30bc68eade21eaf0c34af75b952d34ac2e45809daf36b82b5d9d5901bc5b4a7b28bd47c24562)
* **Looking for a specific integration like Dart, Wordpress, Drupal, Angular, or Rails?** Check out our [integration page](http://u.720life.cn/g/54145d0471d91890860f7f8463c030468ab25669c6254e8b40e62adbbdafa07d4281bf6d46b862ba9e97d4d65ed7232d189bb421e9c2f9affa1c26d7289d1f92)


## Contributing
* **Missing documentation in your language?** Help us make Semantic available in more languages by [joining our translation community](http://u.720life.cn/g/187a633cc93501bb91ac0a975d230ba55f0ba12aa9764a709ebaf50420f887eb504709b6d623459f7cddf0bd63ddcb15579b1349fa73044005f7688f0d7513b6)
* **Want to help with integration?** Projects are organizing for official [Meteor](http://u.720life.cn/g/54145d0471d91890860f7f8463c030468ab25669c6254e8b40e62adbbdafa07d0d04e64f508ec508a84c7273658d86b3fa482386d73ddff60d8b76a6957da2fc), and [Angular](http://u.720life.cn/g/54145d0471d91890860f7f8463c030468ab25669c6254e8b40e62adbbdafa07d6ba58e193fd73531e19d0296de2f9209174b48f5d530c9c3d7a0d18cac97ad38) integrations as well as a [Sass](http://u.720life.cn/g/54145d0471d91890860f7f8463c030468ab25669c6254e8b40e62adbbdafa07d94783024f1fd5effda51870f66562bc0) port. Join the discussion on their respective boards.
* **Want to help others learn concepts behind Semantic?** [Learnsemantic.com](http://u.720life.cn/g/da359a74e23635481bec54c188544c3ccbe4d5561e16389419522d982b6122c1) needs articles to help others get others up to speed with Semantic UI. [Send me an e-mail](mailto:jack@semantic-ui.com) if you are interested.


## Getting Started

### Basic Usage (Default Theme)

We recommend setting up the Semantic build workflow to support on-the-fly
theming and customization, but it is not required.

To use the "ready-to-use" distribution version, which includes all components, simply link to
`dist/semantic.js` and `dist/semantic.css` (or their minified counterparts) in your page.

``` html
 
  
```

You may also prefer to use individual components found in `dist/components` to reduce the libraries file size.

``` html
 
```


### Recommended Usage (Themed)

Semantic is best used actively during development. We have included build tools for updating your site's theme as you work.

![Getting Started](https://dl.dropboxusercontent.com/u/2657007/install.gif)

```
npm install
gulp
```

Running gulp for the first time will start the interactive set-up.

This helps you create two important files ``semantic.json`` which stores your folder set-up, and ``themes.config`` a central file for setting ui themes.

The install utility will also help you set-up which components you want to include in your packaged release, ignoring parts of Semantic you may not use.

Once set-up you can use these commands to maintain your project
```nodejs
gulp  // defaults to watch after install
gulp build // build all files from source
gulp clean // clears your dist folder
gulp watch // watch files
gulp install // re-runs install
gulp help // list all commands
```

For more detail into how work with Semantic when building a site please [read out customization guide](http://u.720life.cn/g/7761946278afd54ad094f841d822b53a7096cef702fd8a0ff9ddbe980155d469c62ac3f92cc12127cef19e49e77df7dcbc312d1d05b15106bc63e7f13ecff380) on [LearnSemantic.com](http://u.720life.cn/g/7761946278afd54ad094f841d822b53a1077c9e9a9942c4d0002351b0d15db91)


## Browser Support

* Last 2 Versions FF, Chrome, IE (aka 10+)
* Safari 6
* IE 9+ (Browser prefix only)
* Android 4
* Blackberry 10


## Pull Requests

When adding pull requests be sure to merge into [next](http://u.720life.cn/g/54145d0471d91890860f7f8463c030468ab25669c6254e8b40e62adbbdafa07d2c76e5ca968ababd41bae467ab2ffd78074a1f181aae636383e0730a781bdde2) branch. If you need to demonstrate a fix in ``next`` release, you can use [this jsfiddle](http://u.720life.cn/g/48fbe19ea70a310b4fc2902725284b3c2e32b4e9952631563530433b8cd282c2)

## Reaching Out

If you'd like to start a conversation about Semantic feel free to reach out by e-mail [jack@semantic-ui.com](mailto:jack@semantic-ui.com)

[![Flattr This](https://api.flattr.com/button/flattr-badge-large.png)](https://flattr.com/submit/auto?user_id=jlukic&url=https%3A%2F%2Fgithub.com%2Fjlukic%2FSemantic-UI)




 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e088e1ab01da965140f6d16f579dcea7a0f626d44967f5af91913c86c7be3825b9565e8eb8e1f1ef383b07b8ccf6cf927)