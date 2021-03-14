# cnode-electron
用electron 结合 react 以及[material-ui ](http://u.720life.cn/g/59cf9c0ec1896124aa6ae4dd453abb7f74273df73aeaee491933d9991d944c68d4ac188af44ce6be6283251a7096494ea4fe5e1408f852c17ed6ad0c8d6bfb76)   
根据node中文社区提供的api制作的node中文社区客户端 


![Alt text](https://github.com/wq123456/cnode-electron/blob/master/preview/1.png)
![Alt text](https://github.com/wq123456/cnode-electron/blob/master/preview/2.png)
![Alt text](https://github.com/wq123456/cnode-electron/blob/master/preview/3.png)
![Alt text](https://github.com/wq123456/cnode-electron/blob/master/preview/4.png)
![Alt text](https://github.com/wq123456/cnode-electron/blob/master/preview/5.png)
![Alt text](https://github.com/wq123456/cnode-electron/blob/master/preview/6.png)

[windows 64版本下载 ](http://u.720life.cn/g/a109a0615ed740cf52cdd9f7a4793a4123c981145765ed001eb85db01a3f0ab0) 
[mac 64版本下载 ](http://u.720life.cn/g/a109a0615ed740cf52cdd9f7a4793a41e93d083f25c32b0d48af438647199b77) 
使用方法: 
浏览器开发 
1 git clone https://github.com/wq123456/cnode-electron.git  
2 cd cnode-electron & npm install  
3 node server.js  
4 打开浏览器 http://127.0.0.1:3000 

electron 预览 

1 注释掉 app/store/configureStore.js 里面的 devtools()  
2 运行 npm run buildapp 重新构建app.js  
3 npm start 启动 electron  

发布:  

1 从node_modules/electron-prebuild/dist 中复制Electron.app到任意目录 
2 mac上显示包内容，找到Resources 文件，创建 app文件，然后把css ,index.html,sound,main.js,SYS_Channel.js,author.json,app.js复制到app文件中退出。（windows也有resources） 
3 双击Elecron.app 即可看到效果。然后可以自行更改文件名图标等  
ps: 官方的asar方法打包限制太多，不好使。 npm install 安装electron-prebuilt可能会失败，建议单独对其进行安装





 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6eaa40644741fd19e1586a59b821309e229ac4835ea1b56d1c99a0aa560893f07e3fe39c47b1b407118e9a36c97ba6da1f)