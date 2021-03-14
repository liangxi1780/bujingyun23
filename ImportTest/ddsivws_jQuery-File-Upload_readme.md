# jQuery File Upload Plugin

## Demo
[Demo File Upload](http://u.720life.cn/g/5cc336d067ebc308dbdf29ac34e0548a92544b43badc4c496d193ffb0accc084a2aaa4a9e60fdd7c4750f51c5b7fd937)

## Description
File Upload widget with multiple file selection, drag&amp;drop support, progress bars, validation and preview images, audio and video for jQuery.  
Supports cross-domain, chunked and resumable file uploads and client-side image resizing. Works with any server-side platform (PHP, Python, Ruby on Rails, Java, Node.js, Go etc.) that supports standard HTML form file uploads.

## Setup
* [How to setup the plugin on your website](http://u.720life.cn/g/54145d0471d91890860f7f8463c030467c8c0e8e936246c8b435ca1a17ec418ded9af66a59783c10f4eb213a36b44bc8c68defc4631bc723c25cad333780d52f)
* [How to use only the basic plugin (minimal setup guide).](http://u.720life.cn/g/54145d0471d91890860f7f8463c030467c8c0e8e936246c8b435ca1a17ec418ded9af66a59783c10f4eb213a36b44bc8dfffbae69c41e426b22aef034a2fba48)

## Support

* **[Support Forum](http://u.720life.cn/g/941693b557d072bb769494a6a61fcd97e1a25fabd58105106d93506ad03635bec4caba2c3bc0c68c0b8a58e1968282b6ebbeb5002492f9623d140d3aa4aeb6ef)**  
**Support requests** and **general discussions** about the File Upload plugin can be posted to the official
[Support Forum](http://u.720life.cn/g/941693b557d072bb769494a6a61fcd97e1a25fabd58105106d93506ad03635bec4caba2c3bc0c68c0b8a58e1968282b6ebbeb5002492f9623d140d3aa4aeb6ef).  
If your question is not directly related to the File Upload plugin, you might have a better chance to get a reply by posting to [Stack Overflow](http://u.720life.cn/g/ddb1c8aa997182cb1a4af16f7df394520a2863231ad8d7352308cd295ccf0ae90be6ae055a1e5c2808c2a2755989b47a680e1478892b76c676a786fbc4baec991f4cabab8937df03411deda42e9fb886).

* Bugs and new features
**Bug fixes** and **new features** can be proposed using [pull requests](http://u.720life.cn/g/54145d0471d91890860f7f8463c030467c8c0e8e936246c8b435ca1a17ec418d9c8d62191cb9445b1e95233781925b828366f690ae59b6068d8dbd4de8ac128d).
Please read the [contribution guidelines](http://u.720life.cn/g/54145d0471d91890860f7f8463c030467c8c0e8e936246c8b435ca1a17ec418d8b585d97f62ffdc07efc25a14fa7d53014f45d78f60d98ece3843b4ce12cb0c2f3341a954aa686f5cf70a79694146310) before posting.

## Features
* **Multiple file upload:**  
  Allows to select multiple files at once and upload them simultaneously.
* **Drag & Drop support:**  
  Allows to upload files by dragging them from your desktop or filemanager and dropping them on your browser window.
* **Upload progress bar:**  
  Shows a progress bar indicating the upload progress for individual files and for all uploads combined.
* **Cancelable uploads:**  
  Individual file uploads can be canceled to stop the upload progress.
* **Resumable uploads:**  
  Aborted uploads can be resumed with browsers supporting the Blob API.
* **Chunked uploads:**  
  Large files can be uploaded in smaller chunks with browsers supporting the Blob API.
* **Client-side image resizing:**  
  Images can be automatically resized on client-side with browsers supporting the required JS APIs.
* **Preview images, audio and video:**  
  A preview of image, audio and video files can be displayed before uploading with browsers supporting the required APIs.
* **No browser plugins (e.g. Adobe Flash) required:**  
  The implementation is based on open standards like HTML5 and JavaScript and requires no additional browser plugins.
* **Graceful fallback for legacy browsers:**  
  Uploads files via XMLHttpRequests if supported and uses iframes as fallback for legacy browsers.
* **HTML file upload form fallback:**  
  Allows progressive enhancement by using a standard HTML file upload form as widget element.
* **Cross-site file uploads:**  
  Supports uploading files to a different domain with cross-site XMLHttpRequests or iframe redirects.
* **Multiple plugin instances:**  
  Allows to use multiple plugin instances on the same webpage.
* **Customizable and extensible:**  
  Provides an API to set individual options and define callBack methods for various upload events.
* **Multipart and file contents stream uploads:**  
  Files can be uploaded as standard "multipart/form-data" or file contents stream (HTTP PUT file upload).
* **Compatible with any server-side application platform:**  
  Works with any server-side platform (PHP, Python, Ruby on Rails, Java, Node.js, Go etc.) that supports standard HTML form file uploads.

## Requirements

### Mandatory requirements
* [jQuery](http://u.720life.cn/g/0a8164b4e54fe9c39d5074c1f90b955107edd69253c714b7b4b0ab058cef2fcb) v. 1.6+
* [jQuery UI widget factory](http://u.720life.cn/g/7376a341fdd27f0a85a9c660aae402964fb8c9a8ba4a087744ba8a0772c1c47780dbf5ddef49428fa4e920e0a851ccd3) v. 1.9+ (included)
* [jQuery Iframe Transport plugin](http://u.720life.cn/g/54145d0471d91890860f7f8463c030467c8c0e8e936246c8b435ca1a17ec418d8b585d97f62ffdc07efc25a14fa7d530df9f91e67e23ba62926ac0625b09e32990478a7fc448fe33acd5ea70547088f848c23b0f63766dfdefe31ed18a2917f1) (included)

The jQuery UI widget factory is a requirement for the basic File Upload plugin, but very lightweight without any other dependencies from the jQuery UI suite.

The jQuery Iframe Transport is required for [browsers without XHR file upload support](http://u.720life.cn/g/54145d0471d91890860f7f8463c030467c8c0e8e936246c8b435ca1a17ec418ded9af66a59783c10f4eb213a36b44bc843309f4d05e5fb2d42ee2921977d9db3f412aab8738759fe52ea7ef8d49d587d).

### Optional requirements
* [JavaScript Templates engine](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304684bff494ce23ab234a6e8238079f6f4f20d70ac211da3e5647de1f170bb336a3) v. 2.5.4+
* [JavaScript Load Image library](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304684bff494ce23ab234a6e8238079f6f4fb8105fa96a2fcaca58779e092d05c434) v. 1.13.0+
* [JavaScript Canvas to Blob polyfill](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304684bff494ce23ab234a6e8238079f6f4ffc73695580a4df733c53c4378fc073ca1f7ebebe0075ddb0129160c629b5c1c0) v. 2.1.1+
* [blueimp Gallery](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046022a81adfc640cf7e05410589e728b1151338dad3dfbf3d18ab0cfea81e5190a) v. 2.15.1+
* [Bootstrap](http://u.720life.cn/g/e23be2821e5181a1a46a005bc6e93d9dc1c8dad0ef41593aa593e12a30fc455b) v. 3.2.0+
* [Glyphicons](http://u.720life.cn/g/98485ec29cb87678a7a5c907fd21b9a8b9ae6647cc2a2256e6e07e4aec46be50)

The JavaScript Templates engine is used to render the selected and uploaded files for the Basic Plus UI and jQuery UI versions.

The JavaScript Load Image library and JavaScript Canvas to Blob polyfill are required for the image previews and resizing functionality.

The blueimp Gallery is used to display the uploaded images in a lightbox.

The user interface of all versions except the jQuery UI version is built with [Bootstrap](http://u.720life.cn/g/e23be2821e5181a1a46a005bc6e93d9dc1c8dad0ef41593aa593e12a30fc455b) and icons from [Glyphicons](http://u.720life.cn/g/98485ec29cb87678a7a5c907fd21b9a8b9ae6647cc2a2256e6e07e4aec46be50).

### Cross-domain requirements
[Cross-domain File Uploads](http://u.720life.cn/g/54145d0471d91890860f7f8463c030467c8c0e8e936246c8b435ca1a17ec418ded9af66a59783c10f4eb213a36b44bc8ad059d1396114b7d47e16aacbcb4f1d4eaaf356466481f92783f9d28552f8b9a) using the [Iframe Transport plugin](http://u.720life.cn/g/54145d0471d91890860f7f8463c030467c8c0e8e936246c8b435ca1a17ec418d8b585d97f62ffdc07efc25a14fa7d530df9f91e67e23ba62926ac0625b09e32990478a7fc448fe33acd5ea70547088f848c23b0f63766dfdefe31ed18a2917f1) require a redirect back to the origin server to retrieve the upload results. The [example implementation](http://u.720life.cn/g/54145d0471d91890860f7f8463c030467c8c0e8e936246c8b435ca1a17ec418d8b585d97f62ffdc07efc25a14fa7d530bbd3b203148f592b69161f86d5500c5f846d24eb5369f9b821d24d45b3c7b83b) makes use of [result.html](http://u.720life.cn/g/54145d0471d91890860f7f8463c030467c8c0e8e936246c8b435ca1a17ec418d8b585d97f62ffdc07efc25a14fa7d530331112e6806e152438ef241bdb654c99968f72403927923411b3111e29e57811) as a static redirect page for the origin server.

The repository also includes the [jQuery XDomainRequest Transport plugin](http://u.720life.cn/g/54145d0471d91890860f7f8463c030467c8c0e8e936246c8b435ca1a17ec418d8b585d97f62ffdc07efc25a14fa7d530196ddf5335676e64e6b6431f9649d84c0f567725e1f856feb7a41d9a4db2f2a4f2c87c821e7553118a187342eac777ff), which enables limited cross-domain AJAX requests in Microsoft Internet Explorer 8 and 9 (IE 10 supports cross-domain XHR requests).  
The XDomainRequest object allows GET and POST requests only and doesn't support file uploads. It is used on the [Demo](http://u.720life.cn/g/5cc336d067ebc308dbdf29ac34e0548a92544b43badc4c496d193ffb0accc084a2aaa4a9e60fdd7c4750f51c5b7fd937) to delete uploaded files from the cross-domain demo file upload service.

## Browsers

### Desktop browsers
The File Upload plugin is regularly tested with the latest browser versions and supports the following minimal versions:

* Google Chrome
* Apple Safari 4.0+
* Mozilla Firefox 3.0+
* Opera 11.0+
* Microsoft Internet Explorer 6.0+

### Mobile browsers
The File Upload plugin has been tested with and supports the following mobile browsers:

* Apple Safari on iOS 6.0+
* Google Chrome on iOS 6.0+
* Google Chrome on Android 4.0+
* Default Browser on Android 2.3+
* Opera Mobile 12.0+

### Supported features
For a detailed overview of the features supported by each browser version please have a look at the [Extended browser support information](http://u.720life.cn/g/54145d0471d91890860f7f8463c030467c8c0e8e936246c8b435ca1a17ec418ded9af66a59783c10f4eb213a36b44bc843309f4d05e5fb2d42ee2921977d9db3f412aab8738759fe52ea7ef8d49d587d).

## License
Released under the [MIT license](http://u.720life.cn/g/4f958e764157e985f98bcd747101b46d6e32a6c141336d74c753aec0719dca813f42d61b954bff2b3e2daa4c80d4e6c9).

## Donations
jQuery File Upload is free software, but you can donate to support the developer, Sebastian Tschan:

Flattr: [![Flattr](https://api.flattr.com/button/flattr-badge-large.png)](https://flattr.com/thing/286433/jQuery-File-Upload-Plugin)

PayPal: [![PayPal](https://www.paypalobjects.com/WEBSCR-640-20110429-1/en_US/i/btn/btn_donateCC_LG.gif)](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=PYWYSYP77KL54)



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ece28994c03e444658721d11485673d8528751896dc15646e0cf8d2e8f2bd0ed9109ca61373baf62bc462128634469b2ee6aeb4ff5b893a47f8d71530472356d3)