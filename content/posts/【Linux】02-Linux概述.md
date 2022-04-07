---
title: "【Linux】02-Linux概述"
date: 2022-04-01T12:26:49+08:00
draft: false
author: ""
description: "Linux"
images: []

tags: ["Linux","Linux目录结构","Linux关机命令","Linux发行版本"]
categories: ["TP316 操作系统"]

hiddenFromHomePage: false
hiddenFromSearch: false
ruby: true
fraction: true
fontawesome: true
linkToMarkdown: true
rssFullText: false

---

## 一、Linux简介

Linux，全称GNU/Linux，是一种免费使用和自由传播的类Unix操作系统，其内核由林纳斯·本纳第克特·托瓦兹于1991年10月5日首次发布。

Linux主要受到Minix和Unix思想的启发，是一个基于POSIX的多用户、多任务、支持多线程和多CPU的操作系统。

Linux能运行主要的Unix工具软件、应用程序和网络协议，支持32位和64位硬件。Linux继承了Unix以网络为核心的设计思想，是一个性能稳定的多用户网络操作系统。

---

## 二、发行版本

Linux 遵循 GNU 通用公共许可证（GPL），任何个人和机构都可以自由地使用 Linux 的所有底层源代码，也可以自由地修改和再发布。

由于 Linux 是自由软件，任何人都可以创建一个符合自己需求的 Linux 发行版。

目前主流的 Linux 版本有：

* Debian

  * Ubuntu
  * Linux Mint
* Fedora

  * Red Hat Enterprise Linux
  * Oracle Linux
  * CentOS
* SUSE

  * SLES
  * openSUSE
* 其他发行版本

---

## 三、关机命令

```bash
# 关机
shutdown 
# 10分钟后关机
shutdown -h 10
# 立刻关机 
shutdown -h now
# 将在今天17:51关机 
shutdown -h 17:51
# 立刻重启 
shutdown -r now
# 10分钟后重启  
shutdown -r 10
# 重启系统 等同于shutdown -r now 
reboot
# 关闭系统 等同于shutdown -h now 或 poweroff 
halt 
```

---

## 四、系统目录结构

Linux中一切皆文件。

根目录 / ，所有文件都在根目录下。

```bash
ls /
```

![image.png](/assets/linux_gs01.png)

**目录解释：**

* /bin：bin（Binary），存放最经常使用的命令。
* /boot：存放的是启动Linux时使用的一些核心文件，包括一些连接文件以及镜像文件。（不要动）
* /dev：dev（Device 设备），存放的是Linux的外部设备，在Linux中访问设备和访问文件的方式是相同的，
* **/etc：存放所有的系统管理所需要的配置文件和子目录。**
* **/home：用户的主目录，在Linux中，每个用户都有一个自己的目录，一般该目录名是以用户的账号命名的。**
* /lib：存放系统最基本的动态连接共享库，其作用类似于Windows里的DLL文件。（不要动）
* /media：挂载自动设别的设备，如U盘、光驱等。
* /mnt：临时挂载别的文件系统。
* **/opt：存放额外安装软件。**
* /proc：虚拟目录，存放系统内存的映射。（不用管）
* **/root：系统管理员的用户主目录。**
* /run：临时文件系统，存放系统启动以来的信息，当系统重启时，该目录下的文件将被清除。
* /sbin：s（Super User），存放的是系统管理员使用的系统管理程序。
* /srv：存放一些服务启动之后需要提取的数据。
* /sys：存放2.6内核中新出现的文件系统sysfs。
* **/tmp：存放临时文件。用完即丢的文件可以存放在该目录下。**
* **/usr：存放用户的应用程序和文件，类似于Windows下的Program Files目录。**
* /usr/bin：系统用户使用的应用程序。
* /usr/sbin：超级用户使用的比较高级的管理程序和系统守护程序。
* /usr/src：内核源码默认的存放目录。
* **/var：存放着不断扩充的东西，习惯将经常被修改的目录放在这个目录下，包括各种日志文件。**
