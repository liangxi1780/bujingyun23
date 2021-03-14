# Harbor

[![Build Status](https://travis-ci.org/goharbor/harbor.svg?branch=master)](https://travis-ci.org/goharbor/harbor)
[![Coverage Status](https://coveralls.io/repos/github/goharbor/harbor/badge.svg?branch=master)](https://coveralls.io/github/goharbor/harbor?branch=master)
[![Go Report Card](https://goreportcard.com/badge/github.com/goharbor/harbor)](https://goreportcard.com/report/github.com/goharbor/harbor)
[![CII Best Practices](https://bestpractices.coreinfrastructure.org/projects/2095/badge)](https://bestpractices.coreinfrastructure.org/projects/2095)
[![Codacy Badge](https://api.codacy.com/project/badge/Grade/c8d726c9cfd047ffaf681449d673f246)](https://www.codacy.com/app/goharbor/harbor?utm_source=github.com&amp;utm_medium=referral&amp;utm_content=goharbor/harbor&amp;utm_campaign=Badge_Grade)
[![Nightly Status](https://us-central1-eminent-nation-87317.cloudfunctions.net/harbor-nightly-result)](https://www.googleapis.com/storage/v1/b/harbor-nightly/o)

 

|![notification](docs/img/bell-outline-badged.svg)Community Meeting|
|------------------|
|The Harbor Project holds bi-weekly community calls, to join them and watch previous meeting notes and recordings, please see [meeting schedule](http://u.720life.cn/g/54145d0471d91890860f7f8463c030468c793e89df9d7697fdfca4a336f998d8e4be392b4449aca2e3d68b2e6146375e3fae89ba91640553a306872f9c2a51956bf5e70b2efe022d21e01edc7c7ffdcf 
 

**Note**: The `master` branch may be in an *unstable or even broken state* during development.
Please use [releases](http://u.720life.cn/g/54145d0471d91890860f7f8463c030467878602434b412b1453ad0bde2188c9fafad88542146f26c59e0c6076239fbb3)  instead of the `master` branch in order to get stable binaries.

 

Harbor is an an open source trusted cloud native registry project that stores, signs, and scans content. Harbor extends the open source Docker Distribution by adding the functionalities usually required by users such as security, identity and management. Having a registry closer to the build and run environment can improve the image transfer efficiency. Harbor supports replication of images between registries, and also offers advanced security features such as user management, access control and activity auditing.

Harbor is hosted by the [Cloud Native Computing Foundation](http://u.720life.cn/g/3eae61f755c4ef4eab2a2f59aab72e16)  (CNCF). If you are an organization that wants to help shape the evolution of cloud native technologies, consider joining the CNCF. For details about who's involved and how Harbor plays a role, read the CNCF
[announcement](http://u.720life.cn/g/ec73c9c498fc4df4b129c314c7c714069a8e0dd6ac30c9c1fde3096bdba58d1db45f943e9efd7743c24e8353c03fd4892b98f120146067efb8d95ed4f5d691c4cef6b737b68c59024ca917435048620f 

## Features

* **Cloud native registry**: With support for both container images and [Helm](http://u.720life.cn/g/5cab730003ff109750d13b01c27e55c5)  charts, Harbor serves as registry for cloud native environments like container runtimes and orchestration platforms.
* **Role based access control**: Users and repositories are organized via 'projects' and a user can have different permission for images under a project.
* **Policy based image replication**: Images can be replicated (synchronized) between multiple registry instances based on policies with multiple filters (repository, tag and label). Harbor will auto-retry to replicate if it encounters any errors. Great for load balancing, high availability, multi-datacenter, hybrid and multi-cloud scenarios.
* **Vulnerability Scanning**: Harbor scans images regularly and warns users of vulnerabilities.
* **LDAP/AD support**: Harbor integrates with existing enterprise LDAP/AD for user authentication and management, and supports importing LDAP groups into Harbor and assigning proper project roles to them.  
* **Image deletion & garbage collection**: Images can be deleted and their space can be recycled.
* **Notary**: Image authenticity can be ensured.
* **Graphical user portal**: User can easily browse, search repositories and manage projects.
* **Auditing**: All the operations to the repositories are tracked.
* **RESTful API**: RESTful APIs for most administrative operations, easy to integrate with external systems.
* **Easy deployment**: Provide both an online and offline installer.

## Install & Run

**System requirements:**

**On a Linux host:** docker 17.03.0-ce+ and docker-compose 1.10.0+ .

Download binaries of **[Harbor release ](http://u.720life.cn/g/54145d0471d91890860f7f8463c030467878602434b412b1453ad0bde2188c9f6562f31bd0c14758d06ce8463fbab615  and follow **[Installation & Configuration Guide](docs/installation_guide.md)** to install Harbor.

If you want to deploy Harbor on Kubernetes, please use the **[Harbor chart](http://u.720life.cn/g/54145d0471d91890860f7f8463c030461ae3d2f91a821a1e36e047b1ca29b7069de8793672013685c0c2b16e50d9ea59 

Refer to **[User Guide](docs/user_guide.md)** for more details on how to use Harbor.

## Community

* **Twitter:** [@project_harbor](http://u.720life.cn/g/5ea88169c4a0fbd169233d52478d54fede938f79b7180d411e34eb38fcffedc01b8c1baadd7542324e7b16ec813fbafc)   
* **User Group:** Join Harbor user email group: [harbor-users@lists.cncf.io](http://u.720life.cn/g/271b428ff5db6a02bf62b483482af8e4008f0ec4dff2e580fab7db628849506f473dd74cebdd86868ac1d5639736c3d9)  to get update of Harbor's news, features, releases, or to provide suggestion and feedback.  
* **Developer Group:** Join Harbor developer group: [harbor-dev@lists.cncf.io](http://u.720life.cn/g/271b428ff5db6a02bf62b483482af8e47985b38e90b2a5dcabb4679e0b94baa903d2a58d4f79a8c90817bcd744c1019e)  for discussion on Harbor development and contribution.
* **Slack:** Join Harbor's community for discussion and ask questions: [Cloud Native Computing Foundation](http://u.720life.cn/g/724b40f283df6dd96f6f65b6d8668cb5e28efe6e9b0ddebb2139cd1889c45a51  channel: [#harbor](http://u.720life.cn/g/cf2e57301f8f075daa1dee7029aa84ae4108642e315c50e85c4abbfe0eda04729aee678bed785c9b2826e97a63195911)  and [#harbor-dev](http://u.720life.cn/g/cf2e57301f8f075daa1dee7029aa84ae4108642e315c50e85c4abbfe0eda047274a6f01f7e325d6400498fa904fd7625b43e9a08af3e9b917c00c64c1e5d7098) 

## Additional Tools

Tools layered on top of Harbor and contributed by community.

* **[Harbor.Tagd](http://u.720life.cn/g/54145d0471d91890860f7f8463c030460fd14b5bfda2992c08912878f8cb171593e54dd381403ef0aa50361cea6befad 
  - Automates the process of cleaning up old tags from your Harbor container registries.
  - Lead by [@nlowe](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046fc8df178ebef55cdc3dd4df0e0c0b08a)  from HylandSoftware.

## Demos

* **[Live Demo](http://u.720life.cn/g/b38d9ca9a9c8d4fd6ce528e73dbcc45457827733c112ab889d0e2a51cd34d9a1  - A demo environment with the latest Harbor stable build installed. For additional information please refer to [this page](docs/demo_server.md).
* **[Video Demos](http://u.720life.cn/g/54145d0471d91890860f7f8463c030461ae3d2f91a821a1e36e047b1ca29b706ee36a33363506ae4a6244846bc5b61b52a4d04b0a32213cdedc281186966073aa4ac895ac941a74498a92b0f2b82b8b4  - Demos for Harbor features and continuously updated.

## Partners and Users

For a list of users, please refer to [ADOPTERS.md](ADOPTERS.md).

## License

Harbor is available under the [Apache 2 license](LICENSE).

This project uses open source components which have additional licensing terms.  The official docker images and licensing terms for these open source components can be found at the following locations:

* Photon OS 1.0: [docker image](http://u.720life.cn/g/ce46a7789a867c84732a8edd85365bef553220b1f143cb165490c40e162fda97d5527c043e683e1dd8be7ec4a916ebef  [license](http://u.720life.cn/g/54145d0471d91890860f7f8463c030467f8dad16cd7191355f7f99767dee550bdf0c37eddd9489725edb60106ccaedd92d6cd184920729e89b403ca7c2e04d0d) 



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)