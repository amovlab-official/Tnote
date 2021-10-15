# Airsim使用教程

## 前言

此文档会带大家在Windows环境下进行Airsim的环境配置，是根据知乎大佬宁子安的文档进行操作的。有问题可以进微信群和大家一起讨论。AirSim这个软件很大并且对电脑配置要求也很高，所以建议大家在手头没有主机电脑或者笔记本内存不够的情况下，不要轻易选择下载AirSim。

 

此文档在配置完Airsim等相关软件后，还会进行1-2个小demo进行测试，不能安装的同学可以先看看AirSim软件的仿真效果。

 

俗话说学习软件的最好学习资料就是看官方文档，同样学习AirSim的最好办法就是查看官方wiki。网址：https://microsoft.github.io/AirSim/

<img src="https://gitee.com/jingwen-celia/picgo-second/raw/master/img/20211014183109.png"  />


 

## 1.注意电脑配置

AirSim软件对电脑要求较高。以下是我找到的三个例子可以给大家进行参考。

![](https://gitee.com/jingwen-celia/picgo-second/raw/master/img/20211014183549.png)

<center>图1 官方推荐电脑配置说明</center>



![](https://gitee.com/jingwen-celia/picgo-second/raw/master/img/20211014183202.png)

<center>图2 知乎宁子安推荐电脑配置</center>



![](https://gitee.com/jingwen-celia/picgo-second/raw/master/img/20211014183617.png)

<center>图3 我自己电脑配置</center>

## 2.软件汇总

以下均为在Windows配置AirSim的需求软件。现在不用下载，后面跟着步骤再进行下载。

* AirSim版本：v1.5.0 (2021年5月发布)
* 虚幻引擎版本：4.26.2
* Visual Studio版本：Visual Studio Community 2019
* Anaconda版本：v3（Anaconda3-2021.05）
* Python版本：Python 3.8（Anaconda中配置）
* Pycharm版本：Pycharm 2021.2.2



## 3.安装（一）

### 3.1安装Visual Studio 2019集成开发环境

**下载网址：**https://visualstudio.microsoft.com/zh-hans/vs/

<font color="red"> 注意：目前虚拟引擎只支持Visual Studio 2019和2017版本。</font>

（1）下载时直接选择community版本：

![](https://gitee.com/jingwen-celia/picgo-second/raw/master/img/20211015092906.png)

<center>图4 VS 2019官网界面</center>

​	（2）下载好安装时请选择：

​			  在【工作负荷】选项卡下面，请勾选【使用C++的桌面开发】，同时在 【单个组件】选项卡下面搜索并勾选【Windows 10 SDK 10.0.18362】。

​	（3）安装完成后需要重启电脑。



### 3.2 安装虚拟引擎

下载网址：https://www.unrealengine.com/zh-CN/

进入后点击右上角的【下载】，建议选择下载 “创作许可”，如下图所示。点击 “立即下载” 后，会提示登录 Epic Game 账户，如果没有，则需要注册。

![](https://gitee.com/jingwen-celia/picgo-second/raw/master/img/20211015110630.png)

<center>图5 选择“创作许可”版本下载</center>

下载安装好后，选择【Libiary】，安装驱动【4.26.2】

![](https://gitee.com/jingwen-celia/picgo-second/raw/master/img/20211015110831.png)

<center>图6 驱动版本列表</center>

 

### 3.3 安装Airsim

（1）在开始菜单栏-搜索中搜索【Developer Command Prompt for VS 2019】，运行。

![](https://gitee.com/jingwen-celia/picgo-second/raw/master/img/20211015111032.png)

<center>图7 运行“developer Command Prompt for VS 2019”</center>

（2）打开后进入到你想保存AirSim所在的文件夹位置，这里我选择的是D盘（不建议下载到C盘），使用Git工具进行下载，（如果没有工具请先到[官网](https://git-scm.com/downloads)下载Git工具）。输入指令【git clone https://github.com/Microsoft/AirSim.git】。

![](https://gitee.com/jingwen-celia/picgo-second/raw/master/img/20211015111917.png)

<center>图8 下载AirSim</center>

## 4.运行环境测试（block测试）

### 4.1 block测试

安装到这一步，可以先来使用block环境来测试一下Airsim和虚拟引擎是否配置成功。根据官网（https://microsoft.github.io/AirSim/unreal_blocks/）所写，在已经安装好的AirSim文件夹中有一个AirSim自带的Unreal环境稳健，在【Unreal/Environments/Blocks】目录中。

具体操作如下：

		1. 打开【Developer Command Prompt for VS 2019】
		2. 进入文件夹，指令为【CD Airsim\Unreal\Environments\Blocks】，并输入指令【update_from_git.bat】
		3. 双击文件夹中生成的Blocks.sln文件（见下图），会自动运行Visual Studio2019
		4. 在Visual Studio 2019界面中，有三点需要操作：编译选项改为【DebugGame_Editor】和【Win64】，最后要把blocks设为【启动项】
		5. 点击【调试—开始调试】

![](https://gitee.com/jingwen-celia/picgo-second/raw/master/img/20211015112346.png)
<center>图9 官方wiki对于启动Block环境的相关说明 </center>

![](https://gitee.com/jingwen-celia/picgo-second/raw/master/img/20211015112423.png)
<center>图10 VS 2019启动环境三步骤</center>

点击后会打开Unreal Engine，打开blocks环境，点击【运行】

![](https://gitee.com/jingwen-celia/picgo-second/raw/master/img/20211015112538.png)
<center>图11 运行Blocks环境</center>

此时会跳出对话框，如果选择 YES 会出现小车模型，点击 NO 会出现四旋翼无人机模型。这里我们点击NO。出现了以下画面表示我们配置成功至此，我们完成了基础配置。

![](https://gitee.com/jingwen-celia/picgo-second/raw/master/img/20211015112637.png)
<center>图12 四旋翼无人机模型</center>

### 4.2 搭建环境landscape

下面我们可以尝试在虚拟引擎中插入新的地图，并在新的地图上进行浏览。

 

（1）打开【Epic Game Launcher】，点击【Learn】，通过往下滑动，找到【Landscape Mountains】，点进去并点击【Create】，进行下载。

![](https://gitee.com/jingwen-celia/picgo-second/raw/master/img/20211015112915.png)
<center>图13 现在Landscape Mountains地图</center>

（2）找到下载好的地图文件夹位置，双击【LandscpeMountains.uproject】，会打开Unreal编辑器，点击左上角的【文件--新建C++类】，一直点下一步直到创建类，创建好后会自动跳转到Visual Studio2019。最后关闭Unreal和 Visual Studio2019。

![image-20211015113238793](C:\Users\Administrator.DESKTOP-KDTJ7L1\AppData\Roaming\Typora\typora-user-images\image-20211015113238793.png)

![](https://gitee.com/jingwen-celia/picgo-second/raw/master/img/20211015113300.png)
<center>图14创建C++文件</center>

（3）在原AirSim安装路径中，找到【Unreal--Plugins】的Plugins文件，将这个文件夹整个复制到刚刚下载好的地图目录中，如下图：

![](https://gitee.com/jingwen-celia/picgo-second/raw/master/img/20211015113408.png)
<center>图15 复制AirSim插件“Plugins”到新的工程</center>

<font color="orange">小Tips：“Plugins” 文件夹非常重要，可以把它复制到任何一个虚幻引擎的工程中，这样就可以使用 AirSim 插件。</font>

右键点击【LandscapeMountains.uproject】，选择打开方式为写字板或者其他，将其中代码更换为：

```c++
 {
     "FileVersion": 3,
     "EngineAssociation": "4.24",
     "Category": "Samples",
     "Description": "",
     "Modules": [
         {
             "Name": "LandscapeMountains",
             "Type": "Runtime",
             "LoadingPhase": "Default",
             "AdditionalDependencies": [
                         "AirSim"
                     ]
         }
     ],
     "TargetPlatforms": [
         "MacNoEditor",
         "WindowsNoEditor"
     ],
     "Plugins": [
             {
                     "Name": "AirSim",
                     "Enabled": true
             }
         ],
     "EpicSampleNameHash": "1226740271"
 }

```

（5）保存关闭后，右击LandscapeMountains.uproject。选择【Generate Visual Studio project files】。

![](https://gitee.com/jingwen-celia/picgo-second/raw/master/img/20211015120447.png)
<center>图16 生成Visual Studio项目</center>

（6）双击打开LandscapeMountains.sln文件，会自动运行Visual Studio2019。打开后重复上次调试三步骤：编译选项改为【DebugGame_Editor】和【Win64】，最后要把blocks设为【启动项】，最后点击调试，启动Unreal

（7）进入Unreal界面，需要进行一些设置：

a. 在最上层菜单栏找到【窗口--世界场景设置】，点击使其打钩

![](https://gitee.com/jingwen-celia/picgo-second/raw/master/img/20211015120605.png)
<center>图17 打开场景设置</center>

b. 在界面右下角的世界场景设置中选择游戏模式为【AirSimGameMode】

![](https://gitee.com/jingwen-celia/picgo-second/raw/master/img/20211015120644.png)
<center>图18  选择游戏模式为“AirSimGameMode”</center>

c. 在世界场景上方（界面右上角），世界大纲视图中搜索--player，共能搜出来11个初始玩家位置，删除10个只留下一个（偏于后续操作不出问题）。

​    在下方【细节】通过调整XYZ轴来调整初始玩家的位置。

![](https://gitee.com/jingwen-celia/picgo-second/raw/master/img/20211015120944.png)
<center>图19 查看初始玩家</center>

![](https://gitee.com/jingwen-celia/picgo-second/raw/master/img/20211015120959.png)
<center>图20更改初始玩家及位置</center>

d.两点非必须但建议的设置：

○ 打开菜单栏盘【编辑--编辑器偏好设置】，搜索【CPU】，把“**处于背景中时占用较小CPU**”选项打开。这样当Unreal 编辑器不在窗口的最前面时，就不会    实时渲染了，但是不影响仿真的运行。所以还是建议勾选。

![](https://gitee.com/jingwen-celia/picgo-second/raw/master/img/20211015121121.png)
<center>图21 勾选“处于北京市占用较少CPU” </center>

○点击主屏幕左上角小三角，打开【FPS】，此时右边就会出现当前的FPS和时延。当FPS下降到20以内时，说明数据处理比较缓慢，需要找到问题所在，并优化程序。FPS在20以上算是比较流畅的。

![](https://gitee.com/jingwen-celia/picgo-second/raw/master/img/20211015121149.png)
<center>图22 打开FPS设置</center>





 前期初始设置完毕后，保存设置，使用快捷键Ctrl+S保存设置。

点击右上角运行，此时跳出对话框，和之前一样点击yes会出现小车，点击no会出现无人机。

接下来我们更换至电脑视角，通过路径【C:\Users\你的用户名\Documents\AirSim】找到【setting.json】文件。

![](https://gitee.com/jingwen-celia/picgo-second/raw/master/img/20211015121219.png)
<center>图23 打开AirSim中的settings.json文件</center>

 将settings.json 里面代码改成电脑视角的代码，注意该代码里的ComputerVision是指电脑视角，改成Car就是小车模型，改成Multirotor就是对应着四旋翼无人机。

~~~
## SimMode可以设置为 Car、Multirotor ，分别对应小车、四旋翼无人机。
##设置成电脑视角代码：
{
   "SettingsVersion": 1.2,
   "SimMode": "ComputerVision"
 }

##设置成无人机代码：
 {
   "SettingsVersion": 1.2,
   "SimMode": "Multirotor"
 }
~~~



保存后重复【4.1-具体调试-4】步骤，运行虚拟引擎，进入地图后点击【运行】，此时按下F8，通过鼠标，方向键盘和Page Up/Page Down可以在地图中进行第一视角浏览了。

## 安装（二）

如果想通过代码控制无人机，还需要安装别的软件进行控制，这里我们选择使用Python进行编程，需要下载的软件是Anaconda和Pycharm，而这里是使用Anaconda对python环境进行管理。

### 5.1 Anaconda安装与配置

官网地址：https://www.anaconda.com/products/individual-d

下载：选择【Product-Individual Edition】，选择Windows版本下载。

 

按着提示一路安装完成后，在菜单栏中出现了几个应用：

* Anaconda Navigator：图形用户界面，用于管理python环境。
* Anaconda PowerShell Prompt：命令行工具。
* Jupyter notebook：基于web的交互式计算环境，可以编辑markdown，用于展示数据分析的过程。
* qtconsole：一个可执行 IPython 的仿终端图形界面程序。
* spyder：一个使用Python语言、跨平台的、科学运算集成开发环境。

 

配置Python环境，只需要应用到**Anaconda Navigator**和**Anaconda PowerShell Prompt**两个工具。

 

#### 配置Python环境

菜单搜索Anaconda Navigator，打开软件，点击【environment-Create】配置一个新的环境，自行命名，这里我命名为“Airsim”，Python选择的3.8版本，点击创建。

![](https://gitee.com/jingwen-celia/picgo-second/raw/master/img/20211015121332.png)
<center>图24 创建一个新环境</center>

![](https://gitee.com/jingwen-celia/picgo-second/raw/master/img/20211015121504.png)
<center>图25 新环境初始设置</center>

<font color="red">注意：这里的Location地址位置非常重要，需要记得新配置的环境在那个路径下。</font>

 

#### 创建第三方库

创建好后直接通过pip命令安装msgpack-rpc-python和airsim两个库。首先点击新建好环境（Airsim）右边的小三角，再点击【Open Terminal】打开终端；

![image-20211015121522762](C:\Users\Administrator.DESKTOP-KDTJ7L1\AppData\Roaming\Typora\typora-user-images\image-20211015121522762.png)
<center>图26 打开终端</center>

在终端中输入以下命令，进行安装两个库。

```
 pip install msgpack-rpc-python
 pip install airsim
```

### 5.2 Pycharm安装与配置

官方网址：https://www.jetbrains.com/pycharm/download/#section=windows

下载安装：有账号的可以选择professional版本，没有账号直接选择community免费版本。

​     安装除了安装路径自定义，其余都默认直接安装。

配置环境

这里需要配置Anaconda配置出的环境，还记得上个步骤专门划出来的路径location吗，就是用在这。以下具体步骤：

打开安装好的Pycharm，点击【New Project】

![](https://gitee.com/jingwen-celia/picgo-second/raw/master/img/20211015121649.png)
<center>图27 打开PyCharm</center>

勾选Previously configured interper，并点击右边![](https://gitee.com/jingwen-celia/picgo-second/raw/master/img/20211015121729.png)扩展。

![](https://gitee.com/jingwen-celia/picgo-second/raw/master/img/20211015121901.png)
<center>图28 进行环境配置</center>

点击System Interpreter，点击扩展，选择上个步骤配置出的环境（Airsim）路径里面的Python.exe。比如这里是【D:\ppam.u\Anaconda3\envs\AirSim\python.exe】。

![](https://gitee.com/jingwen-celia/picgo-second/raw/master/img/20211015121944.png)

![](https://gitee.com/jingwen-celia/picgo-second/raw/master/img/20211015121959.png)
<center>图29 Anaconda与PyCharm的环境配置</center>

 

然后就可以创建你的项目了，注意这里的location是指你的Python代码位置，可自定义。

![](https://gitee.com/jingwen-celia/picgo-second/raw/master/img/20211015122039.png)
<center>图30 创建新工程时需要修改的路径</center>

通过【右键点击新建项目-New-Python File】，就可以构建自己的Python代码。

![image-20211015122110417](C:\Users\Administrator.DESKTOP-KDTJ7L1\AppData\Roaming\Typora\typora-user-images\image-20211015122110417.png)
<center>图31 在新项目中添加Python文件</center>

## 6.Demo演示

通过上述就是所有基本配置，下面可以根据两个代码demo自己运行一下程序。

### 6.1 无人机飞正方形demo

代码：

~~~
 """
 飞正方形（速度控制）
 """
 import airsim
 import time
 
 client = airsim.MultirotorClient()  # connect to the AirSim simulator
 client.enableApiControl(True)       # 获取控制权
 client.armDisarm(True)              # 解锁
 client.takeoffAsync().join()        # 第一阶段：起飞
 
 client.moveToZAsync(-2, 1).join()   # 第二阶段：上升到2米高度
 
 # 飞正方形
 client.moveByVelocityZAsync(1, 0, -2, 8).join()     # 第三阶段：以1m/s速度向前飞8秒钟
 client.moveByVelocityZAsync(0, 1, -2, 8).join()     # 第三阶段：以1m/s速度向右飞8秒钟
 client.moveByVelocityZAsync(-1, 0, -2, 8).join()    # 第三阶段：以1m/s速度向后飞8秒钟
 client.moveByVelocityZAsync(0, -1, -2, 8).join()    # 第三阶段：以1m/s速度向左飞8秒钟
 
 # 悬停 2 秒钟
 client.hoverAsync().join()          # 第四阶段：悬停6秒钟
 time.sleep(6)
 
 client.landAsync().join()           # 第五阶段：降落
 client.armDisarm(False)             # 上锁
 client.enableApiControl(False)      # 释放控制权 """
 飞正方形（速度控制）
 """
 import airsim
 import time
 
 client = airsim.MultirotorClient()  # connect to the AirSim simulator
 client.enableApiControl(True)       # 获取控制权
 client.armDisarm(True)              # 解锁
 client.takeoffAsync().join()        # 第一阶段：起飞
 
 client.moveToZAsync(-2, 1).join()   # 第二阶段：上升到2米高度
 
 # 飞正方形
 client.moveByVelocityZAsync(1, 0, -2, 8).join()     # 第三阶段：以1m/s速度向前飞8秒钟
 client.moveByVelocityZAsync(0, 1, -2, 8).join()     # 第三阶段：以1m/s速度向右飞8秒钟
 client.moveByVelocityZAsync(-1, 0, -2, 8).join()    # 第三阶段：以1m/s速度向后飞8秒钟
 client.moveByVelocityZAsync(0, -1, -2, 8).join()    # 第三阶段：以1m/s速度向左飞8秒钟
 
 # 悬停 2 秒钟
 client.hoverAsync().join()          # 第四阶段：悬停6秒钟
 time.sleep(6)
 
 client.landAsync().join()           # 第五阶段：降落
 client.armDisarm(False)             # 上锁
 client.enableApiControl(False)      # 释放控制权
~~~



效果：

https://v.youku.com/v_show/id_XNTgwODMxNDYwMA==.html

 

### 6.2 无人机飞圆形demo

代码：

![image-20211015122236847](C:\Users\Administrator.DESKTOP-KDTJ7L1\AppData\Roaming\Typora\typora-user-images\image-20211015122236847.png)

<center>图33 无人机飞圆形代码</center>

 

效果：

https://v.youku.com/v_show/id_XNTgwODQwOTk4OA==.html



## 结束语

以上内容均是参考了知乎大佬【宁子安】和AirSim的官方wiki内容，请大家多提意见，如有不对定当及时修改。以下是我安装过程中遇到的一些问题，希望大家有遇到问题解决了也提出来，此文档作为定时更新文档放在那那那上。最后，阿木实验室面向所有AirSim开发者及爱好者发起招募，欢迎大家加入我们AirSim开发小组，一起为AirSim在无人机开源生态发展做出贡献。（可扫下方二维码进群进行技术交流）

 

进群二维码：

<img src="https://gitee.com/jingwen-celia/picgo-second/raw/master/img/d682a1c78b3843bc40dc6503e0386e3.jpg" style="zoom:25%;" />
<center>（如若过期，请联系小助手：yinyue199506 ，添加时备注：Airsim进群）</center>

 

 

## 常见错误汇总：

1.安装过程遇到以下错误：

ERROR: Could not find NetFxSDK install dir; this will prevent SwarmInterface from installing.  Install a version of .NET Framework SDK at 4.6.0 or higher.

解决方法：安装最新版本的 【.NET Framework SDK】

链接：https://dotnet.microsoft.com/download/dotnet-framework/net461

（注意点击下载Developer版本进行下载）

参考：https://zhuanlan.zhihu.com/p/133456753

 

2.配置landscape地图时，有显示该地图最多支持UE4 4.24引擎

 解决方式：可忽略继续配置，后续实测未发现有什么影响



3在安装airsim库时候，缺少numpy库可能会在其中有报错。宁神教程提前在环境中安装了，但是自己当时并没有搜到这个库就跳过了。后面报错也没有关系，因为后面系统自己会主动安装缺少的库。所以直接安装应该是没有问题的。
