####Powered by python 3 and django 1.9

> Note:
> 目前项目共 2 个分支，blog-tutorial 分支为 Blog 教学项目，该项目附带有配套教程，请参考下方的链接。
>
> dev 分支为我的个人博客的分支，实现了诸多更为高级的特性，并会持续完善和改进以及添加新的功能。具体特性请查看 dev 分支的 readme 文件。

### 项目配套教程

注：如果你完全没有接触过 Django，强烈建议你首先阅读官方文档的入门教程，我们组织首页仓库也有其[中文翻译版本](http://u.720life.cn/g/54145d0471d91890860f7f8463c030464e3cdcf37aef65bbd9abc3fd0b9a0fd87bca20c6a48b16603065a5c45fd9388d916fb7dcab3b9c0daa052f30589b9542)，强烈推荐先阅读该教程以掌握 Django 开发中的一些基础知识。

**第一周**：[Django 学习小组：博客开发实战第一周教程 —— 编写博客的 Model 和首页面](http://u.720life.cn/g/edab4f07812b57c7ea69fa7b67a55e9e9339e409cd99598f4ba0e0f6244f9847f399a25b588fd8633b0c0ec03210f889)

**第二周**：[Django 学习小组：博客开发实战第二周教程 —— 博客详情页面和分类页面](http://u.720life.cn/g/edab4f07812b57c7ea69fa7b67a55e9ea51604d7021b7740f124e23fcdf38d4fc7d0bcca1a700b8e844d984fa7d67c85)

**第三周**：[Django 学习小组：博客开发实战第三周教程——文章列表分页和代码语法高亮](http://u.720life.cn/g/edab4f07812b57c7ea69fa7b67a55e9ed3695d4ac8af382d2933777e31b2076789137c2eea4b55b68b95391e345d083f)

**第四周**：[Django 学习小组：博客开发实战第四周——标签云与文章归档](http://u.720life.cn/g/edab4f07812b57c7ea69fa7b67a55e9e76c15af367ea0c9eb6d7abfe9ff83ec55c2abd42e819cc0aadbf094d4ad9044c)

**第五周**：[Django 学习小组：博客开发实战第五周——基于类的通用视图详解（一）](http://u.720life.cn/g/edab4f07812b57c7ea69fa7b67a55e9e5ad78644913c4524f1cdfb13e9db605ef019ee6093a91c6a03a99447774bb146)

**第六周**：[Django 学习小组：博客开发实战第六周教程 —— 实现评论功能](http://u.720life.cn/g/edab4f07812b57c7ea69fa7b67a55e9e1c4bcf17a47440da9124747356f1efad36a7948b96a74232661e0eaf52fdd7a0)

最佳实践一：[Django Blog 统计某个分类下有多少篇文章的优雅实现方法](http://u.720life.cn/g/edab4f07812b57c7ea69fa7b67a55e9e56b4dd01914e92e8f0937cb9ccb0ead93616d790c1147e96b5617ccf07b901a7)

最佳实践二：[Django Blog 文章按发表时间自动归档的优雅解决方案](http://u.720life.cn/g/edab4f07812b57c7ea69fa7b67a55e9ece2d301ba7430c530fbb37e23e617f2c0425eac78b27ca6b48fb350ab87be0ad)

### 项目运行方式
确保你的开发环境是 python3，如果不是，请考虑使用虚拟环境virtualenv搭建python3, 自行度娘并参照相关教程。

1. fork 本项目到你的仓库
2. 克隆你的仓库到本地
3. 命令行执行 pip install -r requirements.txt（注意在 requirements.txt 所在目录下执行，否则请输入完整路径名）安装依赖包
4. 迁移数据库，在 manage.py 所在目录执行

        python manage.py makemigrations
        python manage.py migrate

5. 类似步骤4，运行命令创建超级用户

        python manage.py createsuperuser

6. 类似步骤4、5，在 manage.py 所在目录执行

        python manage.py runserver

7. 浏览器输入 http://127.0.0.1:8000/

### 贡献人员名单：
JFluo2011，bdbai



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e088ceea085508a27a172b8812510f37695f030266ddc8b3230db5ff2e34ce47a382f2b0ea75eb5955665b3c0f4c87e35)