Amazon S3 Source and Sink
=========================

    [![Build Status](https://travis-ci.org/hydrator/amazon-s3-plugins.svg?branch=master)](https://travis-ci.org/hydrator/amazon-s3-plugins) [![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)      

Amazon S3 source and sink to read/write data from/to Amazon S3 store.

Build
-----
To build this plugin:

```
   mvn clean package
```

The build will create a .jar and .json file under the ``target`` directory.
These files can be used to deploy your plugins.

Deployment
----------
You can deploy your plugins using the CDAP CLI:

    > load artifact  .jar config-file  .json>

For example, if your artifact is named 'amazon-s3-plugins- ':

    > load artifact target/amazon-s3-plugins- .jar config-file target/amazon-s3-plugins- .json
    
## Mailing Lists

CDAP User Group and Development Discussions:

* `cdap-user@googlegroups.com  `

The *cdap-user* mailing list is primarily for users using the product to develop
applications or building plugins for appplications. You can expect questions from 
users, release announcements, and any other discussions that we think will be helpful 
to the users.


## License and Trademarks

Copyright © 2017 Cask Data, Inc.

Licensed under the Apache License, Version 2.0 (the "License"); you may not use this file except
in compliance with the License. You may obtain a copy of the License at

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software distributed under the 
License is distributed on an "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, 
either express or implied. See the License for the specific language governing permissions 
and limitations under the License.

Cask is a trademark of Cask Data, Inc. All rights reserved.

Apache, Apache HBase, and HBase are trademarks of The Apache Software Foundation. Used with
permission. No endorsement by The Apache Software Foundation is implied by the use of these marks.  



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ee160d6937b1960baf36022620f2b626a2b830d1a0d0304252fa69a2dc7219f6493cb2e809e8d9c58ae8b621b6addc13a333cffda1a51b1e214f9033ef5945317)