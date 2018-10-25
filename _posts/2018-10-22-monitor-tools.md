---
layout: post
title: Monitor Tools
date: 2018-10-22
author: Jianzhu Guo
color: rgb(91,111,190)
cover: '/assets/pics/tools.jpg'
---

<!-- todo: links, nvtop, gpustat, GPUtil -->

日常工作中需要经常对笔记本、PC、服务器等进行状态监控，最基本的无外乎 CPU、GPU、磁盘、内存、 IO、网络状况等，简单划分就是计算资源，存储资源和 IO。本博客会记录一些我认为比较实用的一些工具。
也许日常工作中，有人只需要其中的一部分就足够了，但作为优秀的开源作品，我认为还是有必要记录一下的。

# 计算

## top & htop & glances
`top` 在 Linux、macOS 一般是自带的，属于标准版；`htop` 需要编译安装或者包管理器安装，属于高配版，相比于 `top` 支持彩色输出，鼠标操作、能够查看进程对应的命令，排版更加友好等；[`Glances`](https://github.com/nicolargo/glances) 自称 `An eye on your system`， 相当于旗舰版，能查看 CPU，GPU，磁盘，IO 等，且能够挤在一个窗口中显示，亦支持 client/server 模式，可以在本地机器上查看服务器的状态。下面依次是这三个工具的截图。

**top**
![top](/assets/pics/monitor-tools/top.png)

**htop**
![htop](/assets/pics/monitor-tools/htop.png)

**glances**
![glances](/assets/pics/monitor-tools/glances.png)

## nvidia-smi & gpustat & nvtop
[nvidia-smi](https://developer.nvidia.com/nvidia-system-management-interface) (NVIDIA System Management Interface) 是 nvidia driver 安装后自带的工具，是基于 [NVML](https://developer.nvidia.com/nvidia-management-library-nvml) (NVIDIA Management Library) 写的。关于 NVML：
> A C-based API for monitoring and managing various states of the NVIDIA GPU devices. It provides a direct access to the queries and commands exposed via nvidia-smi.

**nvidia-smi**
![nvidia-smi](/assets/pics/monitor-tools/nvidia-smi.png)

[gpustat](https://github.com/wookayin/gpustat) 是基于 pynvml 写的，支持更简洁的，带颜色的输出。持续监测可以用 watch 命令，`-n` 选项表示刷新时间。`-cup` 显示程序命令、用户名、进程 ID，这个单词很好记 : )
```
watch --color -n1 gpustat -cup
```

**gpustat**
![gpustat](/assets/pics/monitor-tools/gpustat.png)


[nvtop](https://github.com/Syllo/nvtop) 也是基于 NVML 写的，提供了类似 htop 的风格。

**nvtop**
![nvtop](/assets/pics/monitor-tools/nvtop.png)


# IO

## nmon & iotop
**计算** 篇中提到的 `glances` 可以监测 IO，此外推荐 [nmon](http://nmon.sourceforge.net/pmwiki.php)。进入 `nmon` 后，按键 c 即进入 cpu 监测模式，d 指硬盘，m 是内存，更多用法参考[主页](http://nmon.sourceforge.net/pmwiki.php)。`iotop` 是一个类 `top` 的工具，显示了用户、进程占用的磁盘 IO 信息。

**nmon**
![nmon](/assets/pics/monitor-tools/nmon.png)
