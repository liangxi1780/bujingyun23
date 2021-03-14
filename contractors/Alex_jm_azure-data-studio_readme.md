# Azure Data Studio

[![Join the chat at https://gitter.im/Microsoft/sqlopsstudio](https://badges.gitter.im/Microsoft/sqlopsstudio.svg)](https://gitter.im/Microsoft/sqlopsstudio?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)
[![Build Status](https://dev.azure.com/ms/azuredatastudio/_apis/build/status/Microsoft.azuredatastudio)](https://dev.azure.com/ms/azuredatastudio/_build/latest?definitionId=4)

Azure Data Studio is a data management tool that enables you to work with SQL Server, Azure SQL DB and SQL DW from Windows, macOS and Linux.

## **Download the latest Azure Data Studio release**

Platform | Link
-- | --
Windows User Installer | https://go.microsoft.com/fwlink/?linkid=2094100
Windows System Installer | https://go.microsoft.com/fwlink/?linkid=2094200
Windows ZIP | https://go.microsoft.com/fwlink/?linkid=2094201
macOS ZIP | https://go.microsoft.com/fwlink/?linkid=2094202
Linux TAR.GZ | https://go.microsoft.com/fwlink/?linkid=2094101
Linux RPM | https://go.microsoft.com/fwlink/?linkid=2094102
Linux DEB | https://go.microsoft.com/fwlink/?linkid=2094203

Go to our [download page](http://u.720life.cn/g/354fa3941ab85caffc78bddb8dff6c0396e3a09abf749d0f30d9fc29fca2eace) for more specific instructions.

## Try out the latest insiders build from `master`:
- [Windows User Installer - **Insiders build**](http://u.720life.cn/g/8143db808c55911b1c2b890c064a5600e3cf99d99dcb1bb9dec748d94d5167dfd950d52e40241aa9d232669b7e35cb46652e7837d39d1e89c602b1090336b9ad39d5fdab7b5c09d026d2e942ee60de33)
- [Windows System Installer - **Insiders build**](http://u.720life.cn/g/8143db808c55911b1c2b890c064a5600e3cf99d99dcb1bb9dec748d94d5167dfd950d52e40241aa9d232669b7e35cb46652e7837d39d1e89c602b1090336b9add4eafb44eb238ee86f6ef371e675b292)
- [Windows ZIP - **Insiders build**](http://u.720life.cn/g/8143db808c55911b1c2b890c064a5600e3cf99d99dcb1bb9dec748d94d5167dfd950d52e40241aa9d232669b7e35cb46652e7837d39d1e89c602b1090336b9ad53cc49c903c5db278bed2f4c14974f1ae93fedac5913ed8a5756a98fd566ee37)
- [macOS ZIP - **Insiders build**](http://u.720life.cn/g/8143db808c55911b1c2b890c064a5600e3cf99d99dcb1bb9dec748d94d5167dfd950d52e40241aa9d232669b7e35cb46246f4efce29cc3344658568352b16937061160a1f7f66751f33be495cf7988fe)
- [Linux TAR.GZ - **Insiders build**](http://u.720life.cn/g/8143db808c55911b1c2b890c064a5600e3cf99d99dcb1bb9dec748d94d5167dfd950d52e40241aa9d232669b7e35cb467f8410ce3875a6ed5cdd2ffe33f4b970d49bc64a36d6333ccf2e74b9f3d0e9ee)

See the [change log](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046ebcc3520f426d7b72895f550424cfdbda03ed34ae11d9932c8c28edb844ed49b30d5884f86fb8cbb1ab3c94af714e6e8c42ebb09001c28476a420c5add19f58b) for additional details of what's in this release.

## **Feature Highlights**

- Cross-Platform DB management for Windows, macOS and Linux with simple XCopy deployment
- SQL Server Connection Management with Connection Dialog, Server Groups, Azure Integration and Registered Servers
- Object Explorer supporting schema browsing and contextual command execution
- T-SQL Query Editor with advanced coding features such as autosuggestions, error diagnostics, tooltips, formatting and peek definition
- Query Results Viewer with advanced data grid supporting large result sets, export to JSON\CSV\Excel, query plan and charting
- Management Dashboard supporting customizable widgets with drill-through actionable insights
- Visual Data Editor that enables direct row insertion, update and deletion into tables
- Backup and Restore dialogs that enables advanced customization and remote filesystem browsing, configured tasks can be executed or scripted
- Task History window to view current task execution status, completion results with error messages and task T-SQL scripting
- Scripting support to generate CREATE, SELECT, ALTER and DROP statements for database objects
- Workspaces with full Git integration and Find In Files support to managing T-SQL script libraries
- Modern light-weight shell with theming, user settings, full-screen support, integrated terminal and numerous other features

Here are some of these features in action.

 

## Contributing
If you are interested in fixing issues and contributing directly to the code base,
please see the document [How to Contribute](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046ebcc3520f426d7b72895f550424cfdbd4477660f0d310b96e2dd5a785ff59e98661ca6734967b51404e6b19c6983b33eb7af5cd4ff737ea3db052a0ac00e1f37), which covers the following:

* [How to build and run from source](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046ebcc3520f426d7b72895f550424cfdbd4477660f0d310b96e2dd5a785ff59e98661ca6734967b51404e6b19c6983b33ea88c295007a4057449d9091e14e89c4cc892622ef72c80a1dfbee384a9e56435)
* [The development workflow, including debugging and running tests](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046ebcc3520f426d7b72895f550424cfdbd4477660f0d310b96e2dd5a785ff59e98661ca6734967b51404e6b19c6983b33e1ff6230848e75c17ceace07c63fc3215d214c71ef4b448522cade9c3158b2178)
* [Submitting pull requests](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046ebcc3520f426d7b72895f550424cfdbd4477660f0d310b96e2dd5a785ff59e98661ca6734967b51404e6b19c6983b33eef4a2536bbcfa6b24a01abc33b4db98107cd08a9966c38b4e2a674df51127546)

This project has adopted the [Microsoft Open Source Code of Conduct](http://u.720life.cn/g/22e7b067064505b0b066921a690bc00f40fc6818092ae136d535683f62b36971e7b295096e982152791c6cc0acadce74). For more information see the [Code of Conduct FAQ](http://u.720life.cn/g/22e7b067064505b0b066921a690bc00f40fc6818092ae136d535683f62b36971711354807af48475ed86c48f9fa10544f1669d39cb939aedffb8409517c51b11) or contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.

## Localization
Azure Data Studio localization is now open for community contributions. You can contribute to localization for both software and docs. https://aka.ms/SQLOpsStudioLoc

Localization is now opened for 10 languages: French, Italian, German, Spanish, Simplified Chinese, Traditional Chinese, Japanese, Korean, Russian, and Portuguese (Brazil). Help us make Azure Data Studio available in your language!

## Privacy Statement
The [Microsoft Enterprise and Developer Privacy Statement](http://u.720life.cn/g/904d0eda6c4951f2fe4847311f92d3edb1e99f042cf9413b83726917c68110b3f7fa07d65a4844f7a43d2626b248e946093264b97cbf24dbd490190371581ef8) describes the privacy statement of this software.

## Contributions and "Thank You"
We would like to thank all our users who raised issues, and in particular the following users who helped contribute fixes:

* Stevoni for `Corrected Keyboard Shortcut Execution Issue #5480`
* yamatoya for `fix the format #4899`
* GeoffYoung for `Fix sqlDropColumn description #4422`
* AlexFsmn for `Added context menu for DBs in explorer view to backup & restore db. #2277`
* sadedil for `Missing feature request: Save as XML #3729`
* gbritton1 for `Removed reference to object explorer #3463`
* Tarig0  for `Add Routine_Type to CreateStoredProc fixes #3257 (#3286)`
* oltruong  for `typo fix #3025'`
* Thomas-S-B for `Removed unnecessary IErrorDetectionStrategy #749`
* Thomas-S-B for `Simplified code #750`
* rdaniels6813  for `Add query plan theme support #3031`
* Ruturaj123 for `Fixed some typos and grammatical errors #3027`
* PromoFaux for `Use emoji shortcodes in CONTRIBUTING.md instead of � #3009`
* ckaczor for `Fix: DATETIMEOFFSET data types should be ISO formatted #714`
* hi-im-T0dd for `Fixed sync issue with my forked master so this commit is correct #2948`
* hi-im-T0dd for `Fixed when right clicking and selecting Manage-correct name displays #2794`
* philoushka  for `center the icon #2760`
* anthonypants for `Typo #2775`
* kstolte for `Fix Invalid Configuration in Launch.json #2789`
* kstolte for `Fixing a reference to SQL Ops Studio #2788`
* AlexFsmn `Feature: Ability to add connection name #2332`
* AlexFsmn `Disabled connection name input when connecting to a server. #2566`
* SebastianPfliegel `Added more saveAsCsv options #2099`
* ianychoi `Fixes a typo: Mimunum -> Minimum #1994`
* AlexFsmn `Fixed bug where proper file extension wasn't appended to the filename. #2151`
* AlexFsmn `Added functionality for adding any file to import wizard #2329`
* AlexFsmn `Fixed background issue when copying a chart to clipboard #2215`
* AlexFsmn `Fixed problem where vertical charts didn't display labels correctly. #2263`
* AlexFsmn `Fixed Initial values for charts to match visuals #2266`
* AlexFsmn `Renamed chart option labels #2264`
* AlexFsmn `Added feature for the opening file after exporting to CSV/XLS/JSON & query files #2216`
* AlexFsmm `Get Connection String should copy to clipboard #2175`
* lanceklinger `Fix for double-clicking column handle in results table #1504`
* westerncj for `Removed duplicate contribution from README.md (#753)`
* ntovas for `Fix for duplicate extensions shown in "Save File" dialog. (#779)`
* SebastianPfliegel for `Add cursor snippet (#475)`
* mikaoelitiana for the fix: `revert README and CONTRIBUTING after last VSCode merge (#574)`
* alextercete for `Reinstate menu item to install from VSIX (#682)`
* alextercete for `Fix "No extension gallery service configured" error (#427)`
* mwiedemeyer for `Fix #58: Default sort order for DB size widget (#111)`
* AlexTroshkin for `Show disconnect in context menu only when connectionProfile connected (#150)`
* AlexTroshkin for `Fix #138: Invalid syntax color highlighting (identity not highlighting) (#140))`
* stebet for `Fix #153: Fixing sql snippets that failed on a DB with a case-sensitive collation. (#152)`
* SebastianPfliegel `Remove sqlExtensionHelp (#312)`
* olljanat for `Implemented npm version check (#314)`
* Adam Machanic for helping with the `whoisactive` extension
* All community localization contributors:
  * French: Adrien Clerbois, ANAS BELABBES, Antoine Griffard, Arian Papillon, Eric Macarez, Eric Van Thorre, Jérémy LANDON, Matthias GROSPERRIN, Maxime COQUEREL, Olivier Guinart, thierry DEMAN-BARCELÒ, Thomas Potier
  * Italian: Aldo Donetti, Alessandro Alpi, Andrea Dottor, Bruni Luca, Gianluca Hotz, Luca Nardi, Luigi Bruno, Marco Dal Pino, Mirco Vanini, Pasquale Ceglie, Riccardo Cappello, Sergio Govoni, Stefano Demiliani
  * German: Anna Henke-Gunvaldson, Ben Weissman, David Ullmer, J.M. ., Kai Modo, Konstantin Staschill, Kostja Klein, Lennart Trunk, Markus Ehrenmüller-Jensen, Mascha Kroenlein, Matthias Knoll, Mourad Louha, Thomas Hütter, Wolfgang Straßer
  * Spanish: Alberto Poblacion, Andy Gonzalez, Carlos Mendible, Christian Araujo, Daniel D, Eickhel Mendoza, Ernesto Cardenas, Ivan Toledo Ivanovic, Fran Diaz, JESUS GIL, Jorge Serrano Pérez, José Saturnino Pimentel Juárez, Mauricio Hidalgo, Pablo Iglesias, Rikhardo Estrada Rdez, Thierry DEMAN, YOLANDA CUESTA ALTIERI
  * Japanese: Fujio Kojima, Kazushi KAMEGAWA, Masayoshi Yamada, Masayuki Ozawa, Seiji Momoto, Takashi Kanai, Takayoshi Tanaka, Yoshihisa Ozaki, 庄垣内治
  * Chinese (simplified): DAN YE, Joel Yang, Lynne Dong, Ryan（Yu） Zhang, Sheng Jiang, Wei Zhang, Zhiliang Xu
  * Chinese  (Traditional): Bruce Chen, Chiayi Yen, Kevin Yang,  Winnie Lin, 保哥 Will,  謝政廷
  * Korean: Do-Kyun Kim, Evelyn Kim, Helen Jung, Hong Jmee, jeongwoo choi, Jun Hyoung Lee, Jungsun Kim정선, Justin Yoo, Kavrith mucha, Kiwoong Youm, MinGyu Ju,  MVP_JUNO BEA, Sejun Kim, SOONMAN KWON, sung man ko, Yeongrak Choi, younggun kim, Youngjae Kim, 소영 이
  * Russian: Andrey Veselov, Anton Fontanov, Anton Savin, Elena Ostrovskaia, Igor Babichev, Maxim Zelensky, Rodion Fedechkin, Tasha T, Vladimir Zyryanov
  * Portuguese Brazil: Daniel de Sousa, Diogo Duarte, Douglas Correa, Douglas Eccker, José Emanuel Mendes, Marcelo Fernandes, Marcondes Alexandre, Roberto Fonseca, Rodrigo Crespi

And of course, we'd like to thank the authors of all upstream dependencies.  Please see a full list in the [ThirdPartyNotices.txt](http://u.720life.cn/g/bb9e19de933fd87f05600116164183c0b3ddd62d3854e3432c88c12f9e59c66261e4b9ac3c775c3b38111c98268c1cd73c5c24b9bcd3564150cf37c1253631ade6517d1f7eb3624d8c33ee79c8afe80a818a6caf8bcf2da4cefc959a50a5cf24)

## License

Copyright (c) Microsoft Corporation. All rights reserved.

Licensed under the [Source EULA](LICENSE.txt).



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e2bb5b6667df82b475d0e36ec2cdf1797db6465ea0cfdfa3595820925d08ebc5d7c54290751696834fa38a86b01417db7cb724e2d2f25b40b633472cdde7eaf30)