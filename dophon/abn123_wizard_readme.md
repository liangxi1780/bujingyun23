# Wizard 开源文档管理系统

![GitHub All Releases](https://img.shields.io/github/downloads/mylxsw/wizard/total)
![Docker Pulls](https://img.shields.io/docker/pulls/mylxsw/wizard)

## 概述

Wizard是一款开源文档管理系统，目前支持三种类型的文档管理

- **Markdown**：也是Wizard最主要的文档类型，研发团队日常工作中交流所采用的最常用文档类型，在 Wizard 中，对 [Editor.md](http://u.720life.cn/g/db08e82e8a423dbbc7bd3115b44ffe3193110e9cbd370ca283774323c60717d3730ac23c7f22136005db8474674be57e) 项目进行了功能扩展，增加了文档模板，Json 转表格，图片粘贴上传等功能
- **Swagger**：支持 [OpenAPI 3.0](http://u.720life.cn/g/144fc7dac4f8956d4599e1fe5c1bbcf8193fa7119a5951829fc22b7a6559d653d164913aa2c83b1c1e4b8217b59973e1) 规范，集成了 Swagger 官方的编辑器，支持文档模板，全屏编辑，文档自动同步功能
- **Table**：这种文档类型是类似于 Excel 电子表格，集成了 [x-spreadsheet](http://u.720life.cn/g/54145d0471d91890860f7f8463c030469b5abe7dc7d19ceb223f525bab731075f66706e199de7a84f41dc1593227fe2f) 项目

> 在Wizard中，正在编辑的文档会定时自动保存到本地的 Local Storage 中，避免错误关闭页面而造成编辑内容丢失。

目前主要包含以下功能

- Swagger，Markdown，[Table](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046244e13198d277f5b0312b4f6b835c67a02d17274b6628e72c62fc70698d20e7058eb7fcf3bbc57f28186a6fbb4ff46153f8d581cdacf65ae8922dd8d537bf8a64f713f7b1ef72a3cdc4ec23053b5aa701d4d3a0a012512962eae1f2827b977e2) 类型的文档管理
- [文档修改历史管理](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046244e13198d277f5b0312b4f6b835c67a2e967789f97300da0e28d3e21cb238d00236608ec003f0c59349460a2ac792212a105743dbdd86b1d2de4407c96cd3c392c16f1054df42a85c6d220438bb683a4baaa86e56e91bdde6e4113c0837ea8b2de0acafe143119862241d860c0a1ce5d8a489bbcc64b0eaf91ac3d79c866e4de73790aec838c955888acd38d80efafa)
- [文档修改差异对比](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046244e13198d277f5b0312b4f6b835c67a2e967789f97300da0e28d3e21cb238d00236608ec003f0c59349460a2ac792212a105743dbdd86b1d2de4407c96cd3c392c16f1054df42a85c6d220438bb683a4baaa86e56e91bdde6e4113c0837ea8b2de0acafe143119862241d860c0a1ce5d8a489bbcc64b0eaf91ac3d79c866e4de73790aec838c955888acd38d80efafa)
- 用户权限管理
- 项目分组管理
- LDAP 统一身份认证
- 文档搜索，标签搜索
- 阅读模式
- 文档评论
- 消息通知
- 文档分享
- 统计功能
- [流程图，序列图，饼图，Tex LaTex 科学公式支持](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046244e13198d277f5b0312b4f6b835c67afe1af6b374d73ad5f0353314d3db471b096fb32fd6e5e25392641076eeffcdfbe813846e8a9e9a0afda1d8bc7ad56d2bf5be911918ec235d8a76dc1d74dacc93078af0597445aa011452dfe87658f8aaade9d193fcf59a91cd763dff7c05b49375cb3425fd4cabadb78640cc43173cc3ddd5e7f8c0d2ddb9080287f09cbed56d3f501fc0a9d6fa72f7d14dcf3a9699b22cf7407ef17bc058ffa8774be42b729f2cbba6261d743a0722c03420ae5e821f)
- [多主题切换](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046244e13198d277f5b0312b4f6b835c67a91ef30927b4b14f4a69b4ea3c7a3f69a0e844eb05d7b96bb04ba0eb213e92fe6ba9e741b9f0af23c5515d2ae21b0b24be8c3a82d74b66da860c738093f5afd88)

如果想快速体验一下Wizard的功能，有两种方式

- 在线体验请访问 [http://wizard.aicode.cc/](http://u.720life.cn/g/84849802f16c9e4d5064c8c792b7c795854acc4fe611dc4d64e47d6111bd28ed) ，目前只提供部分功能的体验，功能预览和使用说明请参考 [Wiki](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046244e13198d277f5b0312b4f6b835c67a12f6a95cd7b5d964130d98f96238e060)。
- 使用Docker来创建一个完整的Wizard服务
    
    进入项目的根目录，执行 `docker-compose up`，就可以快速创建一个Wizard服务了，访问地址 http://localhost:8080 。

## 起源

为了鼓励大家在开发过程中写开发文档，最开始我们选择了 [ShowDoc](http://u.720life.cn/g/77503fbe1554ad792c30c5582d9b0331124e382e5e7965bae730780b1779b14b) 项目来作为文档管理工具，当时团队规模也非常的小，大家都是直接用 Markdown 写一些简单的开发文档。后来随着团队的壮大，前后端分离，团队分工的细化，仅仅采用 Markdown 开始变得捉襟见肘，这时候，我们首先想到了使用开源界比较流行的 [Swagger](http://u.720life.cn/g/144fc7dac4f8956d4599e1fe5c1bbcf883c55dd9d71a04eb7bc64e107270e142) 来创建开发文档。但是 Swagger 文档多了，总得有个地方维护起来吧？

项目中的文档仅仅用Swagger也是不够的，它只适应于API文档的管理，还有很多其它文档，比如设计构想，流程图，架构文档，技术方案，数据库变更等各种文档需要一起维护起来。因此，我决定利用业余时间开发一款 **集成 Markdown 和 Swagger 文档的管理工具**，也就是 **Wizard** 项目了。

起初Wizard项目的想法比较简单，只是用来将 Markdown 文档和 Swagger 文档放在一起，提供一个简单的管理界面就足够了，但是随着在团队中展开使用后，发现在企业中作为一款文档管理工具来说，只提供简单的文档管理功能是不够的，比如说权限控制，文档修改历史，文档搜索，文档分类等功能需求不断的被提出来，因此也促成了 Wizard 项目的功能越来越完善。

- **用户权限管理** 参考了 Gitlab 的权限管理方式，在用户的身份上只区分了 **管理员** 和 **普通用户**，通过创建**用户组**来对用户的权限进行细致的管理，同时每个项目都支持单独的为用户赋予读写权限。
- **项目分组** 在 Wizard 中，文档是以项目为单位进行组织的，刚开始的时候发现这样是OK的，后来项目越来越多，项目分组功能应运而生，以目录的形式来组织项目结构。
- **文档修改历史** 每次对文档的修改，Wizard 都会记录一个快照，避免错误的修改了文档而造成损失，可以通过文档历史快速的恢复文档，对文档的修改，新增，删除等关键操作都会记录审计日志，以最近活动的形式展示出来。
- **文档差异对比** 在团队协助中，经常会出现很多人修改同一份文档，为了避免冲突，文档修改后，其它人在提交旧的历史版本时，系统会提示用户文档内容发生了变更，用户可以通过文档比对功能找出文档中有哪些内容发生了修改。
- **阅读模式** 当使用投影仪展示文档来过技术方案的时候，为了减少不必要的干扰，使用阅读模式，只展示文档内容部分，提供更好的展示体验。
- **文档搜索** 通过搜索功能快速查找需要的文档，目前支持通过文档标题来搜素文档，后续会增加全文检索功能。
- **LDAP支持** 很多公司都会使用 LDAP 来统一的管理公司员工的账号，员工的在公司内部的所有系统中都是用同一套帐号来登录各种系统比如 Jira，Wiki，Gitlab 等，Wizard 也提供了对 LDAP 的支持，只需要简单的几个配置，就可以快速的接入公司的统一帐号体系。
- **文档附件**，**文档分享**，**统计**，**文档排序**，**模板管理**，**文档评论** ...


## 功能演示

请查看项目的 [Wiki](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046244e13198d277f5b0312b4f6b835c67a12f6a95cd7b5d964130d98f96238e060) 文档。

![Wizard-功能预览图](https://ssl.aicode.cc/mweb/Wizard-%E5%8A%9F%E8%83%BD%E9%A2%84%E8%A7%88%E5%9B%BE.gif)

## 关于代码

项目采用了 Laravel 开发框架开发，目前框架的版本已经升级到最新的 5.8（最开始为5.4，一路升级过来）。为了提高开发效率，保持架构的简洁，在开发过程中，一直避免引入过多的外部组件，尽可能的利用 Laravel 提供的各种组件，比如 **Authentication**，**Authorization**，**Events**，**Mail**，**Notifications** 等，非常适合Laravel新手利用该项目来学习Laravel开发框架。

## 安装

目前支持两种安装方式，如果你熟悉Docker，可以直接使用Docker容器的方式来运行该项目，这也是最简单的方式了。如果你没有使用Docker或者不知道什么是Docker，那么请直接参考手动安装部分。

### 通过 Docker 安装 

详细安装方法参考 Docker Hub [mylxsw/wizard](http://u.720life.cn/g/ce46a7789a867c84732a8edd85365befc3d7dc32436da5ca07d2f953b7427a1bb1fb6c96c449a47496d5e073e5a0a0f7)。

我们需要创建一个Dockerfile，在Dockerfile中添加环境配置，比如我采用了宿主机上安装的MySQL服务器，就有了下面的这段Dockerfile配置

    FROM mylxsw/wizard:latest

    # 数据库连接配置
    # 这里可以根据需要添加其它的Env配置，可用选项参考项目的.env.example文件
    ENV DB_CONNECTION=mysql
    ENV DB_HOST=host.docker.internal
    ENV DB_PORT=3306
    ENV DB_DATABASE=wizard_2
    ENV DB_USERNAME=wizard
    ENV DB_PASSWORD=wizard
    ENV WIZARD_NEED_ACTIVATE=false
    # 访问地址，只有正确配置后，导出的 markdown 文档图片才能正常展示
    ENV APP_URL=http://localhost:8080
    
    # 文件上传存储目录
    VOLUME /webroot/storage/app/public

    RUN php artisan config:cache

执行构建

    docker build -t my-wizard .

数据库初始化

    docker run -it --rm --name my-wizard my-wizard php artisan migrate:install
    docker run -it --rm --name my-wizard my-wizard php artisan migrate

运行

    docker run -d --name my-wizard -p 8080:80  my-wizard

然后就可以通过 http://localhost:8080 访问 Wizard 了。    

### 手动安装

手动安装方式需要先安装配置好PHP环境，建议采用 PHP-FPM/Nginx 的方式来运行，具体配置参考 环境依赖 部分。

#### 环境依赖

以下组件的安装配置这里就不做详细展开，可以自行 百度/Google 安装方法。

- PHP 7.2 + (需要启用以下扩展)
    - OpenSSL PHP Extension
    - PDO PHP Extension
    - Mbstring PHP Extension
    - Tokenizer PHP Extension
    - XML PHP Extension
    - Ctype PHP Extension
    - JSON PHP Extension
    - BCMath PHP Extension
    - LDAP PHP Extension
    - Zlib PHP Extension （PDF 导出功能需要用到）
- composer.phar
- MySQL 5.7 + / MariaDB （需要支持ARCHIVE存储引擎，MariaDB 10.0+ 默认没有启用参考 **FAQ 3**）
- Nginx
- Git

> PHP 运行环境的创建，可以参考这里 https://gist.github.com/mylxsw/4b7bbe81fb7f59714423f3284c867149

#### 下载代码

推荐使用 git 来下载项目代码到服务器，我们假定将该项目放在服务器的 `/data/webroot` 目录

    cd /data/webroot
    git clone https://github.com/mylxsw/wizard.git
    cd wizard

下载代码之后，使用 **composer** 安装项目依赖

    composer install --prefer-dist --ignore-platform-reqs

composer 会在在项目目录中创建 **vender** 目录，其中包含了项目所依赖的所有第三方代码库。

> 你也可以直接到项目的 [release](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046244e13198d277f5b0312b4f6b835c67a6f52393a4ffacae4454d1e34f0336885) 页面直接下载包含依赖的软件包。

#### 配置

复制一份配置文件 

    cp .env.example .env

修改 `.env` 中的配置信息，比如 MySQL 连接信息，文件存储目录，项目网址等。

接下来创建数据库，提前在MySQL中创建好项目的数据库，然后在项目目录执行下面的命令

    php artisan migrate:install
    php artisan migrate

接下来配置文件上传目录

    php artisan storage:link

执行该命令后会在 public 目录下创建 `storage/app/public` 目录的符号链接。

在Nginx中配置项目的访问地址

    server {
        listen       80;
        server_name  wizard.example.com;
        root         /data/webroot/wizard/public;
        index        index.php;
    
        location / {
            index index.php index.html index.htm;
            try_files $uri $uri/ /index.php?$query_string;
        }
        
        location ~ .*\.(gif|jpg|png|bmp|swf|js|css)$ {
            try_files $uri  =302;
        }
        
        location ~ .*\.php$ {
            # php-fpm 监听地址，这里用了socket方式
            fastcgi_pass  unix:/usr/local/php/var/run/php-cgi.sock;
            fastcgi_param SCRIPT_FILENAME $document_root$fastcgi_script_name;
            fastcgi_index index.php;
            include fastcgi_params;
        }
    }

#### 升级

项目升级过程非常简单，只需要使用git拉取最新代码（git pull），然后执行下面的命令完成数据库迁移和依赖更新就OK了。

    composer install --prefer-dist --ignore-platform-reqs
    php artisan migrate

### 初始化

安装完成后，Wizard项目就可以通过浏览器访问了，接下来需要访问注册页面创建初始用户 

    http://项目地址/register

在系统中注册的第一个用户为默认管理员角色。

## FAQ

1. 如果在执行数据库迁移（`php artisan migrate`）的时候，报错 `SQLSTATE[42000]: Syntax error or access violation: 1071 Specified key was too long; max key length is 767 bytes`

    该错误是因为 MySQL 版本低于 5.7，在低版本的 MySQL 中会出现该问题。解决方案如下，二选一即可

    - 在 `.env` 文件中添加配置项 `DB_CHARSET=utf8` 和 `DB_COLLATION=utf8_unicode_ci`，添加之后再执行 `php artisan migrate` 命令（缺点是这样就不支持Emoji了）
    - 升级MySQL到 5.7

2. 报错 `SQLSTATE[HY000] [2054] The server requested authentication method unknown to the client` 和 `The server requested authentication method unknown to the client [caching_sha2_password]`

    因为Mariadb版本比较新，对应的MySQL版本在8.0之后也可能会有问题（默认认证方式修改为了`caching_sha2_password`），解决办法连接到数据库，修改一下密码的认证方式为 `mysql_native_password`：

        ALTER USER 'USERNAME'@'HOSTNAME' IDENTIFIED WITH mysql_native_password BY 'PASSWORD';

    > 参考 [Caching SHA-2 Pluggable Authentication](http://u.720life.cn/g/95e6cdfc419b9fe3e81ac644ae2e762dc8e0907e9811698ec9bac55e21109eb3dc03eed4ec5a04f4e1e310ac9051f6b3c5bf9736fcf776563187bb50f6539dade1626a34901b034efc1f605ab4791a5a076c738ae634a6af8d9f6a48b4fd6a46)

3. 数据库使用 Mariadb 10.0+ 版本时，执行数据库迁移报错 `Unknown storage engine 'ARCHIVE'` 

    操作日志存储用到了 **ARCHIVE** 存储引擎，Mariadb 10.0 版本之后默认是没有安装这个存储引擎的

    > The ARCHIVE storage engine was installed by default until MariaDB 10.0. In MariaDB 10.1 and later, the storage engine's plugin will have to be installed.

    所以解决方案有下面这两种（**推荐第一种**）

    1. 最简单的方式时在Mariadb中安装这个插件，只需要连接到Mariadb之后执行 `INSTALL SONAME 'ha_archive';` 命令就可以了，**不需要** 重启数据库

    2. 第二种办法时不安装 **ARCHIVE** 存储引擎，修改 `$WIZARD_HOME/database/migrations/2017_08_03_232417_create_operation_logs_table.php` 文件的第 17 行，将`$table->engine = 'ARCHIVE';` 注释掉（完成迁移之后记得改回去，避免以后使用 `git pull` 来升级系统产生冲突）
        
        ```diff
         Schema::create('wz_operation_logs', function (Blueprint $table) {
        -$table->engine = 'ARCHIVE';
        +// $table->engine = 'ARCHIVE';
         
         $table->increments('id');
        ```

4. 默认上传文件大小限制为 2M，这个限制并不是 Wizard 自身的限制，而是运行环境的限制，如何提高上传文件大小限制呢？

   首先需要修改 PHP 的配置文件 `php.ini`，修改以下两行
   
       ; 上传文件大小限制
       upload_max_filesize = 100M
       ; 表单提交大小限制，必须大于 upload_max_filesize，或者可以设置为 0，不做任何限制
       post_max_size = 0
   
   然后，根据 web 服务器的不同进行修改
   
   - **nginx**： 在 nginx 配置中添加 `client_max_body_size 120M;` 来指定最大 body 大小，可以参考 `docker-compose/nginx.conf` 的配置
   - **apache**：修改 Wizard 目录 `public/.htaccess` 文件中 `LimitRequestBody 0` 选项的值即可，默认为0表示不限制（默认已经修改过）

5. 导出 Markdown 文档后，图片地址错误，无法显示图片

   需要配置 `APP_URL` 环境变量参数，在 `.env` 文件中，修改 `APP_URL` 地址为当前访问 URL 地址即可。

## Stargazers over time

[![Stargazers over time](https://starchart.cc/mylxsw/wizard.svg)](https://starchart.cc/mylxsw/wizard)



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e4f09654dc13f0727917a46d3898718f95d74b6ad43b18ce1350a763a01dae3d41c566c04eae3f1628ed23ea1ae651296)