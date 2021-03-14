# EverVim: The Ultimate Vim Distribution
![EverVim](https://img.shields.io/badge/Coded%20with-EverVim-bd93f9.svg?style=flat-square)

![evervim-header-1](https://i.imgur.com/pkMiOSl.png "EverVim with VimR on macOS")
![evervim-header-2](https://i.imgur.com/2P267n1.png "EverVim with GVIM on Windows")

* * *

## | [About](http://u.720life.cn/g/54145d0471d91890860f7f8463c030468014a7e217c5da6f4f641c2d8e52a61d5b73f814bfcad986f70d904b9e0161cd7ed3c280a1964deeb781546d98e901b5) | [Installation](http://u.720life.cn/g/54145d0471d91890860f7f8463c030468014a7e217c5da6f4f641c2d8e52a61d5b73f814bfcad986f70d904b9e0161cdfe9790e35eb6f3fd75056e20b95fa61e94da542e4b39d11225a2008b510176ca) | [Features](http://u.720life.cn/g/54145d0471d91890860f7f8463c030468014a7e217c5da6f4f641c2d8e52a61d5b73f814bfcad986f70d904b9e0161cd80bc34ad73c5d19917a78b47cd94e49510c5949712d1ceaaa7ea968e7d1c3767) | [ScreenShots](http://u.720life.cn/g/54145d0471d91890860f7f8463c030468014a7e217c5da6f4f641c2d8e52a61d5b73f814bfcad986f70d904b9e0161cd3eb114af91a6de73d9146b049c06e51399a1daba1f0754e642efc81c0e89b595) | [Documentation!](http://u.720life.cn/g/54145d0471d91890860f7f8463c030468014a7e217c5da6f4f641c2d8e52a61d075eae0563428fb689f25cf48cd4705e) | [License](https://github.com/LER0ever/EverVim/blob/master/README.md#license) |

## About
EverVim is the ultimate vim distribution that supports **NeoVim**, Vim, GVim and MacVim. It ships with tons of powerful features through vim plugins, which makes it easy to get started for both newcomers and experienced users.

The distribution is completely customizable using a ~/.EverVim.vimrc Vim config files.

EverVim started as a fork of spf13-vim, which is great but not actively maintained any more. Unlike spf13-vim, EverVim always keeps its modern features up-to-date. It uses [Vim-Plug](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304628345337990118a9ac85e9243586ceb6818460a6e713a7ca39f366111d85c27e) as a plugin manager, which is async and is about 10x faster than Vundle. Keeping your plugins always up to date is just a command away. Vim-Plug uses a plugin bundle so that having lots of them won't mess up the folder structure.

The default config of EverVim is powerful and easy to use just out of the box, and is suitable for most vim users. Customization is easy as well. With `.EverVim.vimrc` file, you can customize the whole collection without modify the original files. That means you're still able to update the EverVim config using `git pull` without compromizing your own modification.

## Installation
### Detailed installation instruction
### | [Linux](http://u.720life.cn/g/54145d0471d91890860f7f8463c030468014a7e217c5da6f4f641c2d8e52a61d2cf3f7723a61ebf8659413aebd4a7fc48c471b525a896be8afe543a5d7e09969) | [macOS](http://u.720life.cn/g/54145d0471d91890860f7f8463c030468014a7e217c5da6f4f641c2d8e52a61d2cf3f7723a61ebf8659413aebd4a7fc4bec67ec4d09b4fe8ab516af41019ad23) | [Windows](http://u.720life.cn/g/54145d0471d91890860f7f8463c030468014a7e217c5da6f4f641c2d8e52a61d2cf3f7723a61ebf8659413aebd4a7fc4df260d74bdc7ba60702be437ee60eff8) |
Finished the installation above?  
Before you started, please read the [Wiki](http://u.720life.cn/g/54145d0471d91890860f7f8463c030468014a7e217c5da6f4f641c2d8e52a61d075eae0563428fb689f25cf48cd4705e) to have an overview about some of EverVim's essential keybindings and plugins.

* * *

##### tl;dr. A brief how-to-install
 
 0. Still 
 You are strongly encouraged to use the full instruction on your first installation of EverVim. 
 
 
 1. Install prerequisites and patched font 
 Download and install the [Knack Nerd Font](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046048938cc02336bcfc8d13779c773ff7efab64a9318a9c520561a2b093c6d95a458bddc2ae3d64efa97ff10fc4601577daee3399a175a1317ec8a252624e314b0afb92c3147f08c5b8f660416df743e94ab1d65200b87eb25ac8eee1b9b787e21bce88851226285a320a5ccef29b7af7d0f346bb5057971af189d0593170952fe) 
 Make **git, curl** is on your system. Python is also needed for Linux. Ctags is optional but highly recommended. 
 

 
 2. Clone and Boot   
 git clone https://github.com/LER0ever/EverVim ~/.EverVim 
 cd .EverVim 
 sh Boot-EverVim.sh or .\Boot-EverVim.ps1 
 
 
 3. Install the plugins 
 Fire up your vim 
 Wait for Plugin Initiation to finish 
 Restart Vim. 
 

### Keep EverVim up-to-date
Press **`u`** at EverVim start screen. Configuration and plugins will be automatically updated.

# Features
### Cross Platform
- Support Vim 7.4.x, Vim 8, MacVim and of course Neovim
- Tested under all platforms
	- Windows (gvim, vim, neovim-qt, Oni)
	- Linux (neovim, neovim-qt, vim, gvim, neovim-gtk, Oni)
	- macOS (MacVim, VimR, Oni)
	- BSD (vim)
	- Android (neovim, vim under Termux)

### Powerful & Easy to use
- Easy to setup, just one bash away.
- All the wonderful features are enabled out of the box
- Full IDE-like support for C/C++, Go, Rust, javascript, etc.
- Use YouCompleteMe by default, neocomplete as a windows fallback
- NERDTree as file explorer
- Git operation right inside vim with fugitive
- Syntastic provides syntax check on every save
- Jump to anywhere in 2 key with EasyMotion
- Markdown CTags support via markdown2ctags

### Pleasant to code
- Fancy Dracula Theme
- Lightline for statusline and tabline
- TagBar for code navigation
- Startup screen to pick up recent files (using Startify)

### Asynchronous
- Use Vim-Plug as vim plugin manager
	- Parallel installation
	- 10x faster initial PlugInstall

### Other Awesomeness
- Collaboration using CoVim

## ScreenShots
#### Updated screenshots at [Wiki/Gallery](http://u.720life.cn/g/54145d0471d91890860f7f8463c030468014a7e217c5da6f4f641c2d8e52a61d57469c7f250005f58ea639a930701b0a)
##### Startup Screen (under NeoVim-Qt)
![evervimstartify](http://i.imgur.com/SHu2yZv.png)
##### NeoVim Terminal
![evervimterm](http://i.imgur.com/lQVWBTH.png)
##### NeoVim GTK
![evervimnvimgtk](http://i.imgur.com/Kp2q00a.png)
##### GVim
![evervimgui](http://i.imgur.com/s8ga2Cv.png)
##### Older Shots
![evervimold](http://i.imgur.com/l8oK1Mj.png)

## [Documentation](http://u.720life.cn/g/54145d0471d91890860f7f8463c030468014a7e217c5da6f4f641c2d8e52a61d5b73f814bfcad986f70d904b9e0161cd363e72e7781dee4e1bd378b923b0d3f6)

## License
EverVim is licensed under **Apache 2.0**

This repo contains part of code from [spf13-vim](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046cd4bb0fc872cc32576eae57bd26a295631a41215ac118cda4b2cce0caa18cf29), 
which is also licensed under [Apache 2.0](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046cd4bb0fc872cc32576eae57bd26a2956df6b07c2fcae25e90616724cf73004937379bfdc5061857d159c1437f3c2a632)



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e5624168943445442f6b44383b7cb6b865c2fbb3798cc9e2daa6dae3d6f6978e59d70bf9b4297d1bebae1a7f090c78a50)