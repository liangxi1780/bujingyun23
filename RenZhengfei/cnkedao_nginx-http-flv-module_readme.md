# nginx-http-flv-module

[![Build Status](https://travis-ci.org/winshining/nginx-http-flv-module.svg?branch=master)](https://travis-ci.org/winshining/nginx-http-flv-module)

Media streaming server based on [nginx-rtmp-module](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304678554323bf7acb43f1a73ce1b5c3ff79096db775e93cd3327174474f820de06c).

[中文说明](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046859258ae67850d2ea2a54a2cdae733eddc386475a9df883fa9453d41a194faa7907acb2e25bd36a678b8f7d6240f1595e02776770da75bc02622bd8706efce55).

Donate if you like this module. Many thanks to you!

   

### Appreciation

* Igor Sysoev, the creator of [NGINX](http://u.720life.cn/g/8e5d45d2feb3582a8a09a3bac21cb32b).

* Roman Arutyunyan, who created [nginx-rtmp-module](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304678554323bf7acb43f1a73ce1b5c3ff79096db775e93cd3327174474f820de06c).

* Contributors, refer to [AUTHORS](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046859258ae67850d2ea2a54a2cdae733eddc386475a9df883fa9453d41a194faa7907acb2e25bd36a678b8f7d6240f1595424fff1f34844bb393d380ef8419e3d9) for details.

## Features

* All features [nginx-rtmp-module](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304678554323bf7acb43f1a73ce1b5c3ff79096db775e93cd3327174474f820de06c) provides.

* Other features provided by nginx-http-flv-module vs [nginx-rtmp-module](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304678554323bf7acb43f1a73ce1b5c3ff79096db775e93cd3327174474f820de06c):

|         Features        | nginx-http-flv-module | nginx-rtmp-module |                     Remarks                     |
| :---------------------: | :-------------------: | :---------------: | :---------------------------------------------: |
|   HTTP-FLV (subscribe)  |           √           |         x         |     HTTPS-FLV and chunked response supported    | 
|        GOP cache        |           √           |         x         |                                                 |
|          VHOST          |           √           |         x         |                                                 |
| Omit `listen` directive |           √           |    See remarks    |  There MUST be at least one `listen` directive  |
|   Audio-only support    |           √           |    See remarks    |  Won't work if `wait_video` or `wait_key` is on |
|  Timing log for access  |           √           |         x         |                                                 |
|     JSON style stat     |           √           |         x         |                                                 |

## Systems supported

* Linux (recommended)/FreeBSD/MacOS/Windows (limited).

## Players supported

* [VLC](http://u.720life.cn/g/8703489d0252775f207f12598c7ac5ef2db6253b82047fa047afde3a903883cb) (RTMP & HTTP-FLV)/[OBS](http://u.720life.cn/g/df648cf675209036a55ceb25f61cf0db49ae4819ab7aec8c163e3165ba773ec9) (RTMP & HTTP-FLV)/[JW Player](http://u.720life.cn/g/4122e8a809eb3ea0a97a40ffb4fc4fd4151f7d690c9e876fce34b8e01e546bda) (RTMP)/[flv.js](http://u.720life.cn/g/54145d0471d91890860f7f8463c030467f720d8e1b6766577845b2bbcfdc170ae84de65be59cdbfac6029068ef9812bf) (HTTP-FLV).

### Note

[flv.js](http://u.720life.cn/g/54145d0471d91890860f7f8463c030467f720d8e1b6766577845b2bbcfdc170ae84de65be59cdbfac6029068ef9812bf) can only run with browsers that support [Media Source Extensions](http://u.720life.cn/g/098598e75704e07d68eba0aa885b4c2b50d66844563cf078167093951fcc58283222206db79ae89c82a0f846bfdb612a).

## Prerequisites

* GNU make for activating compiler on Unix-like systems to compile software.

* GCC for compilation on Unix-like systems or MSVC for compilation on Windows.

* GDB for debug on Unix-like systems.

* [FFmpeg](http://u.720life.cn/g/08a8721494911cd8408a11af9e278b23a8b634180c2ae57692114282107e4428) or [OBS](http://u.720life.cn/g/df648cf675209036a55ceb25f61cf0db49ae4819ab7aec8c163e3165ba773ec9) for publishing media streams.

* [VLC](http://u.720life.cn/g/8703489d0252775f207f12598c7ac5ef2db6253b82047fa047afde3a903883cb) (recommended) or [flv.js](http://u.720life.cn/g/54145d0471d91890860f7f8463c030467f720d8e1b6766577845b2bbcfdc170ae84de65be59cdbfac6029068ef9812bf) (recommended) for playing media streams.

* [PCRE](http://u.720life.cn/g/5c846b878f4c4866dc60e64bcee32166ac0b63b353223389f2af489515945251) for NGINX if regular expressions needed.

* [OpenSSL](http://u.720life.cn/g/25c6ec599554e791edfb864b96d06126eaba8d58ed5c35adb0062df1e10ca5c2) for NGINX if encrypted access needed.

* [zlib](http://u.720life.cn/g/0661ea6174e3583816e5c3c3f43a5a48ebac262107c9ed12e2615d9b2beb261e) for NGINX if compression needed.

## Installation

### Install in RHEL/CentOS (Thanks [dvershinin](http://u.720life.cn/g/54145d0471d91890860f7f8463c030461ff00764801b27cc55f4a449112560ad)

#### RHEL/CentOS 6, 7

For these operating systems, automatic builds of the latest release of module for the latest stable NGINX are available:

    yum install https://extras.getpagespeed.com/release-el$(rpm -E %{rhel})-latest.rpm
    yum install nginx-module-flv

#### RHEL 8

    dnf install https://extras.getpagespeed.com/release-el$(rpm -E %{rhel})-latest.rpm
    sudo dnf --disablerepo=rhel-8-for-x86_64-appstream-rpms install nginx-module-flv

Now configuration files named `http-flv.conf` for HTTP-FLV feature and `rtmp.conf` for RTMP feature are located in `/etc/nginx/http-flv` directory, add them to `/etc/nginx/nginx.conf` manually via `include` to enable HTTP-FLV and RTMP features:

    http {
        ...
        include /etc/nginx/http-flv/http-flv.conf;
    }

    include /etc/nginx/http-flv/rtmp.conf;

To enable this module, add the following to `/etc/nginx/nginx.conf` and reload NGINX:

    load_module modules/ngx_http_flv_live_module.so;

#### Note

The above setting **MUST** be located before the directive `events`, or NGINX can not be started.

Updates can be completed via `yum update`. More details about other NGINX modules, refer to [GetPageSpeed repository](http://u.720life.cn/g/5afbfdba57062fb94daa98526a4fb70a9171cd8c8cc56c311aa1668ce25868584af171b18c155faa5dad459794c2b207).
 
For other systems, follow Installation instructions in the next section.

### Install by compiling source code

#### Note

nginx-http-flv-module has all features that [nginx-rtmp-module](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304678554323bf7acb43f1a73ce1b5c3ff79096db775e93cd3327174474f820de06c) provides, so **DON'T** compile nginx-http-flv-module along with [nginx-rtmp-module](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304678554323bf7acb43f1a73ce1b5c3ff79096db775e93cd3327174474f820de06c).

#### On Windows

For details about build steps, please refer to [Building nginx on the Win32 platform with Visual C](http://u.720life.cn/g/8e5d45d2feb3582a8a09a3bac21cb32b9bb3cc03867b98c700a8731c79430c2a5165d5a58fea664243256ad854bf7e301efdf7bd2f91daf16f7d9daa08439708), and don't forget to add `--add-module=/path/to/nginx-http-flv-module` in `Run configure script` step.

#### On Unix-like systems

Download [NGINX](http://u.720life.cn/g/8e5d45d2feb3582a8a09a3bac21cb32b) and nginx-http-flv-module.

Uncompress them.

cd to NGINX source directory & run this:

##### Compile the module into [NGINX](http://u.720life.cn/g/8e5d45d2feb3582a8a09a3bac21cb32b)

    ./configure --add-module=/path/to/nginx-http-flv-module
    make
    make install

or

##### Compile the module as a dynamic module

    ./configure --add-dynamic-module=/path/to/nginx-http-flv-module
    make
    make install

##### Note

If the module is compiled as a dynamic module, the [NGINX](http://u.720life.cn/g/8e5d45d2feb3582a8a09a3bac21cb32b) version **MUST** be equal to or greater than 1.9.11.

## Usage

For details of usages of [nginx-rtmp-module](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304678554323bf7acb43f1a73ce1b5c3ff79096db775e93cd3327174474f820de06c), please refer to [README.md](http://u.720life.cn/g/54145d0471d91890860f7f8463c0304678554323bf7acb43f1a73ce1b5c3ff79b1b613bd41eb85289be4621cb7fa01040a3497994bfe040b4eff1071e48377e8).

### Publish

For simplicity, transcoding is not used (so **-c copy** is used):

    ffmpeg -re -i MEDIA_FILE_NAME -c copy -f flv rtmp://example.com[:port]/appname/streamname

#### Note

* Some legacy versions of [FFmpeg](http://u.720life.cn/g/08a8721494911cd8408a11af9e278b23a8b634180c2ae57692114282107e4428) don't support the option `-c copy`, the options `-vcodec copy -acodec copy` can be used instead.

The `appname` is used to match an application block in rtmp block (see below for details).

The `streamname` can be specified at will but can **NOT** be omitted.

The **default port for RTMP** is **1935**, if some other ports were used, `:port` must be specified.

### Play

#### via HTTP-FLV

    http://example.com[:port]/dir?[port=xxx&]app=appname&stream=streamname

#### Note

* If [ffplay](http://u.720life.cn/g/d457506e4c86c47270e5e2b633113cc81896472eeaf15ee57790c44909f1ef376b39a2dda4a400a5277f793c633b28de) is used in command line to play the stream, the url above **MUST** be enclosed by quotation marks, or arguments in url will be discarded (some shells not so smart will interpret "&" as "run in background").

* If [flv.js](http://u.720life.cn/g/54145d0471d91890860f7f8463c030467f720d8e1b6766577845b2bbcfdc170ae84de65be59cdbfac6029068ef9812bf) is used to play the stream, make sure that the published stream is encoded properly, for [flv.js](http://u.720life.cn/g/54145d0471d91890860f7f8463c030467f720d8e1b6766577845b2bbcfdc170ae84de65be59cdbfac6029068ef9812bf) supports **ONLY H.264 encoded video and AAC/MP3 encoded audio**.

The `dir` is used to match location blocks in http block (see below for details).

The **default port for HTTP** is **80**, if some other ports were used, `:port` must be specified.

The **default port for RTMP** is **1935**, if some other ports were used, `port=xxx` must be specified.

The value of `app` (appname) is used to match an application block, but if the requested `app` appears in several server blocks and those blocks have the same address and port configuration, host name matches `server_name` directive will be additionally used to identify the requested application block, otherwise the first one is matched.

The value of `stream` (streamname) is used to match the name of published stream.

#### Example

Assume that `listen` directive specified in `http` block is:

    http {
        ...
        server {
            listen 8080; #not default port 80
            ...

            location /live {
                flv_live on;
            }
        }
    }

And `listen` directive specified in `rtmp` block is:

    rtmp {
        ...
        server {
            listen 1985; #not default port 1935
            ...

            application myapp {
                live on;
            }
        }
    }

And the name of published stream is `mystream`, then the url of playback based on HTTP is:

    http://example.com:8080/live?port=1985&app=myapp&stream=mystream

#### Note

Since some players don't support HTTP chunked transmission, it's better to specify `chunked_transfer_encoding off;` in location where `flv_live on;` is specified in this case, or play will fail.

#### via RTMP

    rtmp://example.com[:port]/appname/streamname

#### via HLS

    http://example.com[:port]/dir/streamname.m3u8

#### via DASH

    http://example.com[:port]/dir/streamname.mpd

## Sample Pictures

### RTMP ([JW Player](http://u.720life.cn/g/4122e8a809eb3ea0a97a40ffb4fc4fd4151f7d690c9e876fce34b8e01e546bda) & HTTP-FLV ([VLC](http://u.720life.cn/g/8703489d0252775f207f12598c7ac5ef2db6253b82047fa047afde3a903883cb)

![RTMP & HTTP-FLV](samples/jwplayer_vlc.png)

### HTTP-FLV ([flv.js](http://u.720life.cn/g/54145d0471d91890860f7f8463c030467f720d8e1b6766577845b2bbcfdc170ae84de65be59cdbfac6029068ef9812bf)

![HTTP-FLV](samples/flv.js.png)

## Example nginx.conf

### Note

The directives `rtmp_auto_push`, `rtmp_auto_push_reconnect` and `rtmp_socket_dir` will not function on Windows except on Windows 10 17063 and later versions, because `relay` in multiple processes mode needs help of Unix domain socket, please refer to [Unix domain socket on Windows 10](http://u.720life.cn/g/b4daa60d3d059fb4c6303e4a19d951a8de9da263685c64db5d83fd0458b295940c8997eb69549dbf437f66d4754a0bb0a94c46b4a1332691a2b21510f6a2fa579b54db77c8ed626c899a410ee71ae2c8) for details.

It's better to specify the directive `worker_processes` as 1, because `ngx_rtmp_stat_module` may not get statistics from a specified worker process in multi-processes mode, for HTTP requests are randomly distributed to worker processes. `ngx_rtmp_control_module` has the same problem. The problem can be optimized by this patch [per-worker-listener](http://u.720life.cn/g/54145d0471d91890860f7f8463c030467349859dd8fdf9af3f5a69573073c7e60c186d138f0a5a394ae5bd66715f1da9ef2a5cec6d29cd54cf2a93adb8d8cd6018e846c9c49078bb3a94d2f9e42840db).

In addtion, `vhost` feature is not perfect in multi-processes mode yet, waiting to be fixed. For example, the following configuration is OK in multi-processes mode:

    rtmp {
        ...
        server {
            listen 1935;

            application myapp {
                ...
            }
        }

        server {
            listen 1935;
            server_name localhost;

            application myapp {
                ...
            }
        }
    }

While the following configuration doesn't work for play requests distinated to the port 1945 of non-publisher worker processes on which some streams are published:

    rtmp {
        ...
        server {
            listen 1935;

            application myapp {
                ...
            }
        }

        server {
            listen 1945;
            server_name localhost;

            application myapp {
                ...
            }
        }
    }

### Example configuration

    worker_processes  1; #should be 1 for Windows, for it doesn't support Unix domain socket
    #worker_processes  auto; #from versions 1.3.8 and 1.2.5

    #worker_cpu_affinity  0001 0010 0100 1000; #only available on FreeBSD and Linux
    #worker_cpu_affinity  auto; #from version 1.9.10

    error_log logs/error.log error;

    #if the module is compiled as a dynamic module and features relevant
    #to RTMP are needed, the command below MUST be specified and MUST be
    #located before events directive, otherwise the module won't be loaded
    #or will be loaded unsuccessfully when NGINX is started

    #load_module modules/ngx_http_flv_live_module.so;

    events {
        worker_connections  4096;
    }

    http {
        include       mime.types;
        default_type  application/octet-stream;

        keepalive_timeout  65;

        server {
            listen       80;

            location / {
                root   /var/www;
                index  index.html index.htm;
            }

            error_page   500 502 503 504  /50x.html;
            location = /50x.html {
                root   html;
            }

            location /live {
                flv_live on; #open flv live streaming (subscribe)
                chunked_transfer_encoding  on; #open 'Transfer-Encoding: chunked' response

                add_header 'Access-Control-Allow-Origin' '*'; #add additional HTTP header
                add_header 'Access-Control-Allow-Credentials' 'true'; #add additional HTTP header
            }

            location /hls {
                types {
                    application/vnd.apple.mpegurl m3u8;
                    video/mp2t ts;
                }

                root /tmp;
                add_header 'Cache-Control' 'no-cache';
            }

            location /dash {
                root /tmp;
                add_header 'Cache-Control' 'no-cache';
            }

            location /stat {
                #configuration of push & pull status

                rtmp_stat all;
                rtmp_stat_stylesheet stat.xsl;
            }

            location /stat.xsl {
                root /var/www/rtmp; #specify in where stat.xsl located
            }

            #if JSON style stat needed, no need to specify
            #stat.xsl but a new directive rtmp_stat_format

            #location /stat {
            #    rtmp_stat all;
            #    rtmp_stat_format json;
            #}

            location /control {
                rtmp_control all; #configuration of control module of rtmp
            }
        }
    }

    rtmp_auto_push on;
    rtmp_auto_push_reconnect 1s;
    rtmp_socket_dir /tmp;

    rtmp {
        out_queue           4096;
        out_cork            8;
        max_streams         128;
        timeout             15s;
        drop_idle_publisher 15s;

        log_interval 5s; #interval used by log module to log in access.log, it is very useful for debug
        log_size     1m; #buffer size used by log module to log in access.log

        server {
            listen 1935;
            server_name www.test.*; #for suffix wildcard matching of virtual host name

            application myapp {
                live on;
                gop_cache on; #open GOP cache for reducing the wating time for the first picture of video
            }

            application hls {
                live on;
                hls on;
                hls_path /tmp/hls;
            }

            application dash {
                live on;
                dash on;
                dash_path /tmp/dash;
            }
        }

        server {
            listen 1935;
            server_name *.test.com; #for prefix wildcard matching of virtual host name

            application myapp {
                live on;
                gop_cache on; #open GOP cache for reducing the wating time for the first picture of video
            }
        }

        server {
            listen 1935;
            server_name www.test.com; #for completely matching of virtual host name

            application myapp {
                live on;
                gop_cache on; #open GOP cache for reducing the wating time for the first picture of video
            }
        }
    }



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6eb27d12f799a50a04a9372f0b3985f9e07ebd5f409e236c234083a56880fb0b7e26cb48c799092afaa75f8f231e5ff70c22a13cc11113b4f0af97d06803926faf)