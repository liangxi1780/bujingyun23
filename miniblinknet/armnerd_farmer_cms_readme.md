server {
   listen 80;
   server_name www.kaixiang.com;
   root /data/kaixiang/public;
   index index.html
   index.php;
   location / {
        try_files $uri $uri/
        /index.php$is_args$query_string;
   }
   location ~ \.php$ {
        try_files $uri =404;
        fastcgi_pass 127.0.0.1:9000;
        fastcgi_index index.php;
        fastcgi_param SCRIPT_FILENAME
        $document_root$fastcgi_script_name;
        include fastcgi_params;
   }
}



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e130131ca2c200bfbaa90d8d60a594faa0dee819dbee548add79a287f41b68ffc3b290f7a91c577a1bc11464c397c6375)