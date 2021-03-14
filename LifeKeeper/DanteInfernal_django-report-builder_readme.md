# django-report-builder

A GUI for Django ORM. Build custom queries and display results.
Targets sys admins and capable end users who might not be able to program or gain direct interactive shell access.

[![pipeline status](https://gitlab.com/burke-software/django-report-builder/badges/master/pipeline.svg)](https://gitlab.com/burke-software/django-report-builder/commits/master)
[![coverage report](https://gitlab.com/burke-software/django-report-builder/badges/master/coverage.svg)](https://gitlab.com/burke-software/django-report-builder/commits/master)

# News

## 6.2

- Added partial Python 3.7 support. We can't fully support Python 3.7 until Celery does.

## 6.1

- Added Django 2.1 support. 2.0 and 1.11 are still supported.

## 6.0

- Added django 2.0 support. Dropped support for Django 1.8 and 1.10 as Django no longer supports them
- Bug fixes

# What is Django Report Builder?

![](docs/screenshots/reportbuilderscreen.jpg)

## Features

* Add filters
* Add display fields
* Preview and create xlsx reports
* Very simple security, user must have change or "view" permission to view
  reports. Unprivileged users can still build reports and see database schema.
* Model properties (thanks yekibud)
* Export to Report global admin action
* Scheduled reports can generate and send to users on cron like schedule
* Optional asynchronous report generation

# Documentation

http://django-report-builder.readthedocs.org/

[Google group](http://u.720life.cn/g/941693b557d072bb769494a6a61fcd979ee9fee4d4fd0c2a6b8a30bc68eade21dc2add269a0934b43ce0f8ddda15ea8612dac84ed8d299eba532eaa00eee13bd).

[Contributing](http://u.720life.cn/g/4f754cd38d2f7b6bda48877bfc52758b66466c61f072d54646ca0e38e1b9629ec367a76e9db6ecc4ae93452fec85106f0497dc6916174ae632d3d01627aca8cd1f1f3532ec2505f63a5787bd74c990df)



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ec050cf791e78da14f674310d4cc991752c6d61c2aaf01d1020ff7504165f8f22e6c2ea0fd5cc10c512b9d686c2f511fe4982560a80a1ac6758ed41abf4155e41)