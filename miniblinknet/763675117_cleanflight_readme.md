# Cleanflight

![Cleanflight](docs/assets/cleanflight/cleanflight-logo-light-wide-1-240px.jpg)

IMPORTANT NOTICE: Support for STM32F1 based flight controllers will be removed in late 2017, this includes NAZE, CC3D (original) and CJMCU like flight controllers.

Cleanflight is flight controller software for multi-rotor and fixed wings.  The Cleanflight project, and related projects such as Betaflight and iNav are
used on the majority of flight controllers used around the world.  There is no other software used on as many flight-controllers!

* If you're looking for experimental new features and don't mind doing your homework, checkout the [betaflight fork](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046e669abb644e905060a3c546cb5996a8c538147c99c989a24d6be8a28271a97e0).
* If you're looking for advanced navigation features then check out the [iNav fork](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046048ae698cb804472bfc450f84587d8080d4e9462bbf3bcb0345eb13db0e5d0b1).
* All other users should use Cleanflight.

## Features

Features:

* Awesome flight performance as trusted by the majority of Acrobatic and Racing Drone pilots.
* Support for modern STM32 based processors F1/F3/F4/F7.
* Support for modern accelerometer/gyro/barometer/compass sensors.
* Support for modern ESC technologies DSHOT/ONESHOT and legacy PWM.
* Support for Multi-color RGB LED strip support.
* Advanced on-board telemetry logging (Blackbox).
* Wide support of receivers (SBus/iBus/SumD/SumH/PPM/PWM/CRSF/JetiExBus)
* Wide support of telemetry protocols (FrSky/SmartPort/S.Port/HoTT/iBus/LTM/MavLink/CRSF/SRXL).
* Built-in OSD support & configuration without needing third-party OSD software/firmware/comm devices.
* Support for external OSD slave systems.
* VTX support (RTC6705/Unify Pro(SmartAudio)/IRC Tramp/etc).
* and MUCH, MUCH more.

## Installation & Documentation

* Cleanflight documentation - https://github.com/cleanflight/cleanflight/tree/master/docs
* Betaflight Wiki -  https://github.com/betaflight/betaflight/wiki 

## Support

Your first place for support are the [Cleanflight forums on RCGroups](http://u.720life.cn/g/b3ff97d3ed7b87310466c9bbba11911b70a3cb9dea53342adac59bc89c53a04cd1b141e02173ff7d7ef09d96c75b3856f6f5d8cb31f2253e14cd9bf46695cf599b26d5b6c6ace92f364f5c4ece37a90182560408496a629bc47e9ac90d1b02386f13e7f96bd0871f15dbba96f8c6254e3d65199a6e6762339df7df07108be7af)

The Github issue tracker is NOT for end-user support.

## IRC Support and Developers Channel

There's a dedicated Cleanflight IRC channel on the Freenode IRC network. Many users and some of the developers frequent there, and it is a helpful and friendly community - but there are two important things to keep in mind: First and most importantly, please go ahead and ask if you have questions, but **make sure you wait around long enough for a reply**. Next, sometimes people are out flying, asleep or at work and can't answer immediately, even though they are present in the channel. This is how IRC works: Many people stay logged in, even though they are not actively participating in the discussion all the time. Have a seat, grab a drink and hang around if it's a quiet time of day.

irc://irc.freenode.net/#cleanflight

If you are using Windows and don't have an IRC client installed, take a look at [HydraIRC](http://u.720life.cn/g/bd882b43eb1964f08fbb9a9afcd7a253a2b7bb682cdee57ae90d6532922d62dc).

There's a dedicated Slack chat channel for betaflight here:

https://slack.betaflight.com/

Etiquette: Don't ask to ask and please wait around long enough for a reply - sometimes people are out flying, asleep or at work and can't answer immediately.

## Videos

There is a dedicated Cleanflight YouTube channel which has progress update videos, flight demonstrations, instructions and other related videos.

https://www.youtube.com/playlist?list=PL6H1fAj_XUNVBEcp8vbMH2DrllZAGWkt8

Please subscribe and '+1' the videos if you find them useful.

## Configuration Tool

To configure Cleanflight you should use the [Cleanflight-configurator GUI tool](http://u.720life.cn/g/011bcbff60d4bdcdf5b89348f1b4fec4ea1629e5a5711d79823204fb51bba15ee435176a9deba3fddf27c757d02e84b5ff8718288a6fdd85cdd37db401122bd7dee13eba127fd42ea1a5d12a41a60d8712796a2b8baee59e3a3bebce56e4f297049a2a24f655f7aa0c2ca0f28964a0f7) (Windows/OSX/Linux).

The source for it is here:

https://github.com/cleanflight/cleanflight-configurator

Note: the configurator auto-updates itself if installed using Chrome, if you need an old version to use old firmware then you can get them here:

https://github.com/cleanflight/cleanflight-configurator/releases


## Contributing

Contributions are welcome and encouraged.  You can contribute in many ways:

* Documentation updates and corrections.
* How-To guides - received help? Help others!
* Bug reporting & fixes.
* New feature ideas & suggestions.

See [CONTRIBUTING.md](CONTRIBUTING.md)

## Developers

Please refer to the development section in the [docs/development](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046e7a70cff1bca7f4f18d0a6097a26e034e078e49ee1bedba8ac5f528a1a0b241e324c77f8009476d0eadc0d1fde375ca957a30511492482ea2929e7dbc560d83d) folder.

TravisCI is used to run automatic builds: https://travis-ci.org/cleanflight/cleanflight

https://travis-ci.org/cleanflight/cleanflight

[![Build Status](https://travis-ci.org/cleanflight/cleanflight.svg?branch=master)](https://travis-ci.org/cleanflight/cleanflight)

## Cleanflight Releases
https://github.com/cleanflight/cleanflight/releases

## Open Source

Cleanflight is software that is **open source** and is available free of charge without warranty to all users.

The license is GPL3.

## Project/Fork History

Cleanflight is forked from Baseflight, which is now dead, all primary development happens in Cleanflight, betaflight and iNav forks.

Cleanflight v2.x -> betaflight -> cleanflight v1.x -> baseflight -> multiwii

## Contributors

Thanks goes to all those whom have contributed to Cleanflight and its origins.

Primary developers:
* Dominic Clifton (hydra) - *cleanflight founder*
* Boris B (borisbstyle) - *betaflight founder*
* digitalentity - *inav founder*
* Martin Budden (martinbudden)
* Jason Blackman (blckmn)

Big thanks to current and past contributors:
* **Alexinparis** (for MultiWii),
* **timecop** (for Baseflight),
* **Sambas** (for the original STM32F4 port).
* Bardwell, Joshua (joshuabardwell)
* ctzsnooze
* Höglund, Anders (andershoglund)
* Ledvina, Petr (ledvinap) - **IO code awesomeness!**
* kc10kevin
* Keeble, Gary (MadmanK)
* Keller, Michael (mikeller) - **Configurator brilliance**
* Kravcov, Albert (skaman82) - **Configurator brilliance**
* MJ666
* Nathan (nathantsoi)
* ravnav
* sambas - **bringing us the F4**
* savaga
* Stålheim, Anton (KiteAnton)
* prodrone - **failsafe work**
* **ctn** - **for the original Configurator**

And many many others who haven't been mentioned....




 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ecb4806e0aed797124e3b5f6ade0212619241b3b6fd2025a603f6900c478f0dfda01416f7a8ec278208915cd5325d0e06)