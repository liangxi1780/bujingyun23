# MicroPython for ESP32

# with support for 4MB of psRAM

 

> This repository can be used to build MicroPython for ESP32 boards/modules with **psRAM** as well as for ESP32 boards/modules **without psRAM.**  
> *Building on* **Linux**, **MacOS** *and* **Windows** (including **Linux Subsystem on Windows 10**) *is supported*.  
> MicroPython works great on ESP32, but the most serious issue is still (as on most other MicroPython boards) limited amount of free memory. 
> This repository contains all the tools and sources necessary to **build working MicroPython firmware** which can fully use the advantages of **4MB** (or more) of **psRAM**. 
> It is **huge difference** between MicroPython running with **less than 100KB** of free memory and running with **4MB** of free memory.

 

ESP32 can use external **SPIRAM** (psRAM) to expand available RAM up to 16MB.

Currently, there are several modules & development boards which incorporates **4MB** of psRAM: 

* [**M5Stack**](http://u.720life.cn/g/a50beacba43d84368ba189e7c5b973996adeccbb4dad41f0127b78599e675900)  _Development Kit_ [version with psRAM](http://u.720life.cn/g/0edd1c6d9db9d558adf0ed505fc8a75bf5beee34ed1857ed3d952a8d308ff97e29fab82e9c1f32d8100b63af3e63b3832e710f96d5cf738644ba4d8ef42788de9efbc5c3758f62f4bd1bf57655535e9f7b52d000873418b7645facd025e4ac1bb181446d07931a7631f7c8a1745baa5db8e0c8495c5895e99caf2b31401a16bc0fe2c7c0fdcb496598e2516e8de898c1db521d91437159402e9e0c38fd806c6dfa1cc6a0179e4def78854fe4a5fb2d1f4d042342e64d03b882d5e3c38bcde029e1b28ae4bb7a01637e365bb22ffc2421) 
* **TTGO T8 V1.1** _board_, available at [eBay](http://u.720life.cn/g/03443566ba06675bd3c17dcfde885b7b77042e41e08fc0fe17dc531f9f6ce8d2dd02cff929825794220dac7c8cd033ee699e6288e55ca53c2268f39f07f63a10e96ac6710da9c1cd0ed4acf5e4826ead1d706455fef48358cf06675e03c5a0e810a177fb5d02c86800651df5b362a7c54506bf139db3469a8c9a941039f089de20f50b922ccf3c060a244746e23e3ee1) 
* **ESP-WROVER-KIT** _boards_ from Espressif, available from [ElectroDragon](http://u.720life.cn/g/19c75ea474055aabb367ed5c57cb1e91eee7cf54ee4a069054698a41727a33d7df2460a22d7f78c1212c14a5ed7d0ca6d4b9c7a327fdc8afefffd92d6d8f2526  [AnalogLamb](http://u.720life.cn/g/798fe3ba4672402e83b00c7861d209b5441062cf9626488904299273c7966cd5eeb21664b5d7b8e5987956ba3c04e28c7f03b0bbeda123f8e1af1afc68c1894cc24e1ecce0ec9ea4949f4551443d5739  ...
* **WiPy 3.0** _board_ from [Pycom](http://u.720life.cn/g/bdf6d503eac7b557ae8c16fd50feb25dd760eeba001960ff697a986b3b33e2a2f73f084d2aefc00bca25a5604f83a360 
* **TTGO TAudio** _board_ ([eBay](http://u.720life.cn/g/03443566ba06675bd3c17dcfde885b7b2dacf9ed7bf4db1f76a06bfc70d4e4866cada55459fe45efcd1eb567177c915e0e874ee798acee9b99e584b06a5e2853243d6d19b6437c3d1c43bc1de10f13a2831e2bb56d06cb8baa2bf9d08432387257060d0baddc0c2ed114f45595c2073551957839ccfa72a501bbd602c33e19693ea2802f86cb5419fcf2a118a522e7dfffb0a90e9b3cdd1fb2d7b8163230532f) 
* **Lolin32 Pro** _board_ from [Wemos](http://u.720life.cn/g/72cfbeea1e7de58692400fff68287f2866771684ca03e1a5156e63dc5cf3322edb4d320fee2a55cf89cb31549d6d653aecab35568318c2324a2c25dd7632a829)  - **`no longer available`** ([Schematic](http://u.720life.cn/g/72cfbeea1e7de58692400fff68287f284273a6990e07c9a2be2ade0604579c9ebb117535c7f878131e78e3fecc9377bb24651f9cdaee3da33f7232a797d109c83aab6a5d137acbbf630de6f512beccab 
* **ESP-WROVER** _module_ from Espressif, available from [ElectroDragon](http://u.720life.cn/g/19c75ea474055aabb367ed5c57cb1e91eee7cf54ee4a069054698a41727a33d7df2460a22d7f78c1212c14a5ed7d0ca6002b45d138ae6177f26ef31fc9389c2c626f01ddcf177859bcac6c109b789674)  and many other vendors.
* **ALB32-WROVER** _module_ (4 MB SPIRAM & 4/8/16 MB Flash) from [AnalogLamb](http://u.720life.cn/g/798fe3ba4672402e83b00c7861d209b5441062cf9626488904299273c7966cd55223abd6bdea92cc3c81ccb2fe4cb376b706dec71b4acc45eca418c4430c9e92ddab3384b42c949a3694b88c9e219c158448e665ba519d38de539b3a27a15ebc 
* **S01**, **L01** and **G01** _OEM modules_ from [Pycom](http://u.720life.cn/g/bdf6d503eac7b557ae8c16fd50feb25dcfe69fe58ee1c9e2d4e43d0a51b024f1c8ef9e9a74881588c6f291a0b148cc7a 

---

[Wiki pages](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046727a032cbb9cdde1d7f6040efcee0561196beb78969e350831aed49907824026a9d35292faa5b63e74c7e29cfe00600e)  with detailed documentation specific to this **MicroPython** port are available.

Some examples can be found in [modules_examples](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046727a032cbb9cdde1d7f6040efcee0561196beb78969e350831aed4990782402678cdc4c2e3b22ccdcbfb3b14e7934dccd6ad9f172e0a4cb111e4d25516b5613db30a3764b9fd4744b8d0a08ad396a5f97c4aaeb699a6ed43300c94fb84247ab29d02fa58ceea45ab8c70172bdb6a7cadfdd2dad5add60350c7fe8c9c536512d8)  directory.

---

This repository contains all the tools and sources necessary to **build working MicroPython firmware** which can fully use the advantages of **4MB** (or more) of **psRAM**

It is **huge difference** between MicroPython running with **less than 100KB** of free memory and running with **4MB** of free memory.

---

## **The MicroPython firmware is built as esp-idf component**

This means the regular esp-idf **menuconfig** system can be used for configuration. Besides the ESP32 configuration itself, many MicroPython options can also be configured via **menuconfig**.

This way many features not available in standard ESP32 MicroPython are enabled, like unicore/dualcore, all Flash speed/mode options etc. No manual *sdkconfig.h* editing and tweaking is necessary.

---

### Features

* MicroPython core based on latest build from [main Micropython repository](http://u.720life.cn/g/54145d0471d91890860f7f8463c030469012c6c0dd5158b7f2d966a729acca7a999f55332c8a9300ffb378e2e45cff63) 
* added changes needed to build for ESP32 with psRAM
* Default configuration has **2MB** of MicroPython heap, **20KB** of MicroPython stack, **~200KB** of free DRAM heap for C modules and functions
* MicroPython can be built in **unicore** (FreeRTOS & MicroPython task running only on the first ESP32 core, or **dualcore** configuration (MicroPython task running on ESP32 **App** core)
* ESP32 Flash can be configured in any mode, **QIO**, **QOUT**, **DIO**, **DOUT**
* **BUILD.sh** script is provided to make **building** MicroPython firmware as **easy** as possible
* Internal Fat filesystem is built with esp-idf **wear leveling** driver, so there is less danger of damaging the flash with frequent writes.
* **SPIFFS** filesystem is supported and can be used instead of FatFS in SPI Flash. Configurable via **menuconfig**
* Flexible automatic and/or manual filesystem configuration
* **sdcard** support is included which uses esp-idf **sdmmc** driver and can work in **SD mode** (*1-bit* and *4-bit*) or in **SPI mode** (sd card can be connected to any pins). For imformation on how to connect sdcard see the documentation.
* Files **timestamp** is correctly set to system time both on internal fat filesysten and on sdcard
* **Native ESP32 VFS** support for spi Flash & sdcard filesystems.
* **RTC Class** is added to machine module, including methods for synchronization of system time to **ntp** server, **deepsleep**, **wakeup** from deepsleep **on external pin** level, ...
* **Time zone** can be configured via **menuconfig** and is used when syncronizing time from NTP server
* Built-in **ymodem module** for fast transfer of text/binary files to/from host
* Some additional frozen modules are added, like **pye** editor, **urequests**, **functools**, **logging**, ...
* **Btree** module included, can be Enabled/Disabled via **menuconfig**
* **_threads** module greatly improved, inter-thread **notifications** and **messaging** included
* **Neopixel** module using ESP32 **RMT** peripheral with many new features
* **DHT** module implemented using ESP32 RMT peripheral
* **1-wire** module implemented using ESP32 RMT peripheral
* **i2c** module uses ESP32 hardware i2c driver
* **spi** module uses ESP32 hardware spi driver
* **adc** module improved, new functions added
* **pwm** module, ESP32 hardware based
* **timer** module improved, new timer types and features
* **curl** module added, many client protocols including FTP and eMAIL
* **ssh** module added with sftp/scp support and _exec_ function to execute program on server
* **display** module added with full support for spi TFT displays
* **mqtt** module added, implemented in C, runs in separate task
* **mDNS** module added, implemented in C, runs in separate task
* **telnet** module added, connect to **REPL via WiFi** using telnet protocol
* **ftp** server module added, runs as separate ESP32 task
* **GSM/PPPoS** support, connect to the Internet via GSM module
* **OTA Update** supported, various partitions layouts
* **Eclipse** project files included. To include it into Eclipse goto File->Import->Existing Projects into Workspace->Select root directory->[select *MicroPython_BUILD* directory]->Finish. **Rebuild index**.

---


### How to Build

---

Detailed instructions on **MicroPython** building process are available in the [Wiki](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046727a032cbb9cdde1d7f6040efcee0561196beb78969e350831aed499078240264c598ca130f816434daac4bd7c3c776ee49297b6448668d7bc7b5d075e115434 

---


#### Using file systems

Detailed information about using MicroPython file systems are available in the [Wiki](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046727a032cbb9cdde1d7f6040efcee0561196beb78969e350831aed49907824026537b52ae826db9854f6c1e0157fa9202e9567999a4390b908e65bf0486134749 

---


### Some examples

Using new machine methods and RTC:

```python
import machine

rtc = machine.RTC()

rtc.init((2017, 6, 12, 14, 35, 20))

rtc.now()

rtc.ntp_sync(server=" " [,update_period=])
  #   can be empty string, then the default server is used ("pool.ntp.org")

rtc.synced()
  # returns True if time synchronized to NTP server

rtc.wake_on_ext0(Pin, level)
rtc.wake_on_ext1(Pin, level)
  # wake up from deepsleep on pin level

machine.deepsleep(10000)
ESP32: DEEP SLEEP

# ...
# ...

Reset reason: Deepsleep wake-up
Wakeup source: RTC wake-up
    uPY stack: 19456 bytes
     uPY heap: 3073664/5664/3068000 bytes (in SPIRAM using malloc)

MicroPython ESP32_LoBo_v3.1.0 - 2017-01-03 on ESP32 board with ESP32
Type "help()" for more information.

machine.wake_reason()
  # returns tuple with reset & wakeup reasons
machine.wake_description()
  # returns tuple with strings describing reset & wakeup reasons

```

Using sdcard module:

```python
import uos

uos.mountsd()
uos.listdir('/sd')
```

Working directory can be changed to root of the sd card automatically on mount:

```python
>>> import uos
>>> uos.mountsd(True)
---------------------
 Mode:  SD (4bit)
 Name: NCard
 Type: SDHC/SDXC
Speed: default speed (25 MHz)
 Size: 15079 MB
  CSD: ver=1, sector_size=512, capacity=30881792 read_bl_len=9
  SCR: sd_spec=2, bus_width=5

>>> uos.listdir()
['overlays', 'bcm2708-rpi-0-w.dtb', ......
>>>
```

---

Tested on **ESP-WROVER-KIT v3**
![Tested on](https://raw.githubusercontent.com/loboris/MicroPython_ESP32_psRAM_LoBo/master/Documents/ESP-WROVER-KIT_v3_small.jpg)

---

### Example terminal session


```
I (0) cpu_start: App cpu up.
I (1569) spiram: SPI SRAM memory test OK
I (1570) heap_init: Initializing. RAM available for dynamic allocation:
D (1570) heap_init: New heap initialised at 0x3ffae6e0
I (1575) heap_init: At 3FFAE6E0 len 00001920 (6 KiB): DRAM
D (1581) heap_init: New heap initialised at 0x3ffc1a00
I (1586) heap_init: At 3FFC1A00 len 0001E600 (121 KiB): DRAM
I (1593) heap_init: At 3FFE0440 len 00003BC0 (14 KiB): D/IRAM
I (1599) heap_init: At 3FFE4350 len 0001BCB0 (111 KiB): D/IRAM
D (1606) heap_init: New heap initialised at 0x4009d70c
I (1611) heap_init: At 4009D70C len 000028F4 (10 KiB): IRAM
I (1617) cpu_start: Pro cpu start user code
I (1622) spiram: Adding pool of 4096K of external SPI memory to heap allocator
I (1630) spiram: Reserving pool of 32K of internal memory for DMA/internal allocations
D (1646) clk: RTC_SLOW_CLK calibration value: 3305242
D (89) intr_alloc: Connected src 46 to int 2 (cpu 0)
D (90) intr_alloc: Connected src 57 to int 3 (cpu 0)
D (90) intr_alloc: Connected src 24 to int 9 (cpu 0)
I (95) cpu_start: Starting scheduler on PRO CPU.
D (0) intr_alloc: Connected src 25 to int 2 (cpu 1)
I (4) cpu_start: Starting scheduler on APP CPU.
D (119) heap_init: New heap initialised at 0x3ffe0440
D (125) heap_init: New heap initialised at 0x3ffe4350
D (130) intr_alloc: Connected src 16 to int 12 (cpu 0)
D (145) nvs: nvs_flash_init_custom partition=nvs start=9 count=4
D (178) intr_alloc: Connected src 34 to int 3 (cpu 1)
D (187) intr_alloc: Connected src 22 to int 4 (cpu 1)

Internal FS (SPIFFS): Mounted on partition 'internalfs' [size: 1048576; Flash address: 0x2D0000]
----------------
Filesystem size: 956416 B
           Used: 512 B
           Free: 955904 B
----------------

FreeRTOS running on BOTH CORES, MicroPython task running on both cores.
Running from partition at 10000, type 10 [MicroPython_1].

 Reset reason: Power on reset
    uPY stack: 19456 bytes
     uPY heap: 3073664/5664/3068000 bytes (in SPIRAM using malloc)

MicroPython ESP32_LoBo_v3.1.0 - 2017-01-03 on ESP32 board with ESP32
Type "help()" for more information.
>>> 
>>> import micropython, machine
>>> 
>>> micropython.mem_info()
stack: 752 out of 19456
GC: total: 3073664, used: 5904, free: 3067760
 No. of 1-blocks: 19, 2-blocks: 7, max blk sz: 325, max free sz: 191725
>>> 
>>> machine.heap_info()
Heap outside of MicroPython heap:
---------------------------------
              Free: 239920
         Allocated: 52328
      Minimum free: 233100
      Total blocks: 85
Largest free block: 113804
  Allocated blocks: 79
       Free blocks: 6

SPIRAM info:
------------
              Free: 1048532
         Allocated: 3145728
      Minimum free: 1048532
      Total blocks: 2
Largest free block: 1048532
  Allocated blocks: 1
       Free blocks: 1
>>>
```



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)