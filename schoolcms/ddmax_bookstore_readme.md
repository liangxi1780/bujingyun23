# mongoDB简单操作

### brew services start mongodb (mac brew 启动 mongodb)

### MongoDb 命令查询所有数据库列表
#### > show dbs

### 如果想查看当前连接在哪个数据库下面，可以直接输入db
#### > db

### 想切换到test数据库下面
#### > use test

### 想查看test下有哪些表或者叫collection，可以输入
#### > show collections

### 删除user表
#### > db.user.drop();



  1. 超级用户相关：

         #增加或修改用户密码

         db.addUser('admin','pwd')

         #查看用户列表

         db.system.users.find()

         #用户认证

         db.auth('admin','pwd')

         #删除用户

         db.removeUser('mongodb')

         #查看所有用户

         show users

         #查看所有数据库

         show dbs

         #查看所有的collection

         show collections

         #查看各collection的状态

         db.printCollectionStats()

         #查看主从复制状态

         db.printReplicationInfo()

         #修复数据库

         db.repairDatabase()

         #设置记录profiling，0=off 1=slow 2=all

         db.setProfilingLevel(1)

         #查看profiling

         show profile

         #拷贝数据库

         db.copyDatabase('mail_addr','mail_addr_tmp')

         #删除collection

         db.mail_addr.drop()

         #删除当前的数据库

         db.dropDatabase()

   2. 客户端连接

          /usr/local/mongodb/bin/mongo user_addr -u user -p 'pwd'

   3. 增删改

           #存储嵌套的对象

          db.foo.save({'name':'ysz','address':{'city':'beijing','post':100096},'phone':[138,139]})

          #存储数组对象

          db.user_addr.save({'Uid':'yushunzhi@sohu.com','Al':['test-1@sohu.com','test-2@sohu.com']})

          #根据query条件修改，如果不存在则插入，允许修改多条记录

          db.foo.update({'yy':5},{'$set':{'xx':2}},upsert=true,multi=true)

          #删除yy=5的记录

          db.foo.remove({'yy':5})

          #删除所有的记录

         db.foo.remove()

   4. 索引

          增加索引：1(ascending),-1(descending)

          db.things.ensureIndex({firstname: 1, lastname: 1}, {unique: true});

          #索引子对象

          db.user_addr.ensureIndex({'Al.Em': 1})

          #查看索引信息

          db.deliver_status.getIndexes()

          db.deliver_status.getIndexKeys()

          #根据索引名删除索引

          db.user_addr.dropIndex('Al.Em_1')

   5. 查询

          查找所有

          db.foo.find()

          #查找一条记录

          db.foo.findOne()

          #根据条件检索10条记录

          db.foo.find({'msg':'Hello 1'}).limit(10)

          #sort排序

          db.deliver_status.find({'From':'yushunzhi@sohu.com'}).sort({'Dt',-1})

          db.deliver_status.find().sort({'Ct':-1}).limit(1)

         #count操作

         db.user_addr.count()

         #distinct操作

         db.foo.distinct('msg')

         #>操作

         db.foo.find({"timestamp": {"$gte" : 2}})

         #子对象的查找

         db.foo.find({'address.city':'beijing'})

   6. 管理

          查看collection数据的大小

          db.deliver_status.dataSize()

          #查看colleciont状态

          db.deliver_status.stats()

          #查询所有索引的大小

          db.deliver_status.totalIndexSize()




#### 插入数据
##### db.books.insert({title:'The Murder House', genere:'Suspense', description:'No. 7 Ocean Drive is a gorgeous, multi-million-dollar beachfront estate in the Hamptons, where money and privilege know no bounds. But its beautiful gothic exterior hides a horrific past', author:'James Patterson', publisher:'Brown & Company', pages:'480', image_url:'http://ecx.images-amazon.com/images/I/51-6p1J%2BhVL._SX315_BO1,204,203,200_.jpg', buy_url:'http://www.amazon.com/Murder-House-James-Patterson/dp/0316410985'})


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6eac75b200f543eec07295e1e81ac6e5ef187be8107cfdcfa0eba58c1867ef3ec24f01a0ebde257ee4e6818506ae019777)