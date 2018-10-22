---
layout: post
title: Monitor Tools
date: 2018-10-22
author: Jianzhu Guo
color: rgb(91,111,190)
cover: '/assets/pics/tools.jpg'
---

日常工作中需要经常对笔记本、PC、服务器等进行状态监控，最基本的无外乎 CPU、GPU、磁盘、内存、 IO、网络状况等，简单划分就是计算资源，存储资源和 IO。本博客会记录一些我认为比较实用的一些工具。

## top & htop & glances
`top` 在 Linux、macOS 一般是自带的，属于标准版；`htop` 需要编译安装或者包管理器安装，属于高配版，相比于 `top` 支持彩色输出，鼠标操作、能够查看进程对应的命令，排版更加友好等；`glances` 自称 `An eye on your system`， 相当于旗舰版，能查看 CPU，GPU，磁盘，IO 等，且能够挤在一个窗口中显示，亦支持 client/server 模式，可以在本地机器上查看服务器的状态。

![top](/assets/pics/monitor-tools/top.png)
![htop](/assets/pics/monitor-tools/htop.png)
![glances](/assets/pics/monitor-tools/glances.png)
