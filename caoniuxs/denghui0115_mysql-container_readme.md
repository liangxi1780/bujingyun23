MySQL SQL Database Server Container Image
======================================

This repository contains Dockerfiles for MySQL images for OpenShift and general usage.
Users can choose between RHEL, Fedora and CentOS based images.

For more information about using these images with OpenShift, please see the
official [OpenShift Documentation](http://u.720life.cn/g/6ae0e92e990cb67403a1ae7ffa620b4ebaa245765fc9a76e91879b7e4fc97eb1f6cafdc6277dc6ac66196f8733eb3f6b41384a321434a4a3caa9853d28a645e8).

For more information about contributing, see
[the Contribution Guidelines](http://u.720life.cn/g/54145d0471d91890860f7f8463c030460455d92cbdac5837189f91231ce619271afb41846ebeacce7efe62f40d9a32c7a4e9166e4f7c58a365c40e50283b072d).
For more information about concepts used in these container images, see the
[Landing page](http://u.720life.cn/g/54145d0471d91890860f7f8463c030460455d92cbdac5837189f91231ce6192712bc1360bbb47f90f98e8872f53a8deb).


Versions
---------------
MySQL versions currently provided are:
* [MySQL 8.0](8.0)

RHEL versions currently supported are:
* RHEL7
* RHEL8

CentOS versions currently supported are:
* CentOS7


Installation
----------------------
Choose either the CentOS7 or RHEL7 based image:

*  **RHEL7 based image**

    These images are available in the [Red Hat Container Catalog](http://u.720life.cn/g/03e72d70085c7c05ff73e86e211b084228e0aef424e1b885632b2d236804aa24c8cc42122fa59e500e32fe432f0070857aad22d37c8245ca92b2b6183e7be2105272fed320dd38d964a858adb61fee2fcbaf4ee190395c360fedb67f68fdca83).
    To download it run:

    ```
    $ podman pull registry.access.redhat.com/rhscl/mysql-80-rhel7
    ```

    To build a RHEL7 based MySQL image, you need to run Docker build on a properly
    subscribed RHEL machine.

    ```
    $ git clone --recursive https://github.com/sclorg/mysql-container.git
    $ cd mysql-container
    $ git submodule update --init
    $ make build TARGET=rhel7 VERSIONS=8.0
    ```

*  **CentOS7 based image**

    This image is available on DockerHub. To download it run:

    ```
    $ podman pull centos/mysql-80-centos7
    ```

    To build a CentOS based MySQL image from scratch, run:

    ```
    $ git clone --recursive https://github.com/sclorg/mysql-container.git
    $ cd mysql-container
    $ git submodule update --init
    $ make build TARGET=centos7 VERSIONS=8.0
    ```

For using other versions of MySQL, just replace the `8.0` value by particular version
in the commands above.

Note: while the installation steps are calling `podman`, you can replace any such calls by `docker` with the same arguments.

**Notice: By omitting the `VERSIONS` parameter, the build/test action will be performed
on all provided versions of MySQL, which must be specified in  `VERSIONS` variable.
This variable must be set to a list with possible versions (subdirectories).**


Usage
---------------------------------

For information about usage of Dockerfile for MySQL 8.0,
see [usage documentation](8.0).


Test
---------------------------------

This repository also provides a test framework, which checks basic functionality
of the MySQL image.

Users can choose between testing MySQL based on a RHEL or CentOS image.

*  **RHEL based image**

    To test a RHEL7 based MySQL image, you need to run the test on a properly
    subscribed RHEL machine.

    ```
    $ cd mysql-container
    $ git submodule update --init
    $ make test TARGET=rhel7 VERSIONS=8.0
    ```

*  **CentOS based image**

    ```
    $ cd mysql-container
    $ git submodule update --init
    $ make test TARGET=centos7 VERSIONS=8.0
    ```

For using other versions of MySQL, just replace the `8.0` value by particular version
in the commands above.

**Notice: By omitting the `VERSIONS` parameter, the build/test action will be performed
on all provided versions of MySQL, which must be specified in  `VERSIONS` variable.
This variable must be set to a list with possible versions (subdirectories).**



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ec188b9c59d4bccc3d45564b6ffc96427049b8c3e97b789342476005b7fcb12627f84bab82ed7db9d5b3d8669f23b108ffb727077d2729fcc620b84e9a4528031)