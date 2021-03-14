# 新型肺炎疫情数据爬虫+数据持久化+邮件通知



数据源来自“丁香园” ：https://3g.dxy.cn/newh5/view/pneumonia_peopleapp?from=timeline&isappinstalled=0

- 共三部分数据： 实时新闻 + 全局信息（全国 确诊 2055 例 疑似 2692 例 死亡 56 例 治愈 49 例） + 各省份疫情
- 数据库用MYSQL，建表语句在SQL目录下
- 功能：
  - jsoup获取数据，正则匹配筛选数据
  - 用mybatis+mysql做数据持久化
  - 数据发生变化时，发邮件通知

![疫情爬虫20200126175739](pic/疫情爬虫20200126175739.png)

![疫情爬虫_20200126191133](pic/疫情爬虫_20200126191133.png)


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e96f634ecfbc24a72fe629cb238ee5ef09e3dda31be94ec268f1a6c57cbfb01eb1058e4a3e20b008304567cc1897957b877a59eb9a734406cf9b71d86da11d451)