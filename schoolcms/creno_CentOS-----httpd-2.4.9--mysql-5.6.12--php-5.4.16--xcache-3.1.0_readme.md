#CentOS     httpd-2.4.9  mysql-5.6.12  php-5.4.16  xcache-3.1.0

### **【搭建LAXMP】** 


 **步骤:** 

* 安装系统工具包
* 安装Apache
* 安装Mysql数据库
* 安装PHP 
* 整合Apache与PHP
* 安装Xcache加速器
* 启用服务器状态 

---
### 一、安装系统工具包


**1. 准备安装包** 


 **2. 安装** 


``* vim  wget  gcc gcc-c++unzip zip ``

```
rpm -ivh http://dl.fedoraproject.org/pub/epel/6/x86_64/epel-release-6-8.noarch.rpm
```
```
yum -y install vim wget gcc gcc-c++ unzip zip
```

 **3. 关闭iptables和selinux** 
```
chkconfig iptables off
```
```
service iptables stop
```
```
vim /etc/sysconfig/selinux
```
修改一行

> SELINUX = disabled

```
getenforce
```
 **4. 卸载默认的低版本环境及rpm包环境Mysql，Apache，PHP** 

```
rpm -qa |grep mysql
```

> mysql-libs-5.1.66-2.el6_3.x86_64

```
rpm -e --nodeps mysql-libs
```
```
rpm -e --nodeps httpd
```
```
rpm -e --nodeps php
```
---






### 二、安装Apache服务


 **1. 安装Apache** 

 
 
> ``注意：
> 正式开始编译安装步骤，我们按照一定的顺序安装：
> Apache –>Mysql –>PHP，但在安装PHP之前，应该先安装PHP5需要的最新版本库文件，
> 例如：libxml2、libmcrypt、GD2库等文件。
> 安装GD2库是为了让PHP5支持GIF、PNG、JPEG图片格式，所以在安装GD2库之前还要先安装最新的
> zlib、libpng、freetype 和 jpegsrc 等库文件。而且中间还会穿插安装一些软件`` 
 
* apr apr-util pcre zlib apache


### Install apr
 
```
tar xf apr-1.5.1.tar.gz
```
```
cd apr-1.5.1
```
```
./configure --prefix=/usr/local/apr
``` 
```
make
```
```
make install
```

### Install apr-util  

```
tar xf apr-util-1.5.3.tar.gz
```
```
cd apr-util-1.5.3
```
```
./configure --prefix=/usr/local/apr-util --with-apr=/usr/local/apr
```
```
make
```
```
make install
```

### Install pcre

```
unzip pcre-8.33.zip
```
```
cd pcre-8.33
```
```
./configure --prefix=/usr/local/pcre
```
```
make
```
```
make install
```

### Install zlib

```
tar xf zlib-1.2.8.tar.gz
```
```
cd zlib-1.2.8
```
```
./configure --prefix=/usr/local/zlib
```
```
make
```
```
make install
```


### Install apache

```
tar xf httpd-2.4.9.tar.gz
```
```
cd httpd-2.4.9
```
```
./configure --prefix=/usr/local/apache --with-apr=/usr/local/apr --with-apr-util=/usr/local/apr-util --with-pcre=/usr/local/pcre --enable-so --enable-cgi --with-zlib --enable-rewrite --with-z=/usr/local/zlib --enable-mpms-shared=all   --enable-deflate=shared --enable-expires=shared --enable-rewrite=shared --enable-static-support --with-ssl --enable-ssl --enable-module=so --enable-cgid
```
```
make
```
```
make install
``` 

 **2. 测试Apache服务器**

启动Apache服务

```
/usr/local/apache/bin/apachectl stop
```

> AH00558: httpd: Could not reliably determine the server‘s fully qualified domain name, using localhost.localdomain.
> Set the ‘ServerName‘ directive globally to suppress this message

```
vim /usr/local/apache/conf/httpd.conf
```

修改一行 去掉注释 ``#``
 
> ServerName localhost:80



查看apache的80端口是否开启

```
netstat -tnlp |grep :80
```

浏览器访问apache服务器

http://ip
 
> It works!


如果显示``It works!``则表明安装成功！


 **3. 提供SysV服务脚本有两种方法**  

```
cp /usr/local/apache/bin/apachectl /etc/init.d/httpd
```
```
vim /etc/init.d/httpd
```


> 增加两行 

>{
> 
>  \# !/bin/sh 

>  \# chkconfig: 35 80 90

>  \# description Apache Web Server

> }  

```
chmod +x /etc/init.d/httpd
```
```
chkconfig --add httpd
```
```
chkconfig --list httpd 
```
```
service httpd stop
```
```
service httpd start
```
```
netstat -tnlp
```


 **4. 为Apache添加环境变量** 

```
/usr/local/apache/bin/httpd -v  #绝对路径
```


> Server version: Apache/2.4.9 (Unix)
> Server built:   Mar 31 2014 10:06:52

```
httpd
``` 

bash环境下不能直接调用，因为环境变量中没有httpd的路径 

> -bash: httpd: command not found 


```
vim /etc/profile.d/httpd.sh
```

增加一行

> export PATH=$PATH:/usr/local/apache/bin

```
source /etc/profile 
```
```
httpd -v
```
> Server version: Apache/2.4.9 (Unix)
> Server built:   Mar 31 2014 10:06:52

---









### 三. Mysql数据库

 **1. 安装cmake** 

```
tar xf cmake-2.8.11.2.tar.gz
```

```
cd cmake-2.8.11.2
```

```
./configure
```

```
gmake
```

```
make install
``` 

```
ln -sv /usr/local/bin/cmake /usr/bin/cmake
```

 **2. 创建mysql用户和组** 

```
groupadd -r mysql
```

```
useradd -g mysql -r -s /sbin/nologin mysql
```
 
 **3. 创建mysql数据目录** 

```
mkdir -pv /mydata/data
```

```
chown -R mysql:mysql /mydata/data
```


 **4. 安装mysql** 

```
yum -y install ncurses ncurses-devel{mysql在cmake的时候报错所需要的依赖包}
```
 
```
rm -rf /usr/local/src/mysql-5.6.12/CMakeCache.txt
```

```
tar xf mysql-5.6.12.tar.gz
```

```
cd mysql-5.6.12
```

```
cmake . -DCMAKE_INSTALL_PREFIX=/usr/local/mysql -DMYSQL_DATADIR=/mydata/data -DSYSCONFDIR=/etc -DWITH_INNOBASE_STORAGE_ENGINE=1 -DWITH_ARCHIVE_STORAGE_ENGINE=1 -DWITH_BLACKHOLE_STORAGE_ENGINE=1 -DWITH_READLINE=1 -DWITH_SSL:STRING=bundled -DWITH_ZLIB:STRING=bundled -DWITH_LIBWRAP=0 -DMYSQL_UNIX_ADDR=/tmp/mysql.sock -DDEFAULT_CHARSET=utf8 -DDEFAULT_COLLATION=utf8_general_ci
``` 

```
make
```
```
make install  
```

 **5. 为mysql提供服务脚本** 

```
cp support-files/mysql.server /etc/init.d/mysqld
```

```
chmod +x /etc/init.d/mysqld
```

```
chkconfig --add mysqld
```

```
chkconfig mysqld on
```

 **6. 初始化mysql** 

```
cd /usr/local/mysql/
```

```
chown -R mysql:mysql /usr/local/mysql/
```

```
scripts/mysql_install_db --user=mysql --datadir=/mydata/data/ 
```

 **7. 修改mysql配置文件** 

```
cp /usr/local/mysql/my.cnf /etc/my.cnf
```

```
vim /etc/my.cnf  
```

增加如下内容


> binlog-format=ROW
> 
> log-bin=master-bin.log
>   
> log-slave-updates=true
> 
> gtid-mode=on
> 
> enforce-gtid-consistency=true
> 
> master-info-repository=TABLE
> 
> relay-log-info-repository=TABLE
> 
> sync-master-info=1
> 
> slave-parallel-workers=2
> 
> binlog-checksum=CRC32
> 
> master-verify-checksum=1
> 
> slave-sql-verify-checksum=1
> 
> binlog-rows-query-log_events=1
> 
> server-id=1
> 
> report-port=3306
> 
> port=3306
> 
> datadir=/mydata/data
> 
> socket=/tmp/mysql.sock
> 
> report-host=master.allentuns.com


 **8. 启动mysql** 

```
service mysqld start
```

 **9. mysql命令添加到环境变量中** 

```
vim /etc/profile.d/mysql.sh
```

增加一行

> export PATH=$PATH:/usr/local/mysql/bin


```
source /etc/profile #重新读取环境变量 
```

 **10. 输出mysql的库文件** 

```
vim /etc/ld.so.conf.d/mysql.conf
```

增加一行

> /usr/local/mysql/lib/

```
ldconfig -v  #重新加载库文件
```

 **11. 输出mysql的头文件到系统头文件** 

```
ln -sv /usr/local/mysql/include/ /usr/include/mysql
``` 

--- 




### 四、安装PHP

 **1. 安装libxml2** 

```
tar xf libxml2-2.7.2.tar.gz
```

```
cd libxml2-2.7.2
```

```
./configure --prefix=/usr/local/libxml2
```

```
make 
``` 

```
make install
```

 **2. 安装libmcrypt** 
 
```
tar xf libmcrypt-2.5.7.tar.gz
```

```
cd libmcrypt-2.5.7
``` 

```
./configure --prefix=/usr/local/libmcrypt/
```

```
make
``` 

``` 
make install
```

 **3. 安装libpng** 

```
tar xf libpng-1.4.3.tar.bz2
```

```
cd libpng-1.4.3
```

```
yum -y install zlib-devel
```

```
./configure --prefix=/usr/local/libpng
```

```
make
```

```
make install
```

 **4. 安装jpeg7** 

```
tar xf jpegsrc.v7.tar.gz
```

```
cd jpeg-7/
```

```
./configure --prefix=/usr/local/jpeg-7
```

```
make
```

```
make install
```

 **5. 安装freetype** 

```
tar xf freetype-2.4.0.tar.gz
```

```
cd freetype-2.4.0
```

```
./configure --prefix=/usr/local/freetype
```

```
make

```

```
make install
```

 **6. 安装autoconf** 

```
tar xf autoconf-2.69.tar.gz
```

```
cd autoconf-2.69
```

```
./configure
```

```
make
```

```
make install
```

 **7. 安装GD库文件** 

```
tar xf libgd-gd-libgd-9f0a7e7f4f0f.tar.gz
```

```
cd libgd-gd-libgd-9f0a7e7f4f0f
```

```
cmake .
```

```
make
```

```
make install
```

 **8. 安装php** 

```
tar -xf php-5.4.16.tar.gz
```

``` 
cd php-5.4.16
```

```
./configure --prefix=/usr/local/php --with-apxs2=/usr/local/apache/bin/apxs --with-mysql=/usr/local/mysql --with-mysqli=/usr/local/mysql/bin/mysql_config --with-libxml-dir=/usr/local/libxml2/ --with-jpeg-dir=/usr/local/jpeg-7/ --with-png-dir=/usr/local/libpng/ --with-freetype-dir=/usr/local/freetype/ --with-gd --with-zlib-dir=/usr/local/zlib/ --with-mcrypt=/usr/local/libmcrypt/ --enable-soap --enable-mbstring=all --enable-sockets
```

```
make
```

```
make install
```

 **9. 为php提供配置文件** 

```
cp /usr/local/src/php/php-5.4.26/php.ini-production /etc/php.ini
```

---






### 五、整合Apache和PHP

 **1. 编辑apache配置文件httpd.conf，以apache支持php** 

* 首先要在apache配置文件中定义,使apache能够处理php结尾的文件 ,全文查找AddType字段，添加一下内容

```
vim /usr/local/apache/conf/httpd.conf
```

添加三行



> AddType application/x-httpd-php  .php

> AddType application/x-httpd-php-source  .phps

> PHPIniDir "/etc/php.ini"

* 定位至DirectoryIndex index.html修改为：

> DirectoryIndex  index.php  index.html

 **2. 重启Apache服务** 

```
service httpd start
``` 
 
测试页

```
vim /usr/local/apache/htdocs/index.php

```

> 
>   phpinfo(); 

> ?>
> 


---





### 六、安装Xcache加速器 

 **1. 安装xcache-3.1.0** 

```
tar xf xcache-3.1.0.tar.gz
```

```
cd /usr/local/src/xcache-3.1.0
```

```
/usr/local/php/bin/phpize
```

```
./configure --enable-xcache --with-php-config=/usr/local/php/bin/php-config
```

```
make
``` 
 
```
make install
```

编译完成，让php支持xcache功能前提要把xcache的配置信息添加到php的配置文件中


> Installing shared extensions:  
   
> /usr/local/php/lib/php/extensions/no-debug-zts-20100525/

> /usr/local/php/lib/php/extensions/no-debug-zts-20100525/ 


 **2. 追加配置文件xcache.ini至php.ini** 

```
cat xcache.ini >> /etc/php.ini 
```

```
vim /etc/php.ini

```
接下来编辑 /etc/php.d/xcache.ini，找到``zend_extension``开头的行，修改为如下行：


> [xcache-common] 

> ;; non-Windows example:

> extension = /usr/local/php/lib/php/extensions/no-debug-zts-20100525/xcache.so #修改这一行

> ;; Windows example:

> ; extension = php_xcache.dll



 **3. 重启apache并测试** 

```
service httpd stop
```
```
service httpd start 
```
---





### 七、启用服务器状态
```
vim /usr/local/apache/conf/httpd.conf
```
```
 
   SetHandler server-status
   Require all granted
 
```
 

测试

http://ip/server-status 

---

### 其他



 **centos 安装fmpeg** 
 

```
wget http://www.ffmpeg.org/releases/ffmpeg-3.1.tar.gz
```

```
tar -zxvf ffmpeg-3.1.tar.gz
```

```
cd ffmpeg-3.1
```

```
./configure
```

```
make
```

```
make install
```

 
 
等待时间略长
.
.
.
.
.
.
.
.
.
 

查看一下版本

```
ffmpeg -version
```
 

 

安装过程中出现以下错误：



> yasm/nasm not found or too old. Use –disable-yasm for a crippled build.
> 
> If you think configure made a mistake, make sure you are using the latest
> version from Git. If the latest version fails, report the problem to the
> ffmpeg-user@ffmpeg.org mailing list or IRC #ffmpeg on irc.freenode.net.
> Include the log file “config.log” produced by configure as this will help
> solve the problem.

  

需要安装yasm


```
wget http://www.tortall.net/projects/yasm/releases/yasm-1.3.0.tar.gz
```

```
tar -zxvf yasm-1.3.0.tar.gz
```

```
cd yasm-1.3.0
```

```
./configure
```

```
make
```
```
make install
```
 
 

``ffmpeg 主要是用于解码的, 如果需要重新编码, 就需要安装新的第三方编码支持``

参考文章:

* http://blog.creke.net/801.html

* http://www.centoscn.com/image-text/install/2015/0523/5512.html

 

** 重新编译ffmpeg** 

**1.进入ffmpeg目录** 

```
./configure --prefix=/usr/local/ --enable-gpl --enable-version3 --enable-nonfree --enable-shared --enable-zlib --enable-bzlib --enable-libmp3lame --enable-libx264 --enable-pic --enable-libfaac
```

 **生成了新的makefile** 

** 2.执行** 

```
sudo make clean
```

```
make sudo make install
```

**3.这样ffmpeg就被重新编译了，完了就可以验证一下，使用ffmpeg工具，把某个视频文件中的视频流转码成h264格式，音频流转码成mp3lame格式，不妨试试。
**  
 

转MP3错误情况：
 
> “ffmpeg: error while loading shared libraries: libmp3lame.so.0: cannot open shared object file: No such file or directory”

等类似的错误 解决办法是建立软链接：
 
```
ln -s /usr/local/lib/libmp3lame.so.0.0.0 /usr/lib64/libmp3lame.so.0
```

或者修改
/etc/ld.so.conf

```
vi  /etc/ld.so.conf
```

新增一行 


> /usr/local/lib



.......................................................................................................................

 
###  CentOS 6.6下安装OpenOffice4.0


 **1、首先先下载好需要的rpm包：** 


* Apache_OpenOffice_4.0.0_Linux_x86-64_install-rpm_zh-CN.tar.gz


或直接命令下载： 

```
wget http://heanet.dl.sourceforge.NET/project/openofficeorg.mirror/4.0.0/binaries/zh-CN/Apache_OpenOffice_4.0.0_Linux_x86-64_install-rpm_zh-CN.tar.gz
```


放到服务器的目录下（我放到了opt下）


 **2、将下载的openoffice解压（我直接解压到opt目录）：** 

```
tar -zxvf Apache_OpenOffice_4.0.0_Linux_x86-64_install-rpm_zh-CN.tar.gz
```

 **3、解压后生成文件夹zh-CN 进到RPMS目录下，直接** 
```
yum localinstall *.rpm
```
 **4、再装 RPMS/desktop-integration目录下的 openoffice4.0-redhat-menus-4.0-9702.noarch.rpm：** 

``` 
yum localinstall openoffice4.0-redhat-menus-4.0-9702.noarch.rpm
```
 
 **5、安装完成直接启动Openoffice服务：** 

临时启动   
```
/opt/openoffice4/program/soffice -headless -accept="socket,host=127.0.0.1,port=8100;urp;" -nofirststartwizard
```

一直后台启动 
```
nohup  /opt/openoffice4/program/soffice -headless -accept="socket,host=127.0.0.1,port=8100;urp;" -nofirststartwizard &
```
 **6、查看服务是否启动（端口8100是否被soffice占用）：** 

```
netstat -lnp |grep 8100
```

显示结果：

> tcp        0      0 127.0.0.1:8100              0.0.0.0:*                   LISTEN      19501/soffice.bin 






























 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ec6feb02476c852de889233f7cdbeab0645d3f4fcd25565e1d7c1775fc1f9c3945ef54a480cfd572fe1d8a169ca77c9bea44152fe46d99278bfdba4c2839321860763a195a88410b4d9014533de58024aaef1b0f2055d203243cbe494c683fdf4)