# arch-linux-surface

This is an Arch Linux packager that applies 
[jakeday's patches for Surface devices](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046a4b8c32e424c101732e280aa2709bbf8df40cc37c8a0d925c4a7814bb890bd8b) 
to the Linux kernel of your choice. 

## Pre-Installation

First thing you're going to want to do is to clone this repository:

```
git clone https://github.com/dmhacker/arch-linux-surface
cd arch-linux-surface
```

Before you begin compiling & installing the patched kernel, it's recommended that you 
install all necessary firmware that your Surface device needs and replace suspend with hibernate.
You can do this by running the `setup.sh` script with superuser permissions.

```
sudo sh setup.sh
```

Now, you are ready to begin compilation of your kernel. 
Alternatively, you could download the 
[pre-built kernel binaries](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046631c138fbd52276da192bd66c3edb35d7da5b58835b2928a92a7388a3d76aabd0221bf4564af011247d8acce9c789af2) 
and skip ahead to the installation section.

## Compilation

To generate the build directory for the kernel, you need to run the `configure.sh` script. 
The packager will prompt for the target major version of the Linux kernel during configuration.

```
sh configure.sh 
```

Once configure is finished, it will output a directory titled `build-[VERSION]`. 
Note that [VERSION] is the full version of the kernel and not just its major version. 
To build this kernel, use these two commands: 

```
cd build-[VERSION] 
MAKEFLAGS="-j[NPROC]" makepkg -sc
```

  \* Replace [VERSION] with whatever kernel version configure outputs.   
  \*\* Replace [NPROC] with the number of available processors in your machine.  

If you are unable to issue this command because of write permission issues, use the following
command to give yourself access, replacing [USER] and [VERSION] with their appropriate values:

```
chown -R [USER] build-[VERSION]
```

## Installation

When the build process is completed, under `build-[VERSION]`, you will find these packages:
```
linux-surface-[VERSION]-1-x86_64.pkg.tar.xz
linux-surface-headers-[VERSION]-1-x86_64.pkg.tar.xz
linux-surface-docs-[VERSION]-1-x86_64.pkg.tar.xz
```
You can either install them with `sudo pacman -U ...` or do something else with them.



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e2f66767f7de8a9a5217717bc021c2abc647a067903ad016257c10c9c97b8a862b8d346e299e33b40ceb69427e4f9402a5faf163f551f474f589d775c7d87169f)