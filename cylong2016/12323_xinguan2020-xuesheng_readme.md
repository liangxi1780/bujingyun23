这是学生健康报备系统的需求文档，适用于广大中小学生的学生属地摸查、每日健康统计。

为快速上线，本项目分阶段进行：

- 一期：满足单个中小学校上线发布，包含高中、初中、小学、幼儿园，这应该是一个类别的，相对简单，支持设置学校名称、班级管理、班级管理员
- 二期：满足单个大学上线发布，区分学院、系所，可能还要涉及分校，研究生、博士等分类
- 三期：满足区域性多校上线发布，比如：北京市中小学校健康统计


## 需求汇总

一期满足单个中小学校上线发布，涉及功能包括：
- 注册登录
- 班级管理
- 健康上报
- 数据查看

## 首页

负责人：

首页显示“xx学校学生健康报备系统”，区分登录状态，未登录时，显示登录、注册按钮。

若已登录，区分角色，首页显示不同内容。

学生/家长，首页显示两个链接：
- 修改学生信息
- 今日健康报备

老师，首页显示两个链接：
- 修改个人信息
- 查看报备数据

### 登录注册

负责人：邯郸-前端-秦少卫

用户类型：
- 管理员，一期可通过数据库内置用户名、密码的方式，出厂内置
- 老师
- 学生
- 学生家长

登录/注册类型：
- 用户名/密码：全平台都支持
- 微信登录：微信小程序支持，且微信小程序优先微信登录

账号和班级、学生是分开的，注册成功后流程：

- 超级管理员无需注册，系统出厂内置；
- 老师注册后，跳转绑定班级信息，后续可修改
- 学生/家长注册后，跳转绑定学生信息，包括：年级、班级、学号、姓名等

登录成功后，判断当前账号状态，如下：
- 超级管理员：跳转年级、班级管理界面
- 老师：若未绑定班级信息，跳转绑定班级信息页面，否则跳转班级当日健康统计列表页面
- 学生/家长：若未绑定学生信息，跳转绑定学生信息页面，否则跳转当日健康报备页面


### 管理员管理班级信息

负责人：江西-前端-Ran

超级管理员可管理学校的年级、班级，超级管理员账号、密码可通过内置数据库的方式临时处理：

- 年级：新增、修改、删除，删除年级时，提醒会将该年级下关联的所有班级全部删除
- 班级：新增、修改、删除，删除班级时，提醒会将该班级下所有学生及已有的健康报备数据全部删除

班级需设置该班级总共有多少学生。

### 学生/家长 上报健康状况

负责人：[安徽-unicloud-王秀龙](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ee27ae92de6f03d2b927066af1c166882)

统计每个学生每日的健康情况，统计项如下：

- 统计日期，系统生成
- 班级，系统获取
- 学生姓名，系统获取
- 当前健康状况：多选，可选项：良好/咳嗽/乏力/发热，多选时逗号分隔；选良好后，不能再选其他项
- 有无接触`湖北/武汉`人员
- 有无疑似症状
- 当前所在省市
- 今日体温，可选

每天仅可报备一次，若多次报备，则覆盖上次信息。

### 老师查看报备情况

负责人：南笙

统计列表，默认为当天日期，开头显式显示已上报xx人，缺xx人，列表按学号排列 

老师可切换日期，查看之前的历史数据。

 

## 数据库设计

参考 [db.md](db.md)


每日健康统计理论上需家长每日配合提交。


### 空间与小程序appID设置
- 在`main.js`中设置空间的`spaceId`、`clientSecret`；
- 在`manifest.json`中设置微信小程序的`appID`，否则微信端获取的code为：`the code is a mock one`；
- 在`cloudfunctions-dev/src/utils/constants.js`中设置`AppId`、`AppSecret`、`passSecret`字段，否则不能获取`openid`;


### token获取详情
获取用户信息需要根据token获取，方法如下，成功后，`res.data`为详细信息，`res.data.userType`为用户类型，
`userType`的值为数字，对应信息如下。
- 0：老师
- 1：学生
- 2：家长
- 3：管理员

```JS
validateToken() {
				uni.showLoading({
					title: '加载中...'
				});
				uniCloud.callFunction({
					name: 'validateToken',
					data: {
						token: uni.getStorageSync('token')
					}
				}).then((res) => {
					uni.hideLoading()
					uni.showModal({
						content: res.result.msg,
						showCancel: false
					})
				}).catch((err) => {
					uni.hideLoading()
					uni.showModal({
						content: '请求云函数发生错误，' + err.message,
						showCancel: false
					})
				})
			},
```



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e70886450e0f22cb62ce319509cb3dfee38312e193fecd50688a19d942a059506a61fe1a0bf8abad2e0c52fdda5f1ac70888f3ef1685f2cdffa69096f75c84585)