图书管理系统
===============

总体设计
-------------
本程序前后端分离，用户界面部分与数据管理部分没有耦合，因此可以方便地更换为各种不同类型的前端界面。数据管理部分首先基于面向对象思想进行抽象，用reader和book类分别存储图书馆会员和书籍的信息。并对其进行封装，生成简洁易用的过程式接口——静态空间bookManage和statistics供给前端界面调用。其中，bookManage中含有保存所有reader和book对象的两个vector。在这个顶层设计的基础上，我们根据实际功能需求进一步细化数据结构：
### 借阅管理部分
* 图书的分类管理
为了实现这个功能，book类引入表示图书类型的成员。该成员的作用主要是在显示所有图书时——对外接口statistics::display函数有参数type，使得上层可以选择要预览的图书种类。如果不传该参数，则默认输出所有图书信息。
* 借还书操作及记录
首先考虑记录的问题，借书记录中包含借书用户、借的书、借书日期以及应还日期等信息。因此使用一个交集类型borrowStru来表示。续借、计算罚款等操作就可以作为这个类的成员。然后就要考虑该类型与其它类型之间的关联，通过分析需求可以知道，借书操作更多地与借书者相关（如需要在超期还书后输出该借书者目前超期的所有书等），因此为了直接从借书者访问其借书记录，给reader类添加一个vector 成员来存储其所有借书记录。并在reader类中添加增删borrowStru对象的借还书成员函数。
### 读者管理部分
* 读者等级
根据需求，读者需要有一个“读者等级”属性用来记录读者的身份、最多同时借书本书以及单次借书时间，因此显然“读者等级”也应该用一个交集类型表示，在这里我们创建了readerType类用来表示。并给reader类添加一个readerType类型的成员变量用来表示其类型。readerType中记录的信息在borrowStru和reader的借书函数中被使用——borrowStru的续借成员函数中，通过读取readerType的time成员得到借书月数；reader的借书函数中比较当前用户借书数量与readerType中规定的最多借书数量判定用户是否能继续借书。
* 增删查改操作
对于读者的录入、挂失、注销和查询，均在reader类或bookManage中提供了单个函数。直接调用即可完成该工作。
### 统计分析部分
排序的功能提供在静态空间statistics中，支持用户持书数量、用户借书数量、图书借阅量、超期未还数量四个维度的排序统计。排序采用标准库提供的sort函数直接对reader和book的vector进行排序实现。我们建立了四个排序比较函数（作为statistics的私有成员）直接传递给sort作为参数，以实现四种不同的排序。
### 系统参数设置
超期还书罚款和最多续借次数均为borrowStru的私有const成员，直接修改即可对系统进行个性化配置。

### 系统架构图
![架构图](架构图.png)

详细设计
----------------
### date类
#### 数据成员：
``` cpp
int year;
int month;
int day;
```

#### 成员函数：
``` cpp
Date(int year, int month, int day)
主构造函数

void reSet(int year, int month, int day)
重设本对象的年月日

string toString()
将日期转换为“-年-月-日”的字符串

void nextMonth()
将本对象的移到下个月（跨年会自动进位）

void nextDay()
将本对象移到下一天（跨月自动调用nextMonth）

bool isBigger(Date &d)
与另一个Date对象进行大小比较，如果本对象比d大返回true，否则false

int dvalue(Date &d)
计算本对象与d所差的天数（默认d大）
```

### readerType类
#### 数据成员：
``` cpp
string name;
类别名
int time; 
默认借书时间，按月计算
int num; 
可借书数量
```

#### 成员函数：
``` cpp
readerType(string name, int time, int num)
主构造函数
```

### reader类
#### 数据成员：
``` cpp
int no;
读者编号
string name;
string c;
读者班级
readerType type;
读者类型（级别）
bool isLose = false;
是否已挂失
int total = 0;
借书总数
vector allBorrow;
该vector存储当前（未还的）所有借书记录
```

#### 成员函数：
``` cpp
void display(Date d)
输出本对象信息。参数为系统当前时间，用于计算该读者的超期还书数量（对于目前持有的图书）。

bool isBorrow(book* b)
判定本对象目前是否正在借用这本书

bool borrow(book* b, Date d)
本对象借书，如果借书成功返回true，否则返回false（失败原因如用户已挂失、当前借书数过多、已经借过这本书等）。参数为要借用的图书和借书时间（一般是当前系统时间）。该函数内部会创建borrowStru对象。

bool ret(book* b, Date d);
本对象还书，如果还书成功返回true，否则返回false（失败原因如用户已挂失、并没有借过这本书等）。参数为要借用的图书和还书时间（一般是当前系统时间）。该函数内部会删除对应的borrowStru对象。

bool con(book* b)
续借图书，如果续借成功返回true。该函数内部调用本对象对图书b的borrowStru对象的con成员函数。

void displayAllDebt(Date d)
输出本对象的所有超期未还图书（书名），如果本读者没有任何超期未还图书，那么什么也不会输出。参数为检查的时间（一般是当前系统时间）。该函数内部通过调用所有借书记录的isPublish成员函数进行统计。
```

### book类
#### 数据成员：
``` cpp
int no;
图书编号（使用bookManage::addBook构造成员时自动确定）
string name;
书名
string author;
作者
string press;
出版社
Date d;
出版日期
int money;
金额
string type;
图书类型
int stock;
库存量
int surNum = 0;
剩余量
int publishNum = 0;
超期未还的数量，需要调用statistics::caluDebt进行全局统计
```

#### 成员函数：
``` cpp
book(string name, string author, string press, Date d, int money, string type, int stock)
主构造函数

void display()
输出本对象信息
```

### borrowStru类
#### 数据成员：
``` cpp
book* b;
所借图书
reader* p;
借书者
Date d1;
借书日期
Date d2;
应还日期
int nowTimes = 0;
当前续借次数
```

#### 成员函数：
``` cpp
borrowStru(book* b, reader *p, Date d1)
主构造函数

bool con()
（本对象）续借，如果续借成功返回true，否则返回false（失败原因如已达到系统设置的最大续借次数）。该函数会改变d2（根据读者等级中的默认借书时间调用一定次数d2的nextMonth）

bool isPublish(Date d)
计算是否超期还书（通过将d与d2通过date类的isBigger函数进行比较）。参数为还书日期（一般是当前系统时间）

int calu(Date d)
计算超期还书罚款，通过date类的dvalue函数计算d与d2的所差天数，并乘以系统设置的每天罚款。参数为还书日期（一般是当前系统时间）
```

### 静态空间bookManage
#### 数据成员：
``` cpp
static vector bookList;
所有书籍
static vector readerList;
所有读者
static Date today;
系统当前日期
```

#### 成员函数：
``` cpp
static book* findBook(string name)
通过书名查找该书的对象指针

static void removeBook(string name)
通过书名在bookList中删除该书

static void addBook(string name, string author, string press, Date d, int money, string type, int number)
向bookList添加新的图书（会自动构造对象并确定编号）

static void addreader(int no, string name, string c, readerType type)
向readerList添加新的读者（会自动构造对象）

static reader* findreader(string name)
通过读者姓名查找该读者的对象指针

static void removereader(string name)
通过读者姓名在readerList中删除该读者
```

### 静态空间statistics
#### 成员函数：
``` cpp
static void readerRank1()
用户目前持书数量排行。通过将比较函数（比较两个reader对象中的allBorrow.size）传递给标准库排序函数sort实现对readerList进行排序，并按顺序输出读者姓名和他的allBorrow.size。

static void readerRank2()
用户借书总数排行。通过将比较函数（比较两个reader对象中的total）传递给标准库排序函数sort实现对readerList进行排序，并按顺序输出读者姓名和他的total。

static void bookRank1()
当前图书借阅量排行。通过将比较函数（比较两个book对象中的stock-surNuM）传递给标准库排序函数sort实现对bookList进行排序，并按顺序输出书名和他的stock-surNuM。

static void caluDebt()
计算所有图书的当前超期未还数量（计算到每个book对象的publishNum成员）

static void bookRank2()
超期未还图书排行。先调用caluDebt计算每个对象的publishNum。再通过将比较函数（比较两个book对象中的publishNum）传递给标准库排序函数sort实现对bookList进行排序，并按顺序输出书名和他的publishNum。

static void bookRank3()
图书借阅总量排行。通过将比较函数（比较两个book对象中的total）传递给标准库排序函数sort实现对bookList进行排序，并按顺序输出书名和他的total。

static void display(string type = "")
显示图书信息。参数为要显示的图书种类，如果为默认即显示所有图书信息。
```

单元测试
-------------
参见`test.hpp`


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e251d75bea57d4d79d724c752be1ff169e3c4a43024c2a61b7cd055b7129fac0c9700f83bb8a4581f8d51870d4146e872e6fe7a231e79bc5afcfc28fc34d20f65e3fba36df4c881bd7bea44e47e64f154)