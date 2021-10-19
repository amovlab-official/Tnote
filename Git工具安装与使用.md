#  Git工具使用



<img src="https://gitee.com/jingwen-celia/picgo-second/raw/master/img/20211019163228.png" style="zoom:80%;" />

## 安装

1.官网地址：https://git-scm.com/downloads

2.根据自己的需求点击下载：

<img src="https://gitee.com/jingwen-celia/picgo-second/raw/master/img/20211019120206.png" style="zoom: 67%;" />

3.下载好，安装时候一路点next就好

## 使用

以Amov其中一个GitHub上的仓库为例，如果你想要下载这个仓库里的文件，首先先找到这个仓库。

1. 点击【Code】- 点击复制连接按钮<img src="https://gitee.com/jingwen-celia/picgo-second/raw/master/img/20211019121109.png" style="zoom:67%;" />

<img src="https://gitee.com/jingwen-celia/picgo-second/raw/master/img/20211019120800.png" style="zoom:33%;" />



2. 在你想要保存下载文件的位置中**右击鼠标 - 选择【Git Bash Here】**

<img src="https://gitee.com/jingwen-celia/picgo-second/raw/master/img/20211019153725.png" style="zoom:50%;" />



3. 在打开的终端中输入【git clone + 想要下载的仓库网址】，比如现在要git clone我们上述复制的仓库网址 【git clone https://github.com/amovlab-official/Tnote.git】

<img src="https://gitee.com/jingwen-celia/picgo-second/raw/master/img/20211019153429.png" style="zoom:67%;" />

<img src="https://gitee.com/jingwen-celia/picgo-second/raw/master/img/20211019154009.png" style="zoom:80%;" />



## 常见问题汇总

### 1.右键没有"Git Bash Here"，或者Git Bash Here 没有图标显示。

**解决方法：**

第一步：Win + R，输入：**regedit**

<img src="https://gitee.com/jingwen-celia/picgo-second/raw/master/img/20211019154608.png"  />

第二步：在最上方搜索：**计算机\HKEY_CLASSES_ROOT\Directory\Background\shell**

<font color="red">（若无shell文件，新建一个文件命名shell，注意层级在第一层）</font>

<img src="https://gitee.com/jingwen-celia/picgo-second/raw/master/img/20211019154724.png" style="zoom: 67%;" />

第三步：选中shell，【右键shell】-【新建】-【项】，命名为 “Git Bash Here”

![](https://gitee.com/jingwen-celia/picgo-second/raw/master/img/20211019160345.png)![](https://gitee.com/jingwen-celia/picgo-second/raw/master/img/20211019160432.png)  

第四步：选中刚刚建好的文件，【右键Git Bush Here】-【新建】-【项】，命名为“Command”

![](https://gitee.com/jingwen-celia/picgo-second/raw/master/img/20211019162449.png)

第五步：选中新建Command，点击右边菜单栏默认【右键】-【修改】，里面改为你的git安装目录加上git-bash.exe，

比如这里我的是：【D:\ppam.u\Git\bin\bash.exe】。 点击确定

![](https://gitee.com/jingwen-celia/picgo-second/raw/master/img/20211019162435.png)



<font face="微软雅黑" size=3 color = #F4A460>**这时候我们发现鼠标右键出现了“Git Bash Here”，也可以正常启动，但是没有图标，为了美化我们进行如下操作**</font>

第六步：点击Git Bash Here文件，【右键】-【新建】-【字符串值】，取名 “Icon”

![](https://gitee.com/jingwen-celia/picgo-second/raw/master/img/20211019161435.png)

第七步：双击修改属性，修改值为【D:\ppam.u\Git\mingw64\share\git\git-for-windows.ico】，这个文件安装位置与Git安装位置有关，自己可以找一下。

![](https://gitee.com/jingwen-celia/picgo-second/raw/master/img/20211019162356.png)

![](https://gitee.com/jingwen-celia/picgo-second/raw/master/img/20211019163037.png)

点击确定，在文件夹中鼠标右键可以看到出现了有图标的“Git Bash Here”。
