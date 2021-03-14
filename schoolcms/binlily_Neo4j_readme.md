Welcome to the Neo4j wiki!
## 初衷
这是一个知识图谱构建工具,最开始是对产品和领导为了做ppt临时要求配合做图谱展示的不厌其烦,做着做着就抽出一个目前看着还算通用的小工具
## 技术栈
小工具是前台是基于vue + d3.js ,后台是springboot配合Neo4j.
## 演示
demo地址：[http://kg.miaoleyan.com/](http://u.720life.cn/g/5f7f8913e29b344862bae032fad946c70809a253890ece570855817233836028).

实现的基本功能:
1. 新增节点,添加连线,快速添加节点和关系
2. 节点的颜色和大小可修改
3. 节点和关系的编辑,删除
4. 导出成图片
5. csv导入
6. 导出csv
7. 添加图片和富文本
8. 节点之间多个关系


![知识图谱构建小工具](http://file.miaoleyan.com/kg1.gif)
![知识图谱构建小工具](http://file.miaoleyan.com/kg2.gif)
![知识图谱构建小工具](http://file.miaoleyan.com/kg3.gif)
![知识图谱构建小工具](http://file.miaoleyan.com/kg4.gif)
![知识图谱构建小工具](http://file.miaoleyan.com/m99.gif)
![知识图谱构建小工具](http://file.miaoleyan.com/kg52.gif)
![知识图谱构建小工具](http://file.miaoleyan.com/kg51.gif)
![知识图谱构建小工具](http://file.miaoleyan.com/kg33.png)
![知识图谱构建小工具](http://file.miaoleyan.com/nndt/pgMA43Y9y4TOXz1hKQ2YVcVuzb75awGs)
![知识图谱构建小工具](http://file.miaoleyan.com/nndt/knrN8VAaptk4VZ4Uc3vPALqiMqPwhwEu)
## 后续优化:
1. ~~新建单节点,节点的位置能指定(或者和鼠标点下的位置一致) over 2018-11-16~~
2. ~~做出的图谱能够导出成图片 over 2018-11-16~~
3. ~~支持导入功能,同时支持导出关系和节点 over 2018-11-17~~
4. 输入一段文本,通过自然语言等手段,抽出实体和关系,编辑后可形成可视化的图谱
5. 按钮组不能随节点半径的变化而变化
6. ~~节点间多关系线和文字重叠~~
## 运行与启动
1. 需要jdk1.8,安装Neo4j,安装和配置自行百度
2. 启动后访问[http://localhost/kg/index](http://u.720life.cn/g/e71094f6077cb9592da5b56893f0ad14d739a217b33f95f5b750a9fadfa83a38) 即可
3. 新版[http://localhost](http://u.720life.cn/g/e71094f6077cb9592da5b56893f0ad14)
4. 供前端小哥哥小姐姐参考的静态网页：打开文件夹，找到 /kgmaker/src/main/resources/templates/kg/demoforfont-end.html
## 交流
### 希望感兴趣的小伙伴能一起做些事情
![](http://file.miaoleyan.com/nndt/8UQmv0M1CWLxFx45YSuUElouufhePenr)



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ef8a9dca83edba14b88009b5f12d298eaa78d5b204e75b2236a321ca84f1431ba9e301e231a432e6fcd5daadbc87bed78)