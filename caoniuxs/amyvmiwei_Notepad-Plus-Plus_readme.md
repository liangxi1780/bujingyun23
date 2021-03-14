What is Notepad++ ?
===================

[![Join the disscussions at https://notepad-plus-plus.org/community/](https://notepad-plus-plus.org/assets/images/NppCommunityBadge.svg)](https://notepad-plus-plus.org/community/)
&nbsp;&nbsp;&nbsp;&nbsp;[![Join the chat at https://gitter.im/notepad-plus-plus/notepad-plus-plus](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/notepad-plus-plus/notepad-plus-plus?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

Notepad++ is a free (free as in both "free speech" and "free beer") source code
editor and Notepad replacement that supports several programming languages and
natural languages. Running in the MS Windows environment, its use is governed by
GPL License.

Build Status
------------

[![Appveyor build status](https://ci.appveyor.com/api/projects/status/github/notepad-plus-plus/notepad-plus-plus?branch=master&svg=true)](https://ci.appveyor.com/project/donho/notepad-plus-plus)
[![GitHub release](https://img.shields.io/github/release/notepad-plus-plus/notepad-plus-plus.svg)]()

To build Notepad++ from source:
-------------------------------

There are two components that need to be built separately:

 - `notepad++.exe`: (depends on `SciLexer.dll`)
 - `SciLexer.dll` : (with nmake)

You can build Notepad++ with *or* without Boost - The release build of
Notepad++ is built **with** Boost.

Since `Notepad++` version 6.0, the build of `SciLexer.dll` that is distributed
uses features from Boost's `Boost.Regex` library.

You can build SciLexer.dll without Boost, ie. with its default POSIX regular
expression support instead of boost's PCRE one. This is useful if you would
like to debug Notepad++, but don't have boost.

## To build `notepad++.exe`:

 1. Open [`PowerEditor\visual.net\notepadPlus.vcxproj`](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046da89e1afedc49a2c109d932b0310a37bfaa7df20f8510038486fa5904f660060fc707d2e91de3612f76511df7e5be7fa3dd4b17d740b2b081f64b39392f444cf148cd27f41cc1bf498a442ddc6bc3cb9a4b51c84c7837488eaf11a6679cfc415)
 2. Build Notepad++ [like a normal Visual Studio project](http://u.720life.cn/g/16dcfda295bc4929c3b0b0f77d90997820fbf010db724886cc940bd00a0cc160a9a39c7c4e9f64825583a712ae953676c9d62b3ddd5f43eac93db01a376078ee).



## To build `SciLexer.dll` with boost:

Here are the instructions to build SciLexer.dll (for both 32-bit & 64-bit) for Notepad++:

 1. Download the [Boost source code](http://u.720life.cn/g/7c46f0a65728e18ab29a8569eea078df393c36ba07e01a936a66e37c05d87b4d7486f05f394aaf646b455f73ced992ccb0e232359f0346a57546be2f2314df88).
    v1.55 should be used with VS 2013. Then unzip it. In my case, `boost_1_55_0` is copied in `C:\sources\`
 2. Go to `scintilla\boostregex\` then run BuildBoost.bat with your boost path.
    In my case: `BuildBoost.bat C:\sources\boost_1_55_0`
	If you are compiling a 64 bit Scintilla under your *VS2013 x64 Native tool command prompt*, add `-x64` flag.
	In my case: `BuildBoost.bat C:\sources\boost_1_55_0 -x64`
 3. Go in `scintilla\win32\` then run `nmake -f scintilla.mak`



## To build `SciLexer.dll` *without* boost:

This will work with `notepad++.exe`, however some functionality in Notepad++ will be broken.

To build SciLexer.dll without PCRE support (for both 32-bit & 64-bit):

 1. For 32-bit, open a command prompt *for building* ([a.k.a. the *Developer Command Prompt for VS2013*](http://u.720life.cn/g/16dcfda295bc4929c3b0b0f77d90997820fbf010db724886cc940bd00a0cc160d60ac0ed98d2facfb668f2e244727ca189d149e3ff9fee22a24bd15e2d3d44f4)
    - From the IDE, you can do this by right clicking on a file in Solution Explorer,
      and clicking "Open Command Prompt". This will open up a command prompt with all the proper environment variables.
    - From the Windows Start screen/menu, type `Developer Command Prompt for VS2013`,
      and click/select the result.
    - From an *already open* command prompt, run `vcvarsall.bat`
      (e.g. "C:\Program Files (x86)\Microsoft Visual Studio 12.0\VC\vcvarsall.bat").

	For 64-bit, open *VS2013 x64 Native tool command prompt*.

 2. Change directory (`cd` or `pushd`) to `scintilla\win32\`

 3. Build `SciLexer.dll` with one of the following commands:
    - `nmake NOBOOST=1 -f scintilla.mak`         (normal build)
    - `nmake NOBOOST=1 DEBUG=1 -f scintilla.mak` (debugging build)

 4. Copy `SciLexer.dll` from `scintilla\bin\` to the same directory as `notepad++.exe`.
    - For the `Unicode Release` configuration, the output directory
      (where `notepad++.exe` is) is `PowerEditor\bin\`.
    - For the `Unicode Debug` configuration, the output directory
      (where `notepad++.exe` is) is `PowerEditor\visual.net\Unicode Debug\`.


See the [Notepad++ official site](http://u.720life.cn/g/f08efd16883fe42d486befb954ceb20f9c7ecd242bcdf9f2ce877289607ce1db) for more information.

[Notepad++ Contributors](http://u.720life.cn/g/f08efd16883fe42d486befb954ceb20f6f5b7a63f869e4c5c5d5ebd02d7e49a9ba07ef06d349bd18713aff83754c029c)



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ee6cfaf67dffc727e88a5dffdb326bccd9b21843200f6ef98c0dba3b44c36a0b36b99d16c3aa9c2e5d0e0a5fc8cc2d6e82237f9a31a155e7cc9c43347102e4d5b)