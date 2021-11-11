# Prometheus仿真镜像安装说明（适用于联想刃9000K系列电脑）

## 所需设备：

联想9000K电脑一台

Prometheus仿真镜像安装U盘一个

## 安装步骤：

1. 按下刃9000K的开机键，在显示器出现LENOVO标识后快速点击键盘F12键，选择Enter Setup，进入联想Start Menu界面。如图所示：

![](https://gitee.com/jingwen-celia/picgo-second/raw/master/img/20211111121014.png)

2. 通过键盘和Enter键进入到Security->Secure Boot界面中，将Secure Boot一项设置从Enable更改为Disable。如图所示：

   ![](https://gitee.com/jingwen-celia/picgo-second/raw/master/img/20211111121302.png)

![](https://gitee.com/jingwen-celia/picgo-second/raw/master/img/20211111121310.png)

3. 进入Startup界面中，将Fast Boot选项从Enable修改为Disable。如图所示：

![](https://gitee.com/jingwen-celia/picgo-second/raw/master/img/20211111121430.png)

4. 在BIOS完成上述修改后，可按F10键等待电脑重启。

5. 重启进入Windows系统后，在“此电脑”上右键选择管理：

![](https://gitee.com/jingwen-celia/picgo-second/raw/master/img/20211111121452.png)

6. 在计算机管理界面中，选择磁盘管理->右键点选DATA1（D：）->压缩卷（未安装Prometheus仿真镜像的电脑D盘应该只有一个分区，图中示例是已经分好区的情况）：

![](https://gitee.com/jingwen-celia/picgo-second/raw/master/img/20211111121536.png)

7. 在“输入压缩空间量”选项中输入100000~200000（100~200GB）作为仿真镜像的硬盘空间后，点击压缩：

![](https://gitee.com/jingwen-celia/picgo-second/raw/master/img/20211111121558.png)

8. 在D盘中出现灰色的未分配分区后，分区步骤就完成了：

![](https://gitee.com/jingwen-celia/picgo-second/raw/master/img/20211111121618.png)

9. 插入Prometheus仿真镜像安装U盘（最好是插在机箱后置的USB口），在我的电脑中确认到U盘信息后，重新启动电脑，快速点按F12键。通过键盘选择USB-HDD启动选项（若没有该选项，可能是U盘未被识别，尝试其他USB接口并重启重复上述操作）：

![](https://gitee.com/jingwen-celia/picgo-second/raw/master/img/20211111121641.png)

10. 进入安装界面后，选择第二项“Boot System installer”：

![](https://gitee.com/jingwen-celia/picgo-second/raw/master/img/20211111121657.png)

11.进入到System Install界面后，可按图中所示输入，密码统一为”amov”后，点击next：

![](https://gitee.com/jingwen-celia/picgo-second/raw/master/img/20211111121718.png)

12. 在界面中，选择刚才分好的约200GB左右的硬盘空间后，首先将create new下面的数字改为“512”，再点击右边的⬅箭头（示例中下方是安装完成后镜像系统的硬盘分区，安装完成后应在size、label、filesystem这些标签上和它们保持一致）：

![](https://gitee.com/jingwen-celia/picgo-second/raw/master/img/20211111121809.png)

13. 可以看到，列表中出现了一个512MB的新分区。

![](https://gitee.com/jingwen-celia/picgo-second/raw/master/img/20211111122008.png)

14. 重新选择剩下的190多GB的空分区，这次分配16000MiB的空间作为内存空间：

![](https://gitee.com/jingwen-celia/picgo-second/raw/master/img/20211111122016.png)

![](https://gitee.com/jingwen-celia/picgo-second/raw/master/img/20211111122036.png)

15.  最后将剩余的分区一起作为硬盘空间：

![](https://gitee.com/jingwen-celia/picgo-second/raw/master/img/20211111122326.png)

![](https://gitee.com/jingwen-celia/picgo-second/raw/master/img/20211111122338.png)

16. 选择512MB的分区，将左下角的“Transfer User configuration files”点上✔，将右边的mout point选择为“/boot/efi”，最后点击右边的⬅箭头，之后可以看到这个分区的filesystem变为了vfat：

![](https://gitee.com/jingwen-celia/picgo-second/raw/master/img/20211111122426.png)

![](https://gitee.com/jingwen-celia/picgo-second/raw/master/img/20211111122442.png)

17. 选择16GB的分区，将右边的mout point选择为“SWAP”，最后点击右边的⬅箭头，可以看到这个分区的filesystem变为了SWAP：

![](https://gitee.com/jingwen-celia/picgo-second/raw/master/img/20211111122830.png)

![](https://gitee.com/jingwen-celia/picgo-second/raw/master/img/20211111122842.png)

18. 选择180GB的分区，将右边的mout point选择为“ / ”，最后点击右边的⬅箭头，可以看到这个分区的filesystem变为了ext4：

![](https://gitee.com/jingwen-celia/picgo-second/raw/master/img/20211111142921.png)

![](https://gitee.com/jingwen-celia/picgo-second/raw/master/img/20211111144237.png)

19. 重新选择512MB的分区，点击Next->Start，等待安装完成即可：

![](https://gitee.com/jingwen-celia/picgo-second/raw/master/img/20211111144257.png)

![](https://gitee.com/jingwen-celia/picgo-second/raw/master/img/20211111144307.png)

20. 安装结束后，选择reboot，开机时按F12进入启动选项，选择SATA1：Ubuntu进入仿真镜像。此时可以拔下安装U盘：

![](https://gitee.com/jingwen-celia/picgo-second/raw/master/img/20211111144325.png)

21. 进入Ubuntu系统后，连接WIFI，打开终端，首先进行系统更新。依次使用下列命令行执行：

    sudo apt-get update

    sudo apt-get upgrade

![](https://gitee.com/jingwen-celia/picgo-second/raw/master/img/20211111144353.png)

![](https://gitee.com/jingwen-celia/picgo-second/raw/master/img/20211111144400.png)

22.在update和upgrade自动更新完毕后，继续使用下列命令行安装显卡驱动：

sudo lshw -c display

sudo ubuntu-drivers devices

sudo ubuntu-drivers autoinstall

依次执行等待安装结束即可重启。

23.重新进入仿真镜像后，应该可以看到系统分辨率变为正常状态。此时可以打开系统桌面上的“Prometheus镜像快速入门”按说明进行。

![](https://gitee.com/jingwen-celia/picgo-second/raw/master/img/20211111144523.png)

