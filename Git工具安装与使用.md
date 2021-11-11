#  Git工具使用



<img src="https://gitee.com/jingwen-celia/picgo-second/raw/master/img/20211019163228.png" style="zoom:80%;" />

## 安装

1.官网地址：https://git-scm.com/downloads

2.根据自己的需求点击下载：

<img src="https://gitee.com/jingwen-celia/picgo-second/raw/master/img/20211019120206.png" style="zoom: 67%;" />

3.下载好，安装时候一路点next就好

##  Github教程

[https://www.bilibili.com/video/BV1Xx411m7kn](https://www.bilibili.com/video/BV1Xx411m7kn)

[官方教程](https://docs.github.com/en/github/importing-your-projects-to-github/importing-source-code-to-github/adding-an-existing-project-to-github-using-the-command-line)

## 下载代码

以Amov其中一个GitHub上的仓库为例，如果你想要下载这个仓库里的文件，首先先找到这个仓库。

1. 点击【Code】- 点击复制连接按钮<img src="https://gitee.com/jingwen-celia/picgo-second/raw/master/img/20211019121109.png" style="zoom:67%;" />

<img src="https://gitee.com/jingwen-celia/picgo-second/raw/master/img/20211019120800.png" style="zoom:33%;" />



2. 新建文件夹，在空白位置**右击鼠标 - 选择【Git Bash Here】**

<img src="https://gitee.com/jingwen-celia/picgo-second/raw/master/img/20211019153725.png" style="zoom:50%;" />



3. 在打开的终端中输入【git clone + 想要下载的仓库网址】，比如现在要git clone我们上述复制的仓库网址 【git clone https://github.com/amovlab-official/Tnote.git】

<img src="https://gitee.com/jingwen-celia/picgo-second/raw/master/img/20211019153429.png" style="zoom:67%;" />

<img src="https://gitee.com/jingwen-celia/picgo-second/raw/master/img/20211019154009.png" style="zoom:80%;" />



## 上传文件 

前期准备：

1.首先必要有GitHub账户，如果没有请上去官网上注册。（教程：https://blog.csdn.net/weixin_45309916/article/details/107750708）

2.找到你想要上传的GitHub上的仓库，复制仓库地址

<img src="https://gitee.com/jingwen-celia/picgo-second/raw/master/img/20211020154741.png" style="zoom: 50%;" />   



回到本地

1.新建文件夹用来放仓库内容，在新的文件夹空白处 【右击】-【Git Bash Here】

<img src="https://gitee.com/jingwen-celia/picgo-second/raw/master/img/20211020162529.png" style="zoom:50%;" />

2.输入：【git clone + 仓库地址】，克隆仓库

例如这里的是【git clone https://github.com/amovlab-official/Tnote.git】

<img src="https://gitee.com/jingwen-celia/picgo-second/raw/master/img/20211020163607.png" style="zoom:67%;" />

3.把需要上传的文件夹放入到下载好的远程仓库文件夹内

比如需要上传的文件是【wjw.md】,将它拷贝至刚刚克隆的文件夹内

![](https://gitee.com/jingwen-celia/picgo-second/raw/master/img/20211020174640.png)

4.依次输入以下命令：

```
1.cd + 你克隆下来的文件夹 //比如这里是 cd Tnote
2.git init
3.git add .
4.git commit -m"你的提交信息"
5.git push
```

上传成功

## github常用命令

#### 1.使用命令行将现有项目添加到 GitHub



1. 在github上新建一个和本地项目一样名称的仓库

2. 打开终端，进入本地项目
   初始化：

   ```java
   git init
   ```

   添加文件

   ```java
   git add .
   git commit -m "First commit"
   ```

   分支

   ```
   git branch -M main
   ```

   链接远程仓库,输入用户名密码

   ```java
   git remote add origin https://github.com/willian-li/pathfollowingwithobstacleavoidance.git
   ```

   上传到master分支

   ```java
   git push -u origin main
   ```

3. 设置主分支为master
   [https://www.cnblogs.com/dongyaotou/p/14130089.html](https://www.cnblogs.com/dongyaotou/p/14130089.html)

4. 删除main分支
   [https://blog.csdn.net/weixin_30646315/article/details/97449384](https://blog.csdn.net/weixin_30646315/article/details/97449384)

#### 2.github本地切换分支

[https://www.cnblogs.com/u-1596086/p/11328374.html](https://www.cnblogs.com/u-1596086/p/11328374.html)

1. 查看分支

   ```java
   git branch -a
   ```

2. 切换分支

   ```
   git reset --merge
   ```

   ```java
   git checkout master
   ```

#### 3.提交文件到仓库

[官方教程](https://docs.github.com/en/github/managing-files-in-a-repository/managing-files-using-the-command-line/adding-a-file-to-a-repository-using-the-command-line)

1. 添加

   ```java
   git add .   
   git commit -m “first commit”    
   ```

2. 更新本地仓库（远程做了文件修改要执行这步）

   ```java
   git pull origin master
   ```

3. 再上传

   ```java
   git push -u origin master   
   ```





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
