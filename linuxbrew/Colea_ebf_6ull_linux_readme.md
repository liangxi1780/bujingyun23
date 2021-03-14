# ebf_6ull_linux

## 开发环境

**ubuntu18.04**

**安装必要的库**
```bash
sudo apt-get install lzop libncurses5-dev
```

**安装独立编译工具链**

1. 命令安装方式（推荐新手使用这种方法）：

arm-linux-gnueabihf-gcc：`v7.4.0`
```bash
sudo apt-get install gcc-arm-linux-gnueabihf
```

2. 安装包安装方式(推荐老手使用这种方法)

从百度云盘下载`arm-linux-gnueabihf-gcc`编译器的压缩包，版本是 `v4.9.3`

链接：[https://github.com/Embedfire/products/wiki](http://u.720life.cn/g/54145d0471d91890860f7f8463c030466beee424e1021f8b04d832fb2ef584f8d267b70b9f88b562382bf32e1d17f9b6) 

在 **Linux系列产品** 中找到的网盘链接，在`i.MX6ULL系列\5-编译工具链\arm-gcc` 目录下找到 `arm-gcc.tar.gz` 压缩包并且下载

安装方法参考：[https://blog.csdn.net/u013485792/article/details/50958253](http://u.720life.cn/g/ce3f6174933242f367d8a4cd3fa79ded1d01bf6baed859e013d72bb43558d332901837981261ad6c63e46a44067f5c9b03b99ac1ab30a2a68358dd8db3642ac7)

> 作者备注：为什么推荐更低版本的编译器呢？因为作者亲测新版本的编译器并不能完全兼容，在测试比如新版本编译的内核镜像无法识别到4G模块。但是在绝大部分情况下`v7.4.0`版本的编译器都是没有任何问题的！！！请放心使用！！！


## 内核编译过程

**导出环境变量**

```bash
export PATH=/opt/arm-gcc/bin:$PATH
export ARCH=arm 
export CROSS_COMPILE=arm-linux-gnueabihf- 
```

**清除编译信息**

```bash
make ARCH=arm clean
```

## 设置配置选项,使用野火开发板配置

```bash
make ARCH=arm imx6_v7_ebf_defconfig
```

## 开始编译
```bash
make ARCH=arm -j10 CROSS_COMPILE=arm-linux-gnueabihf- 
```

## 编译生成的镜像输出路径

**内核镜像路径**

```bash
ebf_6ull_linux/arch/arm/boot
```

**设备树输出路径**

```bash
ebf_6ull_linux/arch/arm/boot/dts
```

**拷贝zImage与dtb**

可以直接运行脚本`copy.sh`将内核镜像与设备树拷贝到`image`目录下

```bash
./copy.sh
```

## 只编译设备树
在后面添加 `dtbs` 即可
```bash
make ARCH=arm -j10 CROSS_COMPILE=arm-linux-gnueabihf- dtbs
```

---

## 编译的设备树：

- imx6ull-14x14-evk.dts 
- imx6ull-14x14-evk-btwifi.dts 
- imx6ull-14x14-evk-emmc.dts 
- imx6ull-14x14-evk-gpmi-weim-43.dts 
- imx6ull-14x14-evk-emmc-43.dts 
- imx6ull-14x14-evk-gpmi-weim-hdmi.dts 
- imx6ull-14x14-evk-emmc-hdmi.dts 
- imx6ull-14x14-evk-gpmi-weim-wifi.dts 
- imx6ull-14x14-evk-emmc-wifi.dts 
- imx6ull-14x14-evk-gpmi-weim-cam-dht11.dts 
- imx6ull-14x14-evk-emmc-cam-dht11.dts

---
## 骚气的一键编译
直接运行以下命令
```
./build.sh
```

或者...

```
./build.sh 5.0
```

生成的内核镜像与设备树均被拷贝到 `image` 目录下。
内核模块相关均被安装到 `my_lib/lib/` 目录下的`modules`文件夹下，可以直接替换掉`rootfs(根文件系统)`中的`/lib/modules/`。

`build.sh`脚本默认编译5.0寸屏幕的内核镜像，如果需要4.3寸屏幕的内核镜像，则可以使用以下命令去编译:

```
./build.sh 4.3
```

## 配置选项（部分）

运行 `make ARCH=arm menuconfig` 命令打开配置界面，根据自身需求配置即可！

**触摸屏驱动：**
```bash
 Prompt: Goodix I2C touchscreen   
  Location:            
   -> Device Drivers         
      -> Input device support  
       -> Generic input layer (needed for keyboard, mouse, ...) (INPUT [=y]) 
 (1)       -> Touchscreens (INPUT_TOUCHSCREEN [=y])  
 #这个也要使能
    [*]   Goodix touchpanel GT9xx series 
          Goodix GT9xx touch controller auto update support  
          Goodix GT9xx Tools for debuging     
```

**单总线驱动：**

```bash
 Prompt: Dallas's 1-wire support     
 Location:                         
  (1) -> Device Drivers          
  [*]   Userspace communication over connector (NEW)    
```

**添加MPU6050的支持：**

```bash
Prompt: Invensense MPU6050 devices      
Location:  
  -> Device Drivers               
    -> Industrial I/O support (IIO [=y])               
(1)     -> Inertial measurement units   
            Invensense MPU6050 devices   
```

**WIFI蓝牙**
```bash
Location:  
  -> Device Drivers               
    -> Network device support                                         
       -> Wireless LAN
          ->

     Broadcom FullMAC wireless cards support                        
        (/lib/firmware/bcm/AP6236/Wi-Fi/fw_bcm43436b0.bin) Firmware path     
         (/lib/firmware/bcm/AP6236/Wi-Fi/nvram_ap6236.txt) NVRAM path    

#HCI串口配置也要选择
    -> Device Drivers               
    -> Network device support                                         
       -> Wireless LAN
          ->Bluetooth subsystem support   
              ->Bluetooth device drivers   
                    HCI USB driver     
                  [*]   Broadcom protocol support  

  -> Networking support (NET [=y])     
    -> Bluetooth subsystem support (BT [=y]) 
      -> Bluetooth device drivers    
          HCI USB driver    
        [*]   Broadcom protocol support  
```

**PPP点对点拨号：**

所有PPP相关的都选中
```bash
 Prompt: PPP (point-to-point protocol) support              
  Location:          
  -> Device Drivers 
    (1)   -> Network device support (NETDEVICES [=y])       
```

**蓝牙和HCI子系统**

```bash
    -> Networking support (NET [=y])              
     -> Bluetooth subsystem support (BT [=y])   
      (1)     -> Bluetooth device drivers   
  --- RF switch subsystem support                                         
          [*]   RF switch input support  
              Generic rfkill regulator driver
              GPIO RFKILL driver            
```

---

## 常见的编译错误及解决方法

查看wiki：[https://github.com/Embedfire/ebf_6ull_linux/wiki](http://u.720life.cn/g/54145d0471d91890860f7f8463c030465454abaae57cf3b4c59d9cf08cbd5e8021b468bf98838452caee35922d5cbefe)

## 其他信息

**内核版本**

来源官方 `imx_4.1.15_2.0.0_ga` 分支

官方内核源码：[http://git.freescale.com/git/cgit.cgi/imx/linux-imx.git/](http://u.720life.cn/g/528aff8ba2b8727be8794503f939ff7e5d5249140793606ca5bda90cdc5460bbbf501bc3a32fd7e9879b148e1aac99c825bdae348d61355b146b7e23c3fe3ddf)

```bash
# Clone 
git://git.freescale.com/imx/linux-imx.git

http://git.freescale.com/git/cgit.cgi/imx/linux-imx.git
```



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e58eeea97d592916c21983206b42a802edc0889a78bc24643d619343bf6bc276abeb924a1538a79341f5a566b792404c6)