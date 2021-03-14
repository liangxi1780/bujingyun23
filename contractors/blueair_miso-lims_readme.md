[![Build Status](https://travis-ci.org/miso-lims/miso-lims.svg?branch=develop)](https://travis-ci.org/miso-lims/miso-lims) [![Quality Gate](https://sonarcloud.io/api/project_badges/measure?project=uk.ac.bbsrc.tgac.miso:miso&metric=alert_status)](https://sonarcloud.io/dashboard?id=uk.ac.bbsrc.tgac.miso:miso) [![DOI](https://zenodo.org/badge/4726428.svg)](https://zenodo.org/badge/latestdoi/4726428) [![Gitter](https://badges.gitter.im/miso-lims/community.svg)](https://gitter.im/miso-lims/community?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge) [![Documentation Status](https://readthedocs.org/projects/miso-lims-docs/badge/?version=latest)](https://miso-lims.readthedocs.io/projects/docs/en/latest/?badge=latest)



# MISO: An open source LIMS for small-to-large scale sequencing centres

&copy; 2019. [Ontario Institute for Cancer Research](http://u.720life.cn/g/d62d778741241df24a7e60df9b81583c57147a71d297c441c2a30ff8bfaff5d0), Toronto, Canada, [Earlham Institute](http://u.720life.cn/g/10861e346b7b5380afd395dc38eebf9e7fc2928d7b32d896bd1969c42f9ee38d), Norwich, UK.

> MISO project contacts: [Morgan Taschuk](morgan.taschuk@oicr.on.ca), [Robert Davey](robert.davey@earlham.ac.uk)
>
> MISO is free software: you can redistribute it and/or modify
> it under the terms of the GNU General Public License as published by
> the Free Software Foundation, either version 3 of the License, or
> (at your option) any later version.
>
> MISO is distributed in the hope that it will be useful,
> but WITHOUT ANY WARRANTY; without even the implied warranty of
> MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
> GNU General Public License for more details.
>
> You should have received a copy of the GNU General Public License
> along with MISO.  If not, see  .


## Trying MISO

### Docker

The simplest way to get MISO up and running quickly is to use
[Docker](http://u.720life.cn/g/d13d2b0ef4a5c92b4f4a6e9ed4270e65b90c4c1e1b506e1a501feef81ad769e9) compose. Images of the most recent MISO releases are
available on Docker Hub in
the [misolims](http://u.720life.cn/g/ce46a7789a867c84732a8edd85365bef051a1be63f8b79e0644a9a8be546fe2ede01c06aefe4bb65a46b50bdf0e4237e) organisation.

#### Prerequisites

Install required dependencies:

1. [Install Docker 18.06.0+](http://u.720life.cn/g/fe36d46bcf13791bdad89a5e154210d96d905095cc34802ef171f399860c0255)
1. If necessary, [install Docker Compose](http://u.720life.cn/g/fe36d46bcf13791bdad89a5e154210d97625994477674925a4fe69c4d6f0cf0938c347a7e21e893e9dc4462d2b62b982)


Download and extract the `.docker` directory from Github into `miso-lims-compose`.

```
wget https://github.com/miso-lims/miso-lims/archive/master.zip
unzip master.zip 'miso-lims-master/.docker/*'
mv miso-lims-master/.docker miso-lims-compose
rm -r master.zip miso-lims-master/
```

You are now ready to run MISO.

#### Quick Start

To bring up a demo environment, install the pre-requisites above and run the
following commands.

**Plain sample mode** has a straightforward Sample -> Library -> Library Aliquot ->
Pool workflow and is sufficient for basic laboratory tracking for sequencing.

Launch the plain sample demo with docker-compose:
``` bash
cd miso-lims-compose
export MISO_DB_USER=tgaclims && export MISO_DB=lims && export MISO_DB_PASSWORD_FILE=./.miso_db_password && export MISO_TAG=latest
echo "changeme" > ./.miso_db_password
docker-compose -f demo.plain.yml up
```

**Detailed sample mode** has all of the features of plain sample mode, plus it
allows users to build a hierarchy of Samples (e.g. Identity -> Tissue -> Slide
-> gDNA (stock) -> gDNA (aliquot) and also includes alias autogeneration.

Launch the detailed sample demo with docker-compose:

```bash
cd miso-lims-compose
export MISO_DB_USER=tgaclims && export MISO_DB=lims && export MISO_DB_PASSWORD_FILE=./.miso_db_password && export MISO_TAG=latest
echo "changeme" > ./.miso_db_password
docker-compose -f demo.detailed.yml up
```

For both environments, navigate to [http://localhost](http://u.720life.cn/g/e71094f6077cb9592da5b56893f0ad14)
and use the credentials **admin**/**admin**.

Once you are finished with the container, make sure to run
`docker-compose -f   down`, where ` ` is either
`demo.plain.yml` or `demo.detailed.yml`. This will clean up the instances and
networks and release their resources to the host operating system.


These compose files are intended as a demonstration and __not a permanent installation__.

Please see the [Docker Compose Guide](http://u.720life.cn/g/1e5e7e2e0fdf98c2590f2d3ba7d8ac5faedce8394e391edf72f5e4faeb89828f370e3a70bf13ed285085950fc589dfa7abb44bc4f9e66455bf8c354f0058b2b2d0c5c9c0fe486fded06e57c1562133263c1fca09a878d779b44810600f3b997d) for more information on configuring the containers and the compose files.


## User Tutorial

There are tutorials available to introduce and train new users to MISO's functionality.  
* [Plain sample tutorials](http://u.720life.cn/g/1e5e7e2e0fdf98c2590f2d3ba7d8ac5f1ea5f49fbd6cc8634a8c873d9877abeda54f027f1a975e21144318b8e6afba3afc690457c15b301347bc746a4e495461)
* [Detailed sample tutorials](http://u.720life.cn/g/1e5e7e2e0fdf98c2590f2d3ba7d8ac5f1ea5f49fbd6cc8634a8c873d9877abed0f1688a7cc7b5e336db2e106c7a6d1a5)

Some of the resources (MISO URL,
ways of contacting the MISO administrators) can be changed by forking and configuring
the [tutorial repository](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046c953127748e6acf3a12b3d8556ca2661c6a520beb0dabd26ea0f4c0e0fb657bc) to suit your
lab's specific needs.

## Running an Instance of MISO

To run your own MISO instance in the long term, download the
[latest release](http://u.720life.cn/g/54145d0471d91890860f7f8463c030465da52643141f23e748afa6b6f8337b78d3837a2d21cd62c3921c5a7a7f1888fbce7a893c83c9787c416efea736e876c8).

Installation and configuration details can be found in the [MISO building and deploying guide](http://u.720life.cn/g/1e5e7e2e0fdf98c2590f2d3ba7d8ac5faedce8394e391edf72f5e4faeb89828f370e3a70bf13ed285085950fc589dfa7d2db8f7d2c31a9aede6e940409902d5092b7fa892251102a177bb9b3b0bc038349efb712605a4bad2ec00be477f446ba).

## Contact and Community

- [MISO Twitter](http://u.720life.cn/g/5ea88169c4a0fbd169233d52478d54fec1e1d98b10afa1b945d72bd682e9e7ac) : for news and updates
- [MISO Community Gitter](http://u.720life.cn/g/11e95d0ed8d2826912e12fe1dc3f342195a9872383d20b795ada3fea24aa1c2f2d6fe1bf4e5fd3567ac73c5fa5967036) : for user group and developer questions and discussion
- [MISO Users Gitter](http://u.720life.cn/g/11e95d0ed8d2826912e12fe1dc3f3421739485365a12f6b7bd478ecc08bc08127b167097f0954cac7df36a42b84dc528) : for user group questions and discussion
- [MISO Developers Gitter](http://u.720life.cn/g/11e95d0ed8d2826912e12fe1dc3f3421ee8b7d38162f2e24f2fa728356d85fca23947bea98e560b59bb47c9be018dae1) : for developer questions and discussion



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6eac096fd0e748997018cce7a41dd2eb5baef52821db5511d7fdeb14278a93becf775ed444af65a87710132225e03641b5)