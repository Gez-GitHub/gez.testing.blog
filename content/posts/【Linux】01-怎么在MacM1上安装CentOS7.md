---
title: "【Linux】01-怎么在MacM1上安装CentOS7"
date: 2022-04-01T12:26:16+08:00
draft: false
author: ""
description: "Linux"
images: []

tags: ["Linux","Parallels Desktop","CentOS 7","M1芯片","测试模型","测试对象"]
categories: ["TP316 操作系统"]

hiddenFromHomePage: false
hiddenFromSearch: false
ruby: true
fraction: true
fontawesome: true
linkToMarkdown: true
rssFullText: false

---

由于 M1 系列芯片都是使用 ARM 架构的指令集，因此传统的 x86 架构的 Linux 系统是无法使用的。试了很多版本的都会卡在配置界面，找到了一个能用的系统包，下面是安装过程。

**本教程所使用 Mac 配置详情如下：**

* MacBook Pro（14英寸，2021年）
* 16 GB 内存
* 512 GB 存储内存
* macOS Monterey 12.2.1
* Parallels Desktop 17 for Mac (试用版 V17.1.1[51537])

---

## 一、创建虚拟机

![image01.png](/assets/linux_centos01.png)

在 Mac 上打开 PD17，跳过安装Win11。

![image02.png](/assets/linux_centos02.png)

这时安装助手将会被打开，选择【安装Windows或其他操作系统（从 DVD 或镜像文件）】，然后点击【继续】进入下一步。

![image03.png](/assets/linux_centos03.png)

一般会进行自动扫描，如果没有就将下好的ISO镜像文件，拖拽到安装助手上，成功识别后，点击【继续】进入下一步。

下载地址：链接: https://pan.baidu.com/s/1exFPj9ACw9ARr48o3fye2g 提取码: btpd

![image04.png](/assets/linux_centos04.png)

填写名称，选择保存位置。

![image05.png](/assets/linux_centos05.png)

等待创建。

![image06.png](/assets/linux_centos06.png)

---

## 二、安装CentOS 7

选择`Install CentOS 7` 选项

![image07.png](/assets/linux_centos07.png)

进来之后会显示如下界面，这个是因为PD没有成功启动Xstarup的问题，需要通过手动文字字符界面进行安装。

![image08.png](/assets/linux_centos08.png)

第一次输入`r` ，还剩下`5)Installation Destination` 磁盘位置 、`8)Root password`Root用户密码 、`9)User creation` 用户创建，三个配置是感叹号，下面一一配置。

![image09.png](/assets/linux_centos09.png)

### 2.1 磁盘配置

`5)Installation Destination` 磁盘选择，先选数字`5`再依次输入`c` 、`c` 、`c`，完成磁盘的选择。

![image10.png](/assets/linux_centos10.png)

### 2.2 Root用户密码配置

`8)Root password`Root用户密码，先选数字`8`，然后输入root用户的登录密码，可能会提示密码太简单是否确认使用，直接输入`yes` 就好了，这样Root用户密码配置就完成了。

![image11.png](/assets/linux_centos11.png)

### 2.3 完成安装

配置完root用户之后，`9)User creation`的感叹号会消失，这个时候输入`b` ，出现`Installation complete`就代表配置成功安装完成了。

![image12.png](/assets/linux_centos12.png)
![image13.png](/assets/linux_centos13.png)

---

## 三、验证并安装Net-Tools工具

### 3.1 验证CentOS 7

输入用户密码进行登录，验证CentOS 7。

* `cat /etc/redhat-release`：查看CentOS版本
* `uname -a`：显示电脑以及操作系统的全部信息

![image14.png](/assets/linux_centos14.png)

### 3.2 安装Net-Tools工具

当前安装的系统是没有Net-Tools工具的，Net-Tools是一个Linux系统中基本的网络工具集，其集成了常用的网络管理命令“ifconfig、netstat、arp、route等”。

![image15.png](/assets/linux_centos15.png)

安装Net-Tools

```bash
yum search ifconfig
```

![image16.png](/assets/linux_centos16.png)

```bash
yum install net-tools.aarch64
```

![image17.png](/assets/linux_centos17.png)

通过`ifconfig`命令验证Net-Tools是否安装成功。

![image18.png](/assets/linux_centos18.png)
