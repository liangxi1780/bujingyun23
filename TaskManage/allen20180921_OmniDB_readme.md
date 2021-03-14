## Next Release: *2.12.0 - October 11, 2018*

# OmniDB 2.11.0

## Release Date: *August 23, 2018*

## Release Notes

- New features:
  - Support to PostgreSQL 11
    - Tables, functions and stored procedures can be managed in Console Tab and Tree View
    - Debugger can work with PostgreSQL 11 functions and procedures
- Improvements:
  - Server packages now install a service in systemd
  - SQL Template for calling functions and procedures (PostgreSQL)
  - Support for indexes for materialized views in the Tree View (PostgreSQL)
  - Support for rules for views in the Tree View (PostgreSQL)
  - Debugger version for FreeBSD (PostgreSQL)
  - Connection Grid now allows sorting by clicking in the column name
  - Improvements to Django security
- Bug fixes:
  - Fixed MESSAGES from a DO block / function / procedure not being shown if an EXCEPTION happens (PostgreSQL)
  - Fixed Alter Table GUI not handling NULL values (PostgreSQL)
  - Fixed column type names not being displayed correctly in Alter Table GUI (PostgreSQL)
  - Fixed DDL for GRANTs for schema (PostgreSQL)
  - Fixed SQL Template for REFRESH MATERIALIZED VIEW (PostgreSQL)
  - Fixed Postgres-XL tree not replacing node name
- Deprecation notice:
  - Debian 7 is not supported anymore, server packages are built on Debian 8

# 1- Installation

## 1.1- Installation packages

Just go to [omnidb.org](http://u.720life.cn/g/e886f85a155cbe146827520fd184d32136934da46550fdff0412b6aaf6cb70f4), download the appropriate file for your
operating system and architecture and install it.

## 1.2- From source

### 1.2.1- On Debian >= 9 with `pip`

```
sudo apt install python3-pip
pip3 install pip --upgrade
pip3 install -r requirements.txt
```

### 1.2.2- On Debian/Ubuntu using `PyEnv`

```
sudo apt install git make build-essential libssl-dev zlib1g-dev libbz2-dev libreadline-dev libsqlite3-dev wget curl llvm libncurses5-dev libncursesw5-dev xz-utils

git clone https://github.com/pyenv/pyenv.git ~/.pyenv
echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.bashrc
echo 'export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.bashrc
echo 'eval "$(pyenv init -)"' >> ~/.bashrc
source ~/.bashrc

pyenv install 3.5.2
cd OMNIDB_FOLDER
pyenv local 3.5.2

pip install pip --upgrade
pip install -r requirements.txt
```

## 1.3- Running OmniDB

Download or clone OmniDB repo and extract it somewhere. To start Django server, enter into `OmniDB/OmniDB` folder and type:

```
python omnidb-server.py
```

# 2- Introduction

**OmniDB** is a web tool that simplifies database management focusing on interactivity, designed to be powerful and lightweight. Check-out some characteristics:

- **Web Tool**: Accessible from any platform, using a browser as a medium
- **Responsive Interface**: All available functions in a single page
- **Unified Workspace**: Different technologies managed in a single workspace
- **Simplified Editing**: Easy to add and remove connections
- **Safety**: Multi-user support with encrypted personal information
- **Interactive Tables**: All functionalities use interactive tables, allowing copying and pasting in blocks
- **Smart SQL Editor**: Contextual SQL code completion
- **Beautiful SQL Editor**: You can choose between many available color themes
- **Tabbed SQL Editor**: Easily add, rename or delete editor tabs

![](https://omnidb.org/images/screenshots/screen00.png)

Technologies:

- Python (3.5+)
- Django

Supported Platforms:

- Linux
- Windows
- OS X

Supported DBMS:

- [X] PostgreSQL
- [X] Oracle
- [X] MySQL / MariaDB
- [ ] Firebird
- [ ] SQLite
- [ ] Microsoft SQL Server
- [ ] IBM DB2

# 3- Database Schema Management

OmniDB is designed for easy database management. Here are some features:

- Tree view showing database structure

![](https://omnidb.org/images/screenshots/treeview.png)

- Powerful table creation
  - Editing capabilities:
    - Tables' names
    - Columns: name, type and nullable
    - Primary keys and respective columns
    - Foreign keys with either table and reference columns, including updating rules and removal as well
    - Indexes

![](https://omnidb.org/images/screenshots/screen05.png)

- Table editing: Edit table structure according to DBMS limitations
- Data management: Add, edit and remove records

![](https://omnidb.org/images/screenshots/screen07.png)

- SQL Editing
  - Syntax highlighting for SQL
  - SQL code completion for table columns and subquery
  - Multiple themes to be selected

![](https://omnidb.org/images/screenshots/screen06.png)

- Support for external tools:
  - [pglogical](http://u.720life.cn/g/6c5869e7e7856a72e7285db2bea9e143b82d85e12c39b93e627011e266c9cee122eaab8ae8db00a04cf57d8236a60e6f76f270e2d357ff0403bb5e27345c1fb4)
  - [Postgres-BDR](http://u.720life.cn/g/6c5869e7e7856a72e7285db2bea9e143b82d85e12c39b93e627011e266c9cee156880543c0e31d3ab41ab0e854c3ba5b)
  - [Postgres-XL](http://u.720life.cn/g/6c5869e7e7856a72e7285db2bea9e143b82d85e12c39b93e627011e266c9cee11adfc2fe50ec6a92dd0e89b16bcb5d0de93a32f57abfdaebb390df669f3185ba)


- Other features:
  - Querying organized in tables
  - DDL commands execution
  - SQL history
  - Graphs displaying tables and their relations

![](https://omnidb.org/images/screenshots/screen02.png)

  - Graphs displaying complete ER diagram

![](https://omnidb.org/images/screenshots/screen01.png)

  - Visualization of explain plan

![](https://omnidb.org/images/screenshots/execution_plan.png)

  - PL/pgSQL function debugger (requires a plugin, please see [here](http://u.720life.cn/g/54145d0471d91890860f7f8463c030462698f89fae850ce37de263292eb67cb2be86887cd45b57b5f03cb82f8ecdb14af475f65bd6b818884597089092e5fae2dee12eb0f563bcf19efc87c32c557e7d)

![](https://omnidb.org/images/screenshots/debugger.png)

  - Monitoring dashboard

![](https://omnidb.org/images/screenshots/monitoring_dashboard.png)



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ee708ba52e9e10d3e1e27d962607b7c447f4cfc6b11075b4ae35eedd21c861b0313d8542a64bac6e88cbb720ae7ce2474)