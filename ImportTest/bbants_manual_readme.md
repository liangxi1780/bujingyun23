# Enable the Lock Pages in Memory Option (Windows)

  This Windows policy determines which accounts can use a process to
keep data in physical memory, preventing the system from paging the data
 to virtual memory on disk.


Note Locking pages in memory may boost performance when paging memory to disk is expected.


 Use the Windows Group Policy tool (gpedit.msc) to enable this policy
for the account used by  SQL Server. You must be a system administrator
to change this policy.


To enable the lock pages in memory option
On the Start menu, click Run. In the Open box, type gpedit.msc.

On the Local Group Policy Editor console, expand Computer Configuration, and then expand Windows Settings.

Expand Security Settings, and then expand Local Policies.

Select the User Rights Assignment folder.

 The policies will be displayed in the details pane.

In the pane, double-click Lock pages in memory.

In the Local Security Setting – Lock pages in memory dialog box, click Add User or Group.

In the Select Users, Service Accounts, or Groups dialog box, add an account with privileges to run sqlservr.exe.

Log out and then log back in for this change to take effect.




 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e2f6c6a9e2645d44f53ae64846818d15647b6dbb9c86d939cd442bf84d603a505cf27542c83ad57e42c1496a3751c607f)