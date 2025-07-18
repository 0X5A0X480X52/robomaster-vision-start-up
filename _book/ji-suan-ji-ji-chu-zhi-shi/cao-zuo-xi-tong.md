---
icon: computer
---

# 操作系统

操作系统是管理计算机硬件与软件资源的系统软件，是计算机系统的核心，其核心功能包括进程管理（调度进程运行、处理进程同步与通信）、内存管理（分配与回收内存空间、实现虚拟内存）、文件系统管理（组织和存储文件）、设备管理（协调硬件设备与软件交互）等。在 RoboMaster 视觉组工作中，操作系统影响着视觉算法的运行效率，比如 Linux 系统的进程调度机制会影响多线程视觉任务的响应速度，内存管理则关系到图像数据的高效处理。​开源学习资源方面，推荐 “Operating System Concepts” 开源电子书（可在 GitHub 找到相关资源），系统讲解操作系统原理；MIT 的 “6.828 Operating System Engineering” 课程开源资料（包含讲义、实验），能通过实践深入理解；还有 Linux 内核源码（[https://github.com/](https://github.com/torvalds/linux)[torva](https://github.com/torvalds/linux)[lds/](https://github.com/torvalds/linux)[linux](https://github.com/torvalds/linux)），适合进阶学习操作系统底层实现。​

## Linux

感兴趣的可以详细了解操作系统的原理与细节，robomaster比赛中并不经常与底层打交道，但视觉组的大部分程序是运行在linux系统上的，因此有必要熟练使用linux系统。

以下是使用linux

* 直接使用安装linux的操作系统的机器（不推荐将自己主力电脑换成Linux系统，实际机器人上使用的是linux系统）
* 虚拟机（开发时推荐）：可参考博客 [https://blog.csdn.net/weixin\_74195551/article/details/127288338](https://blog.csdn.net/weixin_74195551/article/details/127288338)
* wsl2（开发时推荐）：可参考博客 [https://blog.csdn.net/weixin\_44301630/article/details/122390018](https://blog.csdn.net/weixin_44301630/article/details/122390018)
* docker（开发时推荐）：可参考博客 [https://www.runoob.com/docker/docker-tutorial.html](https://www.runoob.com/docker/docker-tutorial.html)

Linux的使用可参考博客 [https://www.runoob.com/linux/linux-tutorial.html](https://www.runoob.com/linux/linux-tutorial.html) ，或ubuntu的man手册等官方文档

