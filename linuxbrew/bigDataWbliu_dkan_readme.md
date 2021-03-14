# DKAN Open Data Portal

[![DKAN Sitewide Build Status](https://circleci.com/gh/NuCivic/dkan.svg?style=svg)](https://circleci.com/gh/NuCivic/dkan)

[![Join the chat at https://gitter.im/NuCivic/dkan](https://badges.gitter.im/NuCivic/dkan.svg)](https://gitter.im/NuCivic/dkan?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

DKAN is a Drupal-based open data tool with a full suite of cataloging, publishing and visualization features that allows governments, nonprofits and universities to easily publish data to the public. It is inspired by the [CKAN project](http://u.720life.cn/g/54145d0471d91890860f7f8463c030469b56a6ef429559c191dc550c7218d04a) and maintained by [Granicus Data](http://u.720life.cn/g/d713e877fd67331805f94d7bd8107db6b815ae34c58c2243fe8d9339dcf10a0b).

[![DKAN](docs/images/dkan-front-page.png)](http://getdkan.com)

*  [ Live demo » ](http://u.720life.cn/g/8b29d4fa2c55b85eb78e49956039497dc6b54df59e09b7c3325cf5ef7d06f7db)
*  [ Full Documetation » ](http://u.720life.cn/g/d971e5728b372e907b89d3258452a41e66ec7feaca98a52097028bbdbb165390)
*  [ Open data portals using DKAN » ](http://u.720life.cn/g/54145d0471d91890860f7f8463c030467d7de3bf2709c2b7d4b4687cd6177486b8b0373be24f7a6b548d669c0e30c0a8)

## Features

### For data publishers

*   Publish data through a guided process or import via API/harvesting from other catalogs
*   Customize your own metadata fields, themes and branding
*   Store data within DKAN or on external (e.g. departmental) sites
*   Manage access control, version history with rollback, RDF support, user analytics
*   Supported enterprise-quality commercial support and FISMA-certified cloud hosting options available

### For data users

*   Explore, search, add, describe, tag, group datasets via web front-end or API
*   Collaborate with user profiles, groups, dashboard, social network integration, comments
*   Use metadata and data APIs, data previews and visualizations
*   Manage access control, version history with rollback, INSPIRE/RDF support, user analytics
*   Extend and leverage the full universe of more than 18,000 freely available Drupal modules

## Hosting and support

Granicus [Data](http://u.720life.cn/g/d713e877fd67331805f94d7bd8107db6bbd048a24c45ac3d7bf68208c01af481) platform offers 24/7, secure, cloud-based DKAN hosting and support services.

## Installation

Please see the ["Installation" section of the DKAN Documentation](http://u.720life.cn/g/d971e5728b372e907b89d3258452a41e6a8656ad1544c84d192f96bf0e9cc62af506eef3b56e1d448726d5fe286707251d107b5d635ba577b4c72e6a52dc4780).

### Upgrading DKAN

Please see the ["Updating and Maintaining DKAN" section of the DKAN Documentation](http://u.720life.cn/g/d971e5728b372e907b89d3258452a41e6a8656ad1544c84d192f96bf0e9cc62ab3a6a7afe23f40a5c6a9c0f1bcbd627ace7ea66a88a7864832c37b8f1cb8e996) for general upgrade information.

## Releases

Check the [releases page](http://u.720life.cn/g/54145d0471d91890860f7f8463c030461055a1aa7687c38435111feee303401114c1d0b4797ca96cf1fea0442ce0f294) for latest DKAN Version. 7.x-1.x is the development branch.

Contact us if you want to get involved!

DKAN development is a sponsored by NuCivic. For more information about hosting and professional support options for DKAN, see http://getdkan.com/contact

### Releases and Release Candidates

DKAN follows a modified semantic versioning convention, and has _major_, _point_ (also known as _minor_), and _patch_ releases.

The only _major_ release of DKAN has been 7.x-1.0. It is unlikely there will be a 7.x-2.x version of DKAN but in the case of a major architecture change, this is possible. More likely is a 8.x-2.x release if and when DKAN is ported to Drupal 8. At the moment there is no work being done on a Drupal 8 version.

_Point_ releases occur approximately every 1-2 months and include new functionality and architectural changes. For instance, DKAN 7.x-1.1 was the first point release, and 7.x-1.2 was the second. While we try to make updating as seamless as possible, _point release_ updates often involve some work, especially if the website uses a custom theme or modules outside of what is included in the distro.

_Patch_ releases, introduced after the release of DKAN 7.x-1.12, occur much more frequently, and include bug fixes, core and contrib module updates, and minor enhancements. The first patch release was version 7.x-1.12.1, the second was 7.x-1.12.2, and so on. Updating to a new _patch_ release should be very straightforward and cause little to no distruption to a website.

### Tags and branches

After a _point_ release comes out, we create a _release branch_, on which we do any work intended for future _patch_ releases on that version of DKAN. The _release branch_ for version 7.x-1.12 development, for instance, is `release-1-12`. New features and other work destined for the next _point release_ continues on the main development branch, `7.x-1.x`.

We keep the DKAN profile (this project), [DKAN Dataset](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046c1470989727f3d09ae5b798138bcd3cf67eb4d52cc41ec4b65b6e8c5d35e59a6), [DKAN Datastore](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046c1470989727f3d09ae5b798138bcd3cf4c1ea3836368c148093e74189e430b82), [DKAN Workflow](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046c1470989727f3d09ae5b798138bcd3cf5fcdeca037d80ebd5139dc0a7edc8ee4) and [Recline](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046352e99bdfd2bd51c8a62bf4f3d162f638c7562174b2a4edd34ec6e2ce1d0b56f) versioning in sync. Other depdendencies that we maintain, incuding [Open Data Schema Map](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046a05ae1619b9c7c090ad8ffa9803b1946a529e5bfa93966530cb07831965d4c27) and [Visualization Entity](https://github.com/NuCivic/visualization_entity) follow their own, separate release cycle.

## Getting Help with DKAN

Have a question, found a bug, or need help with DKAN? Check our [documentation](http://u.720life.cn/g/d971e5728b372e907b89d3258452a41eef05085e1b1b87e9c32523c0539383be) first. In addition:

### General questions as a developer or site builder

Please post a question on our [Developer list](http://u.720life.cn/g/941693b557d072bb769494a6a61fcd979ee9fee4d4fd0c2a6b8a30bc68eade210099b30cf054306f89436706b1e2f8ad39d62c90969a78664a3e658dc9632458).

### Bugs and issues

Please post it to our [Github issue queue](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046119840351a9f9fb8d74964da198cee92242c33398735188178514039ab98f9b8).

### I would like to purchase Granicus support or hosting

[Please contact us for a consultation](http://u.720life.cn/g/29ddf9fdc2d2dd163784799ccc1ef143980f44f2dbb2c812313a296d66327c79).

## Community

While the GovDelivery Open Data team leads the DKAN project, there is a worldwide community behind it contributing ideas and code. You are welcome to join the discussion:

* [The DKAN Developers mailing list](http://u.720life.cn/g/941693b557d072bb769494a6a61fcd979ee9fee4d4fd0c2a6b8a30bc68eade210099b30cf054306f89436706b1e2f8ad39d62c90969a78664a3e658dc9632458)
* [Our Gitter channel](http://u.720life.cn/g/11e95d0ed8d2826912e12fe1dc3f34215b85c69305b19af954152bd1b2ab92f1)

## Contributing

Please file all tickets for DKAN [in this issue queue](http://u.720life.cn/g/54145d0471d91890860f7f8463c030461055a1aa7687c38435111feee30340115247ab05e88dcfadc57064a7a9d30869). We have several labels in place for you to tag the issue with and identify it with the proper component.

Please follow the [Ticket Template](http://u.720life.cn/g/54145d0471d91890860f7f8463c030461055a1aa7687c38435111feee3034011411998ca6e1940d3901099de27ff0bb909f1e0cf6b76f9f75fd3967d086387a40408c176d8397f4e78b10104172dc435b004d5cc0f543397362373a6ba63a442) when creating new tickets.

Also, please remember to reference the issue across repositories in order for maintainers to pick up commits and pull requests looking at the issue. You can do that for commits like this:

```bash
git commit -m "Issue NuCivic/dkan# : ..."
```

Just replace ** ** with the actual issue number. You can reference pull requests exactly like that if you add the same text **"NuCivic/dkan#&lt;issue_number&gt;"** in a comment. 

This really help us detecting changes and pulling them in in faster.



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6ee4a01ee901616670f69709afb4d5820b4b519d8f58c0861e66682eca20150f1f6d35f82d9024eb8f5acb1aeb2677561b)