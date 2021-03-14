# maze-tower

[![build](https://img.shields.io/badge/build-passing-brightgreen.svg)](https://gitee.com/dinghaoran/maze-tower) [![release](https://img.shields.io/badge/release-v1.0-blue.svg)](https://gitee.com/dinghaoran/maze-tower/releases) [![platform](https://img.shields.io/badge/platform-win-9cf.svg)](https://gitee.com/dinghaoran/maze-tower/releases) [![license](https://img.shields.io/badge/license-MIT-brightgreen.svg)](https://gitee.com/dinghaoran/maze-tower)

>  小学期自制3D迷宫小游戏

### 环境要求

- 编程语言：C++
- 编程环境：Visual Studio 2019 + EasyX
- 编译平台：Windows 10

### 项目简介

**关键词一：迷宫。** 相信对于迷宫，大家都不陌生。指的是充满复杂通道，很难找到从其内部到达入口或从入口到达中心的道路，道路复杂难辨，人进去不容易出来的建筑物。迷宫的游戏规则即为：从入口开始任意行走，找到出口就判定游戏胜利。它作为一种规则简单而又有趣的小游戏，风靡世界。

**关键词二：3D视角。** 在游戏中，我们试着采用模拟3D视角的技术，显示3D图形，尽量使之看起来像真实世界，即真人在一个偌大的现实迷宫中来回穿梭，以在游戏中达到身临其境之感。

### 操作说明

在开始菜单，点击`START GAME`按钮将开始新的一局游戏，点击`CONTINUE`按钮将继续上一局游戏。

进入游戏后，按`W`键前进，按`A`键向左转，按`S`键向后转，按`D`键向右转，按`Q`键退出游戏。

### 游戏元素

有一天恶龙抓走了公主。就像许多冒险故事的开端一样，有一天，恶龙抓走了公主。它巨大的双翼遮云蔽日，吐息间可将整片森林化为灰烬。红灰色的皮肤，深绛色的头发，若隐若现的鳞片，肌肉纠结的手臂，还有高大的身躯和无法消失的龙尾和骨翼。它还杀死了许多士兵，杀死了每一个前来营救公主的人。小小王国里再也没有人敢去挑战它，国王和王后因为失去了小女儿而终日垂泪。于是，就像许多冒险故事一样，有一位英勇的骑士来拯救公主了。

主界面的左侧为3D视角区域，即玩家在迷宫中探索时的视野范围。主界面的右上角为小地图，供玩家进行合理规划路线。主界面的右下角显示有当前层数，供玩家参考。

在地图中有：墙壁(`wall`)、空地(`blank`)、上行楼梯(`upstairs`)、下行楼梯(`downstairs`)、传送门(`portal`)。其中，墙壁是无论如何也无法穿过的实体方块，空地是玩家可以自由行进的区域，上行楼梯可以进入上一层，当然下行楼梯自然可以回到下一层。传送门则在地图中会成对出现，进入一个传送门，玩家就会被瞬间传送至另一个完全相同的传送门处。注意传送门是本游戏过关的核心，需要巧妙运用。

### 关于

> 如果你屈服于恐惧，你就找不到任何答案。


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ea120741ac00d448936c711ae49ea01c440820742e72a2bb208e3bd90a709c82d8aa48a026e45b16aeb32c643b59c0b47)