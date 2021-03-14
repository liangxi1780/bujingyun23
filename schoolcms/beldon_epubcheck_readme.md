[![Current Release](https://img.shields.io/github/release/w3c/epubcheck.svg)](https://github.com/w3c/epubcheck/releases/latest) [![Github All Releases Downloads](https://img.shields.io/github/downloads/w3c/epubcheck/total.svg?colorB=A9A9A9)](https://github.com/w3c/epubcheck/releases/) [![Build Status](https://api.travis-ci.com/w3c/epubcheck.svg?branch=master)](https://travis-ci.com/github/w3c/epubcheck)


EPUBCheck
=========

EPUBCheck is a tool to validate the conformance of EPUB publications against the EPUB specifications.
EPUBCheck can be run as a standalone command-line tool or used as a Java library.

EPUBCheck is open source software, maintained by the [DAISY Consortium](http://u.720life.cn/g/859fb6062f92d372b21cef0b7f2aaa1ed4a44ee967fd719f64b86f066d7ea385) on behalf of the [W3C](http://u.720life.cn/g/098598e75704e07d68eba0aa885b4c2b9882a7699f12eec42da9ca85124e1f84d2bea255ed9518320eb648b5abccbe7619f115d2b4ce7417d580a883b2a1bfd6).


**We Need Your Support!!**  
Financial support is critical to the development of EPUBCheck, the tool we all use to validate EPUB files.
We need to make sure that the resources are adequate to both update the tool and provide for its continued maintenance over the next two years;
please [help us fund and support EPUBCheck](http://u.720life.cn/g/098598e75704e07d68eba0aa885b4c2b9882a7699f12eec42da9ca85124e1f84d2bea255ed9518320eb648b5abccbe7619f115d2b4ce7417d580a883b2a1bfd6), and join the [list of donators](#donators)!


## Downloads

Check the [releases page](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046fb871c91f932b11cfad39a1e5c00a5d3996e2b115368b359ed5c77669216b67c) to get the latest distribution.

[EPUBCheck 4.2.4](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046fb871c91f932b11cfad39a1e5c00a5d311b7a69ff7c3923b08d286fec3921b469e2c3ad019d2b624aec107c24cab9a1c) is the latest production-ready release, to be used to validate both EPUB 2 and 3 files. EPUB 3 publications are checked against the EPUB 3.2 family of specifications.

## Documentation

Documentation on how to **use** EPUBCheck, to **contribute** to the project or to **translate** messages is available on the [EPUBCheck wiki](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046fb871c91f932b11cfad39a1e5c00a5d39693a3cfa78605f2b0887acba316c719).

Technical discussions are held on our public [mailing list](http://u.720life.cn/g/9ab72d4f851b87c0cbd141ac4a33baf98bad2d9f19ab9b8eecbc5efa4d182b1f78e55dce1687e586cd4af111dda4cbb0c77b4bfd7ff0c250ae1617af166984ab). To subscribe to the mailing list, send an email with subject `subscribe` to [public-epubcheck-request@w3.org](mailto:public-epubcheck-request@w3.org?subject=subscribe). To participate in the discussion, simply send an email to [public-epubcheck@w3.org](mailto:public-epubcheck-request@w3.org).

Historical archives of discussions prior to October 2017 are stored at the old [EPUBCheck Google Group](http://u.720life.cn/g/941693b557d072bb769494a6a61fcd979ee9fee4d4fd0c2a6b8a30bc68eade218fef50cbaa0d662575270f8c17653461084e859ac80d70c3ba0bc64c948c65a6).

## Building EPUBCheck

To build epubcheck from the sources you need Java Development Kit (JDK) 1.7 or above and [Apache Maven](http://u.720life.cn/g/bc840264f6cc23df0a8935b6f2922fec747e8988e9d6774b642901b9662b323f) 3.0 or above installed.

You will also need Python to be able to run the BookReporter and related tools.

Build and run tests:

```
$ mvn clean install
```
Will copy `.*jar` files and packages to `target/` folder...

## Credits

Most of the EPUBCheck functionality comes from the schema validation tool [Jing](http://u.720life.cn/g/593edf4ef5a6168459c89200a6f6390775c20b37bd7821067ecb2eb00dbba481bcb8a1df0ab815e17d2ce5d32692ecb2) and schemas that were developed by [IDPF](http://u.720life.cn/g/b0c4855f47b6eb41e809e2a6ca509b265aea230e637cd5779e5fb8b802293792) and [DAISY](http://u.720life.cn/g/859fb6062f92d372b21cef0b7f2aaa1e78993b1ddc71b5c52cd6337ad67fd36c). Initial EPUBCheck development was largely done at [Adobe Systems](http://u.720life.cn/g/33a66496da697b2ff049fee03ca0b19184b1351a8a7c14a5c6f1ac462a2fd8ac).

Initial (pre 2012) authors and contributors to EPUBCheck include: Peter Sorotokin, Garth Conboy, Markus Gylling, Piotr Kula, Paul Norton, Jessica Hekman, Liza Daly, George Bina, Bogdan Iordache, Ionut-Maxim Margelatu

EPUBCheck 4.0 was largely developed by
* [DAISY](http://u.720life.cn/g/859fb6062f92d372b21cef0b7f2aaa1e78993b1ddc71b5c52cd6337ad67fd36c), namely: Romain Deltour, Markus Gylling
* [Barnes & Noble](http://u.720life.cn/g/e51753f52807f6566c7e6a7b473fc415af64f018956c77427fbfa9cd342c0de5), namely: Steve Antoch, Arwen Pond

Regular contributors between 2012 and 2017 include: Romain Deltour, Tobias Fischer, Markus Gylling, Satoshi KOJIMA, Thomas Ledoux, Masayoshi Takahashi

Many thanks are also extended to the numerous people who have contributed to the evolution of EPUBCheck through bug reports and patches!

## Donators

The following organizations are supporting the development of EPUBCheck by their contribution to the [fundraising initiative](http://u.720life.cn/g/098598e75704e07d68eba0aa885b4c2b9882a7699f12eec42da9ca85124e1f84d2bea255ed9518320eb648b5abccbe7619f115d2b4ce7417d580a883b2a1bfd6):

 
     
     
     
     
     
     
     
     
     
     
     
     
     
     
     
     
     
     
 

## License

EPUBCheck is made available under the terms of the [3-Clause BSD License](http://u.720life.cn/g/ba059582536a397f7c573b87c8bea647898b703f1d1097e692abe08871b5648c7274a99f7f54265eb113b7e932f786e6)



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e69a3b396add315182581ed22e0d072041e7adf82080ea2c793d1edd6531e57f85d53df58fd8293dd2d2f69cf3bc0e92c)