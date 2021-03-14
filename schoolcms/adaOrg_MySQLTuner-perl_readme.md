MySQLTuner-perl
====
[![Build Status - Master](https://travis-ci.org/major/MySQLTuner-perl.svg?branch=master)](https://travis-ci.org/major/MySQLTuner-perl)
[![Project Status](http://opensource.box.com/badges/active.svg)](http://opensource.box.com/badges)
[![Project Status](http://opensource.box.com/badges/maintenance.svg)](http://opensource.box.com/badges)
[![Average time to resolve an issue](http://isitmaintained.com/badge/resolution/major/MySQLTuner-perl.svg)](http://isitmaintained.com/project/major/MySQLTuner-perl "Average time to resolve an issue")
[![Percentage of open issues](http://isitmaintained.com/badge/open/major/MySQLTuner-perl.svg)](http://isitmaintained.com/project/major/MySQLTuner-perl "Percentage of issues still open")
[![GPL License](https://badges.frapsoft.com/os/gpl/gpl.png?v=103)](https://opensource.org/licenses/GPL-3.0/)

**MySQLTuner** is a script written in Perl that allows you to review a MySQL installation quickly and make adjustments to increase performance and stability.  The current configuration variables and status data is retrieved and presented in a brief format along with some basic performance suggestions.

**MySQLTuner** supports ~300 indicators for MySQL/MariaDB/Percona Server in this last version.

**MySQLTuner** is maintained and indicator collect is increasing week after week supporting a lot of configuration such as [Galera Cluster](http://u.720life.cn/g/550f8d5fd61708fc5ed3090afdfadabebd10b55792c67b98e95ebfc0b9d7dc0c), [TokuDB](http://u.720life.cn/g/6e6d6140da0b4f68f288d6ba7592ad812cb19e3cd3cdd837b164c95c56a306e0a05eec2c3cbf58c7d0d2344f4ac2fee15a8fce6f359e56987e2a4ab920fdf5d2), [Performance schema](http://u.720life.cn/g/54145d0471d91890860f7f8463c030468524db70a796c6e7f331e4d863e7647be55cb199e93a6173c74188c9136fcf30), Linux OS metrics, [InnoDB](http://u.720life.cn/g/b746ab05f6ffa1a5fcc69ded8aa543a679403e2109a415cfdd2a43b30b737daa4b5bdf4934615d351b11f3353e9a3e0505c056805301d304aa7b4260072186d37a672c1cc4ff5a180394fb5ff307a6e2), [MyISAM](http://u.720life.cn/g/b746ab05f6ffa1a5fcc69ded8aa543a679403e2109a415cfdd2a43b30b737daaff303c566be39bed84c0b6d13fe661f5178c001e67dad27f49c251f47efda3db6db0eeae965212e48c952b6edb55de64), [Aria](https://mariadb.com/kb/en/mariadb/aria/), ...

You can find more details on these indicators here:
[Indicators description](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046f10a2117c167d8be3712611090025ce6c8ebaf666f08a08d9cfb404be54350db960e23aebee9e31483e0f5039ed2c0bec3e92bb19eae09f18e924224650f9c89).


![MysqlTuner](https://github.com/major/MySQLTuner-perl/blob/master/mysqltuner.png)

MySQLTuner needs you:
===

**MySQLTuner** needs contributors for documentation, code and feedback..

* Please join us on issue track at [GitHub tracker](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046f10a2117c167d8be3712611090025ce66a07e5a2e3a9ab051c4a1b2a96faf34f).
* Contribution guide is available following [MySQLTuner contributing guide](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046f10a2117c167d8be3712611090025ce6c8ebaf666f08a08d9cfb404be54350db4878ca1c0d3581830e93611878f46b5ba1ba2493ee108046f48a093dc2201e16)
* Star **MySQLTuner project** at [MySQLTuner Git Hub Project](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046f10a2117c167d8be3712611090025ce6c3a31671df44748941ec9d8de06f23b1)
## Stargazers over time

[![Stargazers over time](https://starcharts.herokuapp.com/major/MySQLTuner-perl.svg)](https://starcharts.herokuapp.com/major/MySQLTuner-perl)

Compatibility
====
Test result are available here: [Travis CI/MySQLTuner-perl](http://u.720life.cn/g/41730a1a7cf811a1831a38c04993d30b27e0195bdcbf5d4ef59ab569ad894b9a72ff1b868b4b87fc97caf2c58ed73299)
* MySQL 8 (full support, password checks don't work)
* MySQL 5.7 (full support)
* MySQL 5.6 (full support)
* MySQL 5.5 (full support)
* MariaDB 10.4 (full support)
* MariaDB 10.3 (full support)
* MariaDB 10.2 (full support)
* MariaDB 10.1 (full support)
* MariaDB 10.0 (full support, 6 last month support)
* MariaDB 5.5 (full support, no more MariaDB support)
* Percona Server 8.0 (full support, password checks don't work)
* Percona Server 5.7 (full support)
* Percona Server 5.6 (full support)

* Percona XtraDB cluster (partial support, no test environment)
* Mysql Replications (partial support, no test environment)
* Galera replication (partial support, no test environment)

* MySQL 3.23, 4.0, 4.1, 5.0, 5.1, 5.5 (partial support - deprecated version)

*** UNSUPPORTED ENVIRONMENTS - NEED HELP FOR THAT :) ***
* Windows is not supported at this time (Help wanted !!!!!)
* Cloud based is not supported at this time (Help wanted !!!!!)

* CVE vulnerabilities detection support from [https://cve.mitre.org](http://u.720life.cn/g/64634fe11b5eff95022a721483f701724e17b927e2dd52ec9d2345ec84182f64)

*** MINIMAL REQUIREMENTS ***

* Perl 5.6 or later (with [perl-doc](http://u.720life.cn/g/c81e2516427d1b3c7e6e2c239d6d55017978d858b0b4a5ee20da82955cc367f9b6c4c536d3a1587af545bfc294fff243c9cdded2b30531b46d47957eb3c9b064) package)
* Unix/Linux based operating system (tested on Linux, BSD variants, and Solaris variants)
* Unrestricted read access to the MySQL server (OS root access recommended for MySQL   sysschema.zip
	# check zip file
	unzip -l sysschema.zip
	unzip sysschema.zip
	cd mysql-sys-master
	mysql -uroot -p   mariadb-sys.zip
	# check zip file
	unzip -l mariadb-sys.zip
	unzip mariadb-sys.zip
	cd mariadb-sys-master/
	mysql -u root -p  GRANT SELECT, PROCESS,EXECUTE, REPLICATION CLIENT,SHOW DATABASES,SHOW VIEW ON *.* TO 'mysqltuner'@'localhost' identified by pwd1234;

**Question: It's not working on my OS! What gives?!**

These kinds of things are bound to happen.  Here are the details I need from you in order to research the problem thoroughly:

* OS and OS version
* Architecture (x86, x86_64, IA64, Commodore 64)
* Exact MySQL version
* Where you obtained your MySQL version (OS package, source, etc)
* The full text of the error
* A copy of SHOW VARIABLES and SHOW GLOBAL STATUS output (if possible)

**Question: How to perform CVE vulnerability checks?**

* Download vulnerabilities.csv from this repository.
* use option --cvefile to perform CVE checks

**Question: How to use mysqltuner from a remote host?**
Thanks to  [@rolandomysqldba](http://u.720life.cn/g/981a1443eaef93f66efdce0e979c87134f1409c836e7efe2f7cb7085bf62ad412b9ed95fcdd495ac6998ff87565718cafa89ebde225a0a8cb2e59b0e89b9428f)

* You will still have to connect like a mysql client:

Connection and Authentication

	--host   Connect to a remote host to perform tests (default: localhost)
	--socket   Use a different socket for a local connection
	--port       Port to use for connection (default: 3306)
	--user   Username to use for authentication
	--pass   Password to use for authentication
	--defaults-file   defaults file for credentials

Since you are using a remote host, use parameters to supply values from the OS

	--forcemem    Amount of RAM installed in megabytes
	--forceswap   Amount of swap memory configured in megabytes

* You may have to contact your remote SysAdmin to ask how much RAM and swap you have

If the database has too many tables, or very large table, use this:

	--skipsize           Don't enumerate tables and their types/sizes (default: on)
	                     (Recommended for servers with many tables)

**Question: Can I install this project using homebrew on Apple Macintosh?**

Yes! `brew install mysqltuner` can be used to install this application using [homebrew](http://u.720life.cn/g/2c75a511bea1268ab8a6d5aafe5f0839) on Apple Macintosh.

MySQLTuner and Vagrant
--
**MySQLTuner** contains following Vagrant configurations:
* Fedora Core 30 / Docker

**Vagrant File** is stored in Vagrant subdirectory.
* Follow following step after vagrant installation:
    $ vagrant up

**MySQLTuner** contains a Vagrant configurations for test purpose and development
* Install VirtualBox and Vagrant
	* https://www.virtualbox.org/wiki/Downloads
	* https://www.vagrantup.com/downloads.html
* Clone repository
 	* git clone https://github.com/major/MySQLTuner-perl.git
* Install Vagrant plugins vagrant-hostmanager and  vagrant-vbguest
	* vagrant plugin install vagrant-hostmanager
	* vagrant plugin install vagrant-vbguest
* Add Fedora Core 30 box for official Fedora Download Website
	* vagrant box add --name generic/fedora30
* Create a data directory
	* mkdir data


## setup test environments

    $ sh build/createTestEnvs.sh

    $ source build/bashrc
    $ mysql_percona80 sakila
    sakila> ...

    $ docker images
    mariadb                  10.1                fc612450e1f1        12 days ago         352MB
    mariadb                  10.2                027b7c57b8c6        12 days ago         340MB
    mariadb                  10.3                47dff68107c4        12 days ago         343MB
    mariadb                  10.4                92495405fc36        12 days ago         356MB
    mysql                    5.6                 95e0fc47b096        2 weeks ago         257MB
    mysql                    5.7                 383867b75fd2        2 weeks ago         373MB
    mysql                    8.0                 b8fd9553f1f0        2 weeks ago         445MB
    percona/percona-server   5.7                 ddd245ed3496        5 weeks ago         585MB
    percona/percona-server   5.6                 ed0a36e0cf1b        6 weeks ago         421MB
    percona/percona-server   8.0                 390ae97d57c6        6 weeks ago         697MB
    mariadb                  5.5                 c7bf316a4325        4 months ago        352MB
    mariadb                  10.0                d1bde56970c6        4 months ago        353MB
    mysql                    5.5                 d404d78aa797        4 months ago        205MB

    $ docker ps
    CONTAINER ID        IMAGE                        COMMAND                  CREATED             STATUS              PORTS                               NAMES
    da2be9b050c9        mariadb:5.5                  "docker-entrypoint.s…"   7 hours ago         Up 7 hours          0.0.0.0:5311->3306/tcp              mariadb55
    5deca25d5ac8        mariadb:10.0                 "docker-entrypoint.s…"   7 hours ago         Up 7 hours          0.0.0.0:5310->3306/tcp              mariadb100
    73aaeb37e2c2        mariadb:10.1                 "docker-entrypoint.s…"   7 hours ago         Up 7 hours          0.0.0.0:5309->3306/tcp              mariadb101
    72ffa77e01ec        mariadb:10.2                 "docker-entrypoint.s…"   7 hours ago         Up 7 hours          0.0.0.0:5308->3306/tcp              mariadb102
    f5996f2041df        mariadb:10.3                 "docker-entrypoint.s…"   7 hours ago         Up 7 hours          0.0.0.0:5307->3306/tcp              mariadb103
    4890c52372bb        mariadb:10.4                 "docker-entrypoint.s…"   7 hours ago         Up 7 hours          0.0.0.0:5306->3306/tcp              mariadb104
    6b9dc078e921        percona/percona-server:5.6   "/docker-entrypoint.…"   7 hours ago         Up 7 hours          0.0.0.0:4308->3306/tcp              percona56
    3a4c7c826d4c        percona/percona-server:5.7   "/docker-entrypoint.…"   7 hours ago         Up 7 hours          0.0.0.0:4307->3306/tcp              percona57
    3dda408c91b0        percona/percona-server:8.0   "/docker-entrypoint.…"   7 hours ago         Up 7 hours          33060/tcp, 0.0.0.0:4306->3306/tcp   percona80
    600a4e7e9dcd        mysql:5.5                    "docker-entrypoint.s…"   7 hours ago         Up 7 hours          0.0.0.0:3309->3306/tcp              mysql55
    4bbe54342e5d        mysql:5.6                    "docker-entrypoint.s…"   7 hours ago         Up 7 hours          0.0.0.0:3308->3306/tcp              mysql56
    a49783249a11        mysql:5.7                    "docker-entrypoint.s…"   7 hours ago         Up 7 hours          33060/tcp, 0.0.0.0:3307->3306/tcp   mysql57
    d985820667c2        mysql:8.0                    "docker-entrypoint.s…"   7 hours ago         Up 7 hours          0.0.0.0:3306->3306/tcp, 33060/tcp   mysql 8    0


MySQLTuner needs you
--
**MySQLTuner** needs contributors for documentation, code and feedback..

* Please join us on issue track at [GitHub tracker](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046f10a2117c167d8be3712611090025ce66a07e5a2e3a9ab051c4a1b2a96faf34f).
* Contribution guide is available following [MySQLTuner contributing guide](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046f10a2117c167d8be3712611090025ce6c8ebaf666f08a08d9cfb404be54350db4878ca1c0d3581830e93611878f46b5ba1ba2493ee108046f48a093dc2201e16)
* Star **MySQLTuner project** at [MySQLTuner Git Hub Project](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046f10a2117c167d8be3712611090025ce6c3a31671df44748941ec9d8de06f23b1)



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e45198efc9e1f3e9c77734b8dd6d253130111b0efe77782cc5b938041cccbcdd29f7163019d2b2fd151c9e83eba764afe)