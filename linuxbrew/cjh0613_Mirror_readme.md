# upupming Mirror v0.0.1

> Note: This version is useful if you have your own server, if you don't have a server, please consider use [v0.0.2](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046ba3ac09850a99a101215f31650076112a44e4588d5f45dea26c85e6a47f9e08c).

Self-hosted mirror(Hosted at https://mirror.upupming.site) websites for Google and Chinese Wikipedia, keeping *to organize the world's information and make it universally accessible and useful* in mind.

- Google
  - [Google Search][1]
    - AMP is too difficult to supported. If you see an AMP page, please request desktop site.
  - [Google Scholar][2]
  - [Google Maps][3]
  - [Google Translate][4]
  - [Google Docs][5]
  - [Google Codejam][8]
  - All other subdomains of google.com
- Chinese Wikipedia
  - [Chinese Wikipedia Desktop][7]
  - [Chinese Wikipedia Mobile][6]

[1]:https://google.upupming.site/
[2]:https://scholar.google.upupming.site/
[3]:https://maps.google.upupming.site
[4]:https://translate.google.upupming.site/
[5]:https://docs.google.upupming.site
[6]:https://mwiki.upupming.site/w/index.php?title=Wikipedia:%E9%A6%96%E9%A1%B5&mobileaction=toggle_view_mobile
[7]:https://wiki.upupming.site/w/index.php?title=Wikipedia:%E9%A6%96%E9%A1%B5&mobileaction=toggle_view_desktop
[8]:https://code.google.upupming.site/codejam/

## Edit this site

Fork this repository, and then follow the [README](./new-age-README.md) of new age theme.

## SSL certificate

Using certbot to get Let's encrypt SSL certificate.

See https://github.com/certbot/certbot

All in one certificate:

```bash
./certbot-auto certonly --agree-tos --manual \
-d *.upupming.site \
-d *.google.upupming.site \
-d *.blog.upupming.site \
-d *.git.upupming.site \
-d  *.gstatic.upupming.site
```

Individual certificates:

```bash
./certbot-auto certonly --agree-tos -t --standalone -d  
```

## Nginx configuration

### compile Nginx from source with necessary modules

#### Download the source and configure

https://docs.nginx.com/nginx/admin-guide/installing-nginx/installing-nginx-open-source/#sources_download
https://nginx.org/en/docs/configure.html 

#### ngx_http_substitutions_filter_module

`subs_filter` is used for substitute string A to string B, and regular expressions are supported compared to `sub_filter`.

See https://github.com/yaoweibin/ngx_http_substitutions_filter_module

#### My configuration parameters

```bash
./configure \
    --user=www \
    --group=www \
    --prefix=/usr/local/nginx \
    --with-http_stub_status_module \
    --with-http_ssl_module \
    --with-http_gzip_static_module \
    --with-http_sub_module \
    --with-http_ssl_module \
    --add-module=/root/ngx_http_substitutions_filter_module \
    --with-pcre=../pcre-8.42
```

### Nginx Configuration

My configuration file [/usr/local/nginx/conf/nginx.conf](./nginx.conf). This config file implements:

1. Replace all links to original website to your proxied website on web pages.
2. Google Analysis & Adsense
3. All subdomains proxy strategy
4. `robots.txt` to avoid server overload.

### Start Nginx server

```bash
nginx
```



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ee9415ab89750846e388caf1cb93ca7bbc3c58c5d90487f2fff47321d93e6fcda1838e1042c0badd75e95f55f1283f3a2)