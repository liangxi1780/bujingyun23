医院、飞机、火车、公交、出租车、小区、电梯等公共场所的消毒管理登记。分消毒员使用的登记端，和监管员使用的管理端。

本项目为登记端。管理端另见：[https://gitee.com/dcloud/xinguan2020-xiaodu-guanli](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6edcd563202d5e7f96eb038e15873ea50a4de9264ca4a69c135b71c57f8320e06eb6dd8ee24483893a84f04dc1fbc924de)

项目负责人：温州威客网络科技有限公司 林举
讨论群：1037708061

## 登记端需求说明

### 功能
- 上报信息： 消毒位置 消毒成果照片 上报时间
- 查看自己的登记历史
- 登陆、注销、修改密码

### 界面
tab: 登记信息、我的。
软件必须登录才能使用。
#### 登记信息
登记信息界面为列表界面，右下角悬浮一个+号

列表为操作员的历史登记信息列表，主标题：消毒位置，副标题：上报时间

点击列表看详情：除了文字显示 消毒位置、上报时间外，还显示消毒成果照片、以地图方式显示上报位置（可能在电梯里位置不准，不求太精准）

+号点击后打开新界面，内容为表单填写，包括：消毒位置（可输入可选择的combox）、拍照消毒成功照片（app可不支持从相册选择）、上报时间和位置不需要登记人员填写，系统自动采集。
如果保存时没有网络，比如在电梯里，需要暂存并持续重试。

#### 我的
常规的登录、登出、修改密码
暂不需要注册，软件必须登录才能使用




 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)