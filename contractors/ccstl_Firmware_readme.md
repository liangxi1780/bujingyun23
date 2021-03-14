# PX4 Drone Autopilot

[![Releases](https://img.shields.io/github/release/PX4/Firmware.svg)](https://github.com/PX4/Firmware/releases) [![DOI](https://zenodo.org/badge/22634/PX4/Firmware.svg)](https://zenodo.org/badge/latestdoi/22634/PX4/Firmware)

[![Build Status](http://ci.px4.io:8080/buildStatus/icon?job=PX4/Firmware/master)](http://ci.px4.io:8080/blue/organizations/jenkins/PX4%2FFirmware/activity)

[![Slack](https://px4-slack.herokuapp.com/badge.svg)](http://slack.px4.io)

This repository holds the [PX4](http://u.720life.cn/g/fdb48169940789ea44a0e199fe15aaab) flight control solution for drones, with the main applications located in the [src/modules](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046a50de737ecd764e71eae4128c45a89c4c6fc5d03cd876158f763ff1e24badbff2e8ea8b5213df360f8f957c115971639) directory. It also contains the PX4 Drone Middleware Platform, which provides drivers and middleware to run drones.

* Official Website: http://px4.io (License: BSD 3-clause, [LICENSE](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046a50de737ecd764e71eae4128c45a89c4600b1b48247cd6c60c5e5825fa6b6ae2781a11cc4048862fa5c64e75b68a07d6)
* [Supported airframes](http://u.720life.cn/g/d027d664162e93e37bec3524233d06b8ee434dc6c7a4957a7c68fb14649094d01b5fae414f3550b983de4a4c795e49f5281616db0e1452b9db820ec24d602378) ([portfolio](http://u.720life.cn/g/08b87e370f9fe67ff38a3ae0a4e937963b0378c431284e43776bbb4042327ef4)
  * [Multicopters](http://u.720life.cn/g/d027d664162e93e37bec3524233d06b8ee434dc6c7a4957a7c68fb14649094d01b5fae414f3550b983de4a4c795e49f56bc4af31be6b085e79de7c7ee1d5f280)
  * [Fixed wing](http://u.720life.cn/g/d027d664162e93e37bec3524233d06b8ee434dc6c7a4957a7c68fb14649094d01b5fae414f3550b983de4a4c795e49f58a736bc0399a2005db69a5e7a2026be8)
  * [VTOL](http://u.720life.cn/g/d027d664162e93e37bec3524233d06b8ee434dc6c7a4957a7c68fb14649094d01b5fae414f3550b983de4a4c795e49f502ba4e94c2f7cf95a54db1f244e7fe4e)
  * many more experimental types (Rovers, Blimps, Boats, Submarines, etc)
* Releases: [Downloads](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046a50de737ecd764e71eae4128c45a89c49d20c93aad3617de3ac2ad1a51a6efbc)


## PX4 Users

The [PX4 User Guide](http://u.720life.cn/g/d027d664162e93e37bec3524233d06b8db989d0ce7112b6809d508afd30d40c4) explains how to assemble [supported vehicles](http://u.720life.cn/g/d027d664162e93e37bec3524233d06b8ee434dc6c7a4957a7c68fb14649094d01b5fae414f3550b983de4a4c795e49f5281616db0e1452b9db820ec24d602378) and fly drones with PX4.
See the [forum and chat](http://u.720life.cn/g/d027d664162e93e37bec3524233d06b8563c00b5d9563d8a3b7c05089915ad51) if you need help!


## PX4 Developers

This [Developer Guide](http://u.720life.cn/g/ff533924e9d4f5197c2d33880dfb1c7b89c10f364de118e80b39433136754c72) is for software developers who want to modify the flight stack and middleware (e.g. to add new flight modes), hardware integrators who want to support new flight controller boards and peripherals, and anyone who wants to get PX4 working on a new (unsupported) airframe/vehicle.

Developers should read the [Guide for Contributions](http://u.720life.cn/g/ff533924e9d4f5197c2d33880dfb1c7bb1a2637ca59cade47b41f2889bd8fe1be2cee49e034fc034983c2b43f5e66f06).
See the [forum and chat](http://u.720life.cn/g/ff533924e9d4f5197c2d33880dfb1c7b180b3542f136cefb2842e4eead883aac) if you need help!


### Weekly Dev Call

The PX4 Dev Team syncs up on a [weekly dev call](http://u.720life.cn/g/ff533924e9d4f5197c2d33880dfb1c7bb1a2637ca59cade47b41f2889bd8fe1b5730a402e62b66188f7b7efd4e9dc061).

> **Note** The dev call is open to all interested developers (not just the core dev team). This is a great opportunity to meet the team and contribute to the ongoing development of the platform. It includes a QA session for newcomers. All regular calls are listed in the [Dronecode calendar](http://u.720life.cn/g/f74b0fc30c3c2b7c7185cfd781f0f556662345f2fac8cec3c0d3fd3ccacffa24ac9518f731075f60d4aa77a6cfb71757).


## Maintenance Team

  * Project: Founder - [Lorenz Meier](http://u.720life.cn/g/54145d0471d91890860f7f8463c030467b41107030ac6588a28a4fbefc5d4c21), Architecture: [Daniel Agar](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304607477b4fb4c486cd53e9614adc7ce7e2)
    * [Dev Call](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046a50de737ecd764e71eae4128c45a89c4229377c23aada149caf7e20bad98ace2) - [Ramon Roche](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046b00dacb8e5ab15551b329555369942e1)
  * Communication Architecture
    * [Beat Kueng](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046408118ac18aa926eb35f3e4becd5742d)
    * [Julian Oes](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046782c2fc73af8417832aba2a83dabb23e)
  * UI in QGroundControl
    * [Gus Grubba](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046d6ca7fb0734ffbccdd4df0306d9ee1e3)
  * [Multicopter Flight Control](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046a50de737ecd764e71eae4128c45a89c4124e8b4fcf34041725cca144ac6e06d0abfbbad92da973f120e4f98b17143589)
    * [Mathieu Bresciani](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304614db89507d9233ef12ce71c245327826)
  * [Multicopter Software Architecture](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046a50de737ecd764e71eae4128c45a89c4124e8b4fcf34041725cca144ac6e06d0abfbbad92da973f120e4f98b17143589)
    * [Matthias Grob](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046bd61ed000adc52067f9f093c82d76762)
  * [VTOL Flight Control](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046a50de737ecd764e71eae4128c45a89c4cca5f098c3f5cc6832859dda87606913)
    * [Roman Bapst](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304673407f009b9f8ca32bfca63407fb2c42)
  * [Fixed Wing Flight Control](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046a50de737ecd764e71eae4128c45a89c49eb9d4f7c8485122bbeb7c1798cc3d7c)
    * [Roman Bapst](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304673407f009b9f8ca32bfca63407fb2c42)
  * OS / NuttX [David Sidrane](http://u.720life.cn/g/54145d0471d91890860f7f8463c030461775d4f21d06acbc3d582fcb5856e00c)
  * Driver Architecture [Daniel Agar](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304607477b4fb4c486cd53e9614adc7ce7e2)
  * Commander Architecture [Julian Oes](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046043da3a4af3db4fe59c923dfe9a9973d)
  * [UAVCAN](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046a50de737ecd764e71eae4128c45a89c437b1c8f51ce486a5abf0f044cb90f9e4) [Daniel Agar](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304607477b4fb4c486cd53e9614adc7ce7e2)
  * [State Estimation](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046a50de737ecd764e71eae4128c45a89c4dbd4dbde5798d60edb654dba4e06f83f378880de648de06635b62e95cc381e97294dee6fcaa20546712f0bece8bb1f2886a200a91ae2d085b04fb8c0dfcd0791) - [Paul Riseborough](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046e2fd797623ae87e500d1e4aafcd7ebec)
  * Vision based navigation
    * [Julian Kent](http://u.720life.cn/g/54145d0471d91890860f7f8463c030466e0d047cd7d812f648ad2cefde56cd7f)
  * Obstacle Avoidance - [Martina Rivizzigno](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304694cb8f35edfd482d82a9b4a42a255c2d)
  * RTPS/ROS2 Interface - [Nuno Marques](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046d417924e391f5c1a81ad2b541355318a)

See also [About Us](http://u.720life.cn/g/9f6b02f0a2edacaed5d1d844522fe9d209f5a8517941fc81741bf6cb53e0d9840ec95fda02b4ba8edb4d69bbc2e57d7e) (px4.io) and the [contributors list](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046a50de737ecd764e71eae4128c45a89c492cd1020b625b9f34bbf04e0990b91ee37e8f6e09ba7ce3ba0b56f3094105295) (Github).

## Supported Hardware

This repository contains code supporting these boards:
  * [Snapdragon Flight](http://u.720life.cn/g/d027d664162e93e37bec3524233d06b8c84a062b4d4e81cdec4fdfc253e7ba64e8719d715499ee4f6a7fe168839e82e7a422ebcd9d2cc78583448d11e62702f8)
  * [Intel Aero](http://u.720life.cn/g/d027d664162e93e37bec3524233d06b8c84a062b4d4e81cdec4fdfc253e7ba641a37cc28848dcb80f02ff6ff61679e51ecd153cb7e3a18cd8d5bcf02778aba80)
  * [Raspberry PI with Navio 2](http://u.720life.cn/g/d027d664162e93e37bec3524233d06b8c84a062b4d4e81cdec4fdfc253e7ba64517eb6d47d061a72ef5e457063c5de2f964cc8a58d9e5b9d82e8e37b27c4552ea87e34a5f78ba87cdeb45e799b8e47ea)
  * [Parrot Bebop 2](http://u.720life.cn/g/ff533924e9d4f5197c2d33880dfb1c7bce0768c9765f597fdfccff9c96290507ecb0dab0bddb6d33dfeeb73cc1f3f1fd)
  * FMUv2
    * [Pixhawk](http://u.720life.cn/g/d027d664162e93e37bec3524233d06b8c84a062b4d4e81cdec4fdfc253e7ba64685cf9bfa677f9abda7f89843159d0d9a17d587b374c657adaa03449136f5ff0)
    * [Pixhawk Mini](http://u.720life.cn/g/d027d664162e93e37bec3524233d06b8c84a062b4d4e81cdec4fdfc253e7ba64685cf9bfa677f9abda7f89843159d0d97bccf9539976b0c0b6bff95531094c01)
    * [Pixfalcon](http://u.720life.cn/g/d027d664162e93e37bec3524233d06b8c84a062b4d4e81cdec4fdfc253e7ba64614dd0cdc242b95225918ea80dd64889a931280041ea5775b118ff19f4a84dde)
  * FMUv3 [Pixhawk 2](http://u.720life.cn/g/d027d664162e93e37bec3524233d06b8c84a062b4d4e81cdec4fdfc253e7ba64685cf9bfa677f9abda7f89843159d0d9b8f6b5c8c9196e25cb80dc4e9800d0d3)
  * FMUv4
    * [Pixracer](http://u.720life.cn/g/d027d664162e93e37bec3524233d06b8c84a062b4d4e81cdec4fdfc253e7ba64a1675c35f35b48d7a4dfc44dbfa3ce58fb10056aea958fc4847cdbd73ce9a82d)
    * [Pixhawk 3 Pro](http://u.720life.cn/g/d027d664162e93e37bec3524233d06b8c84a062b4d4e81cdec4fdfc253e7ba64685cf9bfa677f9abda7f89843159d0d96379bb6b82ddfb48f6abbc50b8c13ad3)
  * FMUv5 (ARM Cortex M7)
    * [Pixhawk 4](http://u.720life.cn/g/d027d664162e93e37bec3524233d06b8c84a062b4d4e81cdec4fdfc253e7ba64685cf9bfa677f9abda7f89843159d0d99a35a1e737dd364770100d05c5883135)
    * [Pixhawk 4 mini](http://u.720life.cn/g/d027d664162e93e37bec3524233d06b8c84a062b4d4e81cdec4fdfc253e7ba64685cf9bfa677f9abda7f89843159d0d927088883f2efb3a96505b3b2408ddb30)  
  * [Airmind MindPX V2.8](http://u.720life.cn/g/b4f71cecdfe320d3d9c141cb2049c801be74266dd55c555867ea935c111e81449a4de3809f7b51468c992adb74c209c9fb59b331c8067aa0ee1659f9ec38855d)
  * [Airmind MindRacer V1.2](http://u.720life.cn/g/1188e6f7423b7ecfb5e9e83b91c3b8b2c4184ed512271073710a3b8ae28518583476968ab0a31862a11fa50282487d2ebdaf1d9cffd493f8d18eec0d91f8e466790ebbc72fd1059d1b4e16e7f42d3447)
  * [Bitcraze Crazyflie 2.0](http://u.720life.cn/g/d027d664162e93e37bec3524233d06b8c84a062b4d4e81cdec4fdfc253e7ba6438bf6fee0f1ebdd23734d90054d764701abdd34c5f47709ae21e2337fb9f005b)

Additional information about supported hardware can be found in [PX4 user Guide > Autopilot Hardware](http://u.720life.cn/g/d027d664162e93e37bec3524233d06b8c84a062b4d4e81cdec4fdfc253e7ba643544191f1aea5030eb9ebddccb8d8a37).

## Project Roadmap

A high level project roadmap is available [here](http://u.720life.cn/g/f74b0fc30c3c2b7c7185cfd781f0f556dbdccbbe25039e310b66f552616d79f474cdb7a246b28a0731563149b69babf8).



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ecffabf5a6f8fd4361170041f56c205832a47243fff3ae7d3df3fe353d02ff8fa019b56fb08040e82648ceef3ba22e57d)