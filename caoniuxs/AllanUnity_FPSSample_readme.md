![](Documentation/Images/Banner.png)

# FPS Sample

Thanks for checking out our project!

This is a fully functional, first person multiplayer shooter game made in
Unity and with full source and assets. It is in active development by a small
team from Unity Technologies. Our goals are to test and showcase new
features in Unity and to be of use for teams who can bootstrap on top of
this, extract useful bits and tools or simply learn from and get inspired by
what is in the project.

Visit our [landing page](http://u.720life.cn/g/2aac7accec24bab7699bf04c26e8a165feefb4dacf1110a94810eb802befcb4a) for more high
level information about the project. Or reach out [in the forum](http://u.720life.cn/g/64af7c40aa3180c24f5a61528b4f26b0256dbdbea2cb0a26d3a81912b79e70fcee6c87f63ba186cf47f9b4eb043e699449988cfbebb71907105179feb8b35cc0).

The project is using a number of new technologies: We use the new [HD Render
Pipeline](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046a6abcba3e6a04c08159bf1207f9ef05fa2a270827bd3ba65210d85d248b3ecf342dce78a426b2524eea490ea9470998f), meaning 
all content has been authored for HDRP. We are also using the new
[network transport layer](http://u.720life.cn/g/54145d0471d91890860f7f8463c03046a6abcba3e6a04c08159bf1207f9ef05f89f4cb4f90ac1333c65b8f1ad20b8defef083f26b9cd024d7b5a4da188b863db) as well as the [Entity-Component System](http://u.720life.cn/g/8d266662ad4c2ef0f814b8b9e3f57754de20801c4734462029c9d63139a7fbd43aa421b8666e05534cc351c603759d32d574dd459dddf8c1ae2ebb16a96c061d). 
In the case of ECS, we have primarily adopted the "ECS-pattern" and use it in
hybrid mode with a lot of regular components. As more and more features of
Unity become available in ECS-aware versions, we will migrate to them.

## Status and prerequisites

Current status at a glance:
```
Unity version: 2018.3 beta 6
Platforms    : Windows (client and server) and Linux (server only)
Fun          : Yes
Finished     : No
Useful       : We think so
```

## Getting the project

To get the project folder you need to clone the project.
Note, that 

> __IMPORTANT__: 
> This project uses Git Large Files Support (LFS). Downloading a zip file using the green button on Github
> **will not work**. You must clone the project with a version of git that has LFS.
> You can download Git LFS here: https://git-lfs.github.com/.

The project size is about 18GB (size of Assets folder). Your cloned repository
will be almost double of that due to git state. If it is much smaller,
you most likely did not have LFS when you cloned.

## Getting the right version of Unity

Once you have cloned the repository, you should install
the version of Unity that is listed above in the prerequisites section. Make
sure you include windows standalone support in your installation.

## Opening the project for the first time

The following guide should take you to the point where
you can hit play in the editor and run around the levels and also build a
standalone version of the game and use it to spin up a server and connect a
few clients to it.

The first time you open the project you need patience! It takes a while
to import all the assets.

> __NOTE__: Due to a bug in Unity 2018.3 beta, you have to take
the following steps right after the initial import:
> 1. Search for `t:prefab` in the Project search field. Then click on the first prefab and shift+click on the last to select them all. Right click and select __Reimport__.
> 2. Search for `t:model` in the Project search field. Repeat the same steps as for prefabs to reimport them all.
> 3. __IF__ you are on a version older than beta 6, you may have had a few crashes during import. In that case you need to find `GooRocket` and `GooRifle` in project, right click and select __Reimport__. 
>
> One day soon we will remove this note and there will be cake.

Once the editor is ready, open the _Project Tools Window_ by
navigating to ___FPS Sample > Windows > Project tools___.

It should look like this:

![](Documentation/Images/ProjectTools.png)

Keep this window docked as you will use it a lot. From here you can open the
levels, build assetbundles and build standalone players. Because this is a
multiplayer game you will need to work with standalone players a lot.

### Trying out preview mode

From the Project Tools window click __Open__ next to Level_00. Our levels are
split into multiple scenes but using these buttons will ensure you open all the scenes
that make up a level.

Once opened, try entering playmode in the editor. You should now
be able to run around in the level. This is what we call 'preview mode'. Here
you can move around and test your level, player traversal and weapons.

### Building bundles and standalone

Leave playmode again and in the Project Tools window, verify that
it says "Building for: StandaloneWindows64..." under the Game headline.
If it does not, change your platform in the usual way, using File > Build
settings window.

Now, in the Project Tools window in the bundles section, press __All \[force\]__.

This will build the levels and other assets into assetbundles. The first time
around this will take a significant amount of time as all shaders have to be
compiled.

Once you have built the bundles, hit __Build game__ in the game section.
This builds the standalone player. Again, first time will be slow.

### Using the quick start launcher

When this is done, locate the "Quick start" section at the bottom of the
Project Tools window. Fill out the settings like this:

> Mode: __Multiplayer__\
> Level: __Level_00__\
> Clients: __1__\
> Headless: __Checked__\
> Use editor: __Unused__

Now hit the green __Start__ button. This should launch two processes: one is
a standalone, headless server, the other is a client that will attempt to
connect to the server.

Congratulations! If you made it this far you should celebrate a bit!

## Development of FPS Sample, Contributions etc.

As of today, internally development of the project happens on Perforce. We
push versions of the project to github from there. As we do that we will update
the [CHANGELOG](CHANGELOG.md) with highlights but the full history is not
carried over.

For practical reasons we are not able to take larger contributions
just now. But bugfixes are very welcome! Read the guidelines for
contributing in [CONTRIBUTING](CONTRIBUTING.md).

## More information

Check out the [Documentation](Documentation/) folder for more information. In particular, the [Getting Started Guide](Documentation/GettingStarted.md) is a good place to, well, start.

## License

Our intention is that you can use everything in this project as a starting
point or as bits and pieces in your own Unity games. For the legal words, see
[LICENSE.md](LICENSE.md).


 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e6c5bc3d7b1c513f04a9534ccb60fd0adc02b895c3157dcebf48b9da77a9f84ab2b7c1de93b9687b6921e1cfda85145b6)