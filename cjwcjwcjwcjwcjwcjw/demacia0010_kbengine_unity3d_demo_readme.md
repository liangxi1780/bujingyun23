KBEngine_unity3d_demo
=============

##This client-project is written for kbengine(a MMOG engine of server)
http://www.kbengine.org


##Releases

	sources		: https://github.com/kbengine/kbengine_unity3d_demo/releases/latest
	binarys		: https://sourceforge.net/projects/kbengine/files/


##Start:
		1: Use git to get the plugin(client) and demo-assets(server):

			In the kbengine_unity3d_demo directory:

			* Git command: git submodule update --init --remote
![submodule_update1](http://www.kbengine.org/assets/img/screenshots/gitbash_submodule.png)

			* Or use TortoiseGit(menu): TortoiseGit -> Submodule Update:
![submodule_update2](http://www.kbengine.org/assets/img/screenshots/unity3d_plugins_submodule_update.jpg)

			*Or manually get the plugin(client) and demo-assets(server)

				Download plugin(client):
					https://github.com/kbengine/kbengine_unity3d_plugins/archive/master.zip
					unzip and copy to "Assets/plugins/kbengine/kbengine_unity3d_plugins"

				Download demo-assets(server):
					https://github.com/kbengine/kbengine_demos_assets/releases/latest
					unzip and copy to "kbengine/"  (The root directory server engine, such as $KBE_ROOT)

		2: Build:
			Unity Editor -> File -> Build Settings -> PC, MAC & Linux Standalone.


##Configure demo:

	Change the login address:
![demo_configure](http://www.kbengine.org/assets/img/screenshots/demo_configure.jpg)

		kbengine_unity3d_demo\Scripts\kbe_scripts\clientapp.cs -> ip
		kbengine_unity3d_demo\Scripts\kbe_scripts\clientapp.cs -> port


##Start the servers:

	Build(KBEngine):
		http://www.kbengine.org/docs/build.html

	Installation(KBEngine):
		http://www.kbengine.org/docs/installation.html

	Copy "kbengine_unity3d_demo\kbengine_demos_assets" to KBEngine root directory:
		"kbengine\" is the engine root.

	Check the startup status:
		If successful will find log "Components::process(): Found all the components!".
		Otherwise, please search the "ERROR" keyword in logs, according to the error description to try to solve.
		(More: http://www.kbengine.org/docs/startup_shutdown.html)

![demo_configure](http://www.kbengine.org/assets/img/screenshots/demo_copy_kbengine.jpg)


	Start server:
		Windows:
			kbengine\kbengine_demos_assets\start_server_fixed.bat

		Linux:
			kbengine\kbengine_demos_assets\start_server_fixed.sh

		(More: http://www.kbengine.org/docs/startup_shutdown.html)


##Start the client:

			Directly start(U3DEditor or Executable file).



##Navmesh-navigation(Optional):
	
	The server to use recastnavigation navigation.
		kbengine\demo\res\spaces\*

	Generation Navmeshs:
		https://github.com/kbengine/unity3d_nav_critterai


![screenshots1](http://www.kbengine.org/assets/img/screenshots/unity3d_demo9.jpg)
![screenshots2](http://www.kbengine.org/assets/img/screenshots/unity3d_demo10.jpg)
![screenshots3](http://www.kbengine.org/assets/img/screenshots/unity3d_demo11.jpg)



 # 良心友情链接

[腾讯QQ群快速检索](http://u.720life.cn/s/8cf73f7c)

[软件免费开发论坛](http://u.720life.cn/s/bbb01dc0)

# 版权声明 

本文由良心工作室整理 欢迎加入[官方交流Q群](https://u.720life.cn/s/f2316816)谈合作

[本文转自如下链接](http://u.720life.cn/g/2e71d0f0a5c601172267ba20d3a43c6e84065f94b7258d6bbb8c628fc9d7c118e2866603d4d8b402530e7a8bf028e4014685f00741a9fb664262fef86ab618894a8c91d003c98cf28ca4899e312eaa24)