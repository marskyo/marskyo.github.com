---
title: Windows To Go制作教程 —— 随身携带Windows系统
layout: post
date: 2018-03-07 10:22
comments: true
tags:
  - Essay
---

我现在越来越倾向于办公和轻娱乐，感觉Mac比Windows更适合和稳定，而且Mac和iPhone的很多功能可以无缝衔接，用起来也很方便，但是很多功能还是离不开Windows，比如网银、报税什么的，所以必须还是要能兼容一下，看了很多教程，目前的解决方案大概三种：

1. Mac自带的启动转换助理安装Windows系统
2. 通过虚拟机软件安装Windows系统
3. 用微软的Windows To Go功能将Windows装进U盘或移动硬盘等任何移动设备

我的MacBook一共只有500GB，实在不想浪费一点空间，而且Windows系统的日常使用率很低，所以第一种方案不是好的方案，第二种除了空间问题外，正版虚拟机还需要购买，也是不便之处，第三种方案是目前较佳选择，不占用任何系统空间，移动设备还可以随时带着走。



## 准备工作

1. 一台装有Windows系统的电脑，我的是一台ThinkPad笔电，只有Mac的只能选择用启动转换助理或虚拟机先在电脑上装双系统。

2. 准备安装的介质，U盘、移动硬盘、固态U盘、mSATA、SD卡……容量至少大于16GB，推荐至少64GB，普通U盘的速度较慢，而且发热明显，建议有能力的选择固态U盘或mSATA，另外微软有一份推荐的适合[Windows To Go的U盘列表](https://docs.microsoft.com/zh-cn/previous-versions/windows/it-pro/windows-8.1-and-8/hh831833(v=ws.11))，但是肯定价格不菲，其实不是推荐的U盘、硬盘一样可以安装。

   <center>下面三种移动设备都可以安装（普通U盘、自组mSATA、移动硬盘）</center>

   ![](http://lc-ec5pgDDk.cn-n1.lcfile.com/vhitrgJld5jEI88wRh0wWWPH8O4EwB2Rzg2U1qm2.jpg)

3. 第一次安装时需要外接键盘，不能全键盘操作的还需要外接鼠标。

4. 如果是Mac系统，可以先在启动转换助理中下载好需要的Windows驱动，拷贝到单独U盘或后续拷贝到装好系统的移动设备。

   <center>启动转换助理。</center>

   ![](http://lc-ec5pgDDk.cn-n1.lcfile.com/CxhcLTpfmf6QCA7bvDBxoyhLY9iwuMI0lkVIe9Js.jpg)

   <center>选择菜单栏操作，点击下载Windows支持软件。</center>

   ![](http://lc-ec5pgDDk.cn-n1.lcfile.com/VgsyO7T1DyjGLIkyXNL6Wn5Kg4Ac6h3IwT0ar84a.jpg)

   <center>选择保存位置，然后会下载好一个文件夹，里面就是这台Mac的Windows驱动。</center>

   ![](http://lc-ec5pgDDk.cn-n1.lcfile.com/gHQOlTdMK8qTEyRKJmp7CXN3nvKyOel1tnBs8Ul5.jpg)

5. Windows镜像文件[MSDN](https://msdn.itellyou.cn/)，微软建议的是Windows企业版，如果不用微软原生Windows To Go工具安装，版本无所谓，但是建议选择企业版或专业版，另外建议安装Windows 8.1及以上的系统。
   ​

## 安装Windows To Go



#### 三种安装方法：

1. 微软自带的方法是通过Windows企业版的Windows To Go功能来进行安装
2. 通过WinToUSB软件安装
3. 通过WTG辅助工具软件安装

第一种方法是微软原生安装方法，但需要Windows企业版，我的老笔记本都是家庭版，所以不适合，也未尝试用此种方法，安装Windows企业版的同学可以自行尝试，可参考[知乎这篇教程](https://www.zhihu.com/question/35253149)。

第二种和第三种方法我都有尝试，可以正常安装，区别是WinToUSB除了免费版还有收费版，免费版貌似只能传统安装，不能选择VHD、VHDX模式。

![](http://lc-ec5pgDDk.cn-n1.lcfile.com/ULUyzOVSx6jTclzV1EtByWDnxKs0sRGS05aNWcf1.jpg)

软件操作简单，按照步骤安装即可。

第三种方法是萝卜头IT论坛的WTG辅助工具，目前最新版本4.8，[软件下载地址](http://bbs.luobotou.org/thread-761-1-1.html)。

启动软件。

![](http://lc-ec5pgDDk.cn-n1.lcfile.com/CJEmA7JecYqE7H8KaDVG0LXTSvIDiafypj004Ogo.jpg)

加载Windows镜像文件，选择镜像文件的install.win。

![](http://lc-ec5pgDDk.cn-n1.lcfile.com/NmOb5G0erVs2VjCIqanUQi3cphGnUxsc5u1AnM73.jpg)

选择需要安装的移动设备，我用的是自己组装的mSATA，右边设置选项选择模式，传统模式也可，如果安装Windows 8.1以上尽量选择VHDX模式，VHD和VHDX模式是一种虚拟磁盘。

传统方式是直接将install.wim中的文件解压到优盘上，与我们平时使用的系统差不多。
优点是：这样的系统 磁盘性能较好。
缺点是：写入速度较慢，某些程序不能安装到优盘上。

VHD：
VHD写入是一种新方法，原理是建立一个VHD虚拟盘，将文件解压到VHD虚拟磁盘中。
然后通过引导程序，引导这个虚拟磁盘。
优点是：写入速度往往较快，一般系统中的程序，都可以在优盘系统中安装。
缺点：XP系统不支持VHD写入。

VHDX：由微软推出Windows 8将支持VHDX文件，新的VHDX格式能支持64TB空间，是当前的VHD格式的2TB空间限制的32倍。

我安装Windows 10，所以选择VHDX，我的MacBook是2016款，基本2015款以后的都选择UEFI+GPT模式。

![](http://lc-ec5pgDDk.cn-n1.lcfile.com/zzVb4meyHssU3UMxDJGk2VJxpElA7z6PlqakcQvx.jpg)

分卷如果有选项可以根据需求选择或默认自动。

![](http://lc-ec5pgDDk.cn-n1.lcfile.com/m6kdfBynFbUcutejqjidfgwwQ30SQ42dDiBMhVRz.jpg)

VHD选项下可以自行设置虚拟硬盘大小或默认。

![](http://lc-ec5pgDDk.cn-n1.lcfile.com/xnR5be1Jyz1KGnWyPsrwFvllSPyeHSOEh8khrCv1.jpg)

系统模式下根据需求选择，一般不用动。

![](http://lc-ec5pgDDk.cn-n1.lcfile.com/rSsqbMyq2tvE7QF4KEOpQObzCQ1jBVuYtCaviNsw.jpg)

分区选项下EFI分区可以自行设置大小或默认，全部选项设置完成后点击创建按钮。

![](http://lc-ec5pgDDk.cn-n1.lcfile.com/xnSXjl3L7x7M9UYrwWX6BIHSoxT3zSqsoRHbMxPm.jpg)

提示确定。

![](http://lc-ec5pgDDk.cn-n1.lcfile.com/HuAdhk0DxCAEAveD9Q6ECIDrmw9FipjtRNaFFcAL.jpg)

然后开始制作过程，不同的移动设备安装时间不同。

![](http://lc-ec5pgDDk.cn-n1.lcfile.com/dkLKVxBeKOFEkzb4NKkocHylXoUycTpk7Flm2W7N.jpg)

![](http://lc-ec5pgDDk.cn-n1.lcfile.com/XNj0HIuJ8zBDTKDBbR2LrxvhiL9InzcQ3pTFpcBe.jpg)

![](http://lc-ec5pgDDk.cn-n1.lcfile.com/EoPBdgc3rmWDl3ml4sDqt4ykF9GeReyQv9IMAzOv.jpg)

普通U盘和机械硬盘时间较长，固态U盘、mSATA基本几分钟就可以安装完成。

![](http://lc-ec5pgDDk.cn-n1.lcfile.com/zqD8IUDnkkpCAAqAPbiNtQhp1xag0GAfYwQhkKMQ.jpg)

设备不同以上选项略有不同，如果一次失败也没有关系，个别设置稍微更改后可再行进行制作尝试。



## 配置Windows系统

安装完成后可以将之前下载好的WindowsSupport文件夹拷贝到移动设备，然后将移动设备插入MacBook，这时需接上外接键盘，开机同时按住Option键进入系统选择界面。

![](http://lc-ec5pgDDk.cn-n1.lcfile.com/97ByBPhN9X6MwvmEPUnjm5hVLVTfMdjBA9XnOuPr.jpg)

如在其他Windows系统电脑上运行Windows To Go可下载万能驱动软件，进入BIOS更改启动设置，改选移动设备优先启动进入WTG系统。

常规配置Windows，这时MacBook键盘无驱动无反应，外接键盘一路Enter，设置用户名、密码，再一路Enter，配置完成进入Windows系统。

![](http://lc-ec5pgDDk.cn-n1.lcfile.com/vj19RoqCxIjNlp9wSQ8wzPJ5Qukj5lzywEHNuF9H.jpg)

![](http://lc-ec5pgDDk.cn-n1.lcfile.com/Ap2NVUFH0BnHxp2wotnyjN1n2QokW8Eu2i5DXPqU.jpg)

打开系统，找到刚才拷贝的WindowsSupport文件夹，安装驱动。

![](http://lc-ec5pgDDk.cn-n1.lcfile.com/52y5WN6tr9xVI7WVCEpkTSpQe57hBSbPKAvHHUSD.jpg)

![](http://lc-ec5pgDDk.cn-n1.lcfile.com/FSDHMLfK6UUHieOF3AcVj9iE5xt4MQmjPOlfB81X.jpg)

安装重启完成之后就不需要外接键盘了，开始享受Windows To Go。

![](http://lc-ec5pgDDk.cn-n1.lcfile.com/krNB8sCkcfCirI1ASLGrjWIxvyiB5mFmuBQBJD51.jpg)



## 其他说明注意事项

1. 如果Windows使用率不高，不玩大型游戏，普通USB 3.0 U盘足够安装使用。
2. 萝卜头IT论坛一直强力推荐他们的ChipFancier Windows To Go专用定制固态U盘，我开始图省事也买了一个，但是在MacBook上使用存在一些问题，不是U盘问题，而是MacBook只有一个Type-C接口，必须用到外接Hub，但是我的Hub不能兼容ChipFancier，几次安装后进入配置系统时蓝屏，问客服说也出现过这种问题，让换Hub，不过换Hub也不一定能解决问题，有一定要碰Hub的运气成分，最后还是退货了。后来用我上面照片上的U盘、自组mSATA、移动硬盘都可以兼容我的Hub，进入系统无问题。
3. MacBook的触摸板在Windows下使用的感觉要比Mac系统下差很多，不知道是不是系统问题。
4. 安装后移动设备不影响在Mac或其他Windows电脑上的正常存储使用，只是Windows To Go占去了一部分容量。
5. 采用VHD或VHDX模式可以将现有设备的Windows系统通过WTG辅助工具直接复制到新的移动设备上。