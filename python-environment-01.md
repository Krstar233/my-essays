---
title: Python环境的搭建
date: 2020-10-04 13:13:57
tags:
- python
- 环境搭建
---
我们学习Python之前，首先要搭建一Python语言能够运行的环境。Python语言作为一种可移植性强的语言，可以在多种平台上使用，考虑到大部分同学使用的都是windows系统，本篇就介绍如何在windows平台上搭建一个Python的运行环境。

- 环境介绍
操作系统平台：windows10
编辑器：Pycharm2019
解释器：Python3.7.4

- Pycharm的下载
Pycharm的下载链接：[https://www.jetbrains.com/pycharm/download/#section=windows](https://www.jetbrains.com/pycharm/download/#section=windows)
Pycharm是付费软件，但同时也有提供免费版本，而免费版将会每隔一段时间会让你重启一次Pycharm，如果大家觉得麻烦的话，也可以自行寻找破解版或者付费使用。
![Pycharm下载页面](https://upload-images.jianshu.io/upload_images/17036461-92d843181324ca96.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

- Pycharm的安装
打开安装包，如果不修改安装路径的话，其实一直点next就可以了。
![安装页面](https://s1.ax1x.com/2020/10/08/0Bn6R1.md.png)

安装设置中可以选择添加桌面快捷方式，也可自行根据需求选择
![安装设置](https://s1.ax1x.com/2020/10/08/0Bn2M6.png)

- 初始化并运行Pycharm
第一次运行Pycharm它会让你进行一些默认的设置，可以根据需要进行设置。
主题我选的是light主题
![设置主题](https://s1.ax1x.com/2020/10/08/0BnLsf.md.png)
如果没有特殊需要的话一般不安装另外的插件。
![是否需要扩展插件](https://s1.ax1x.com/2020/10/08/0BnxoQ.md.png)
这里比较重要的是，这边有个激活页面，因为我们没有购买，所以选择"Evaluate for free"，然后点击 Evaluate。
![激活页面](https://s1.ax1x.com/2020/10/08/0BuCzq.png)
出现这个界面说明Pycharm已经激活成功可以使用了~ 但是如果要完成Python环境的配置的话，仍然需要安装一个Python的解释器才可以在Pycharm中运行编写的Python程序。
![Pycharm](https://s1.ax1x.com/2020/10/08/0BukLT.png)
---
- 下载Python
打开Python的官网：[https://www.python.org/](https://www.python.org/)
点击最新版本的Python，下载
![](https://s1.ax1x.com/2020/10/08/0BuVwF.md.png)
记得把这两个选项都勾上
![Python安装页面](https://s1.ax1x.com/2020/10/08/0BunY9.png)
点击安装
![安装](https://s1.ax1x.com/2020/10/08/0Bu1OK.png)
![安装成功页面](https://s1.ax1x.com/2020/10/08/0BuGwD.png)
win+R输入cmd，打开命令行，输入“python”,验证是否安装了Python，并已配置了Python的环境变量。
如出现以下提示信息，则表明已经成功安装了Python解释器了。
![Python](https://s1.ax1x.com/2020/10/08/0Bu06P.png)
试下输入“ print("hello world") ”吧~
![](https://s1.ax1x.com/2020/10/08/0BuyTg.png)
---
至此，Python程序的运行环境已经基本搭建完成了，下一节我们将介绍如何使用Pycharm搭建工程，并编写一个“Hello World”程序。