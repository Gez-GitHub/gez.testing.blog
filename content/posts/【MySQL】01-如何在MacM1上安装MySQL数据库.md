---
title: "【MySQL】01-如何在MacM1上安装MySQL数据库"
date: 2022-04-01T12:24:23+08:00
draft: false
author: ""
description: "MySQL"
images: []

tags: ["MySQL","安装MySQL8.0","M1芯片"]
categories: ["TP311 程序设计、软件工程"]

hiddenFromHomePage: false
hiddenFromSearch: false
ruby: true
fraction: true
fontawesome: true
linkToMarkdown: true
rssFullText: false

---

## 一、下载MySQL8.0社区版

[MySQL下载地址](https://dev.mysql.com/downloads/mysql/)，由于 M1 系列芯片都是使用 ARM 架构的指令集，所以要选择ARM架构的安装包，下载自己需要的版本，建议下载dmg安装包，安装方便。提一句MySQL版本与jdk版本和驱动包还有一定关系，注意选择合适的版本。

![image01.png](/assets/mysql_az01.png)

![image02.png](/assets/mysql_az02.png)

---

## 二、安装MySQL8.0

双击 mysql-8.0.28-macos11-arm64.dmg 文件，加载镜像。

双击 mysql-8.0.28-macos11-arm64.pkg 文件，开始安装。

![image03.png](/assets/mysql_az03.png)

然后就一直无脑下一步就好了。

![image04.png](/assets/mysql_az04.png)
![image05.png](/assets/mysql_az05.png)
![image06.png](/assets/mysql_az06.png)
![image07.png](/assets/mysql_az07.png)

这里输入root用户密码，一定要记住。

![image08.png](/assets/mysql_az08.png)
![image09.png](/assets/mysql_az09.png)

到这里为止就安装完成了。

---

## 三、启动MySQL

打开系统偏好设置，点击MySQL图标，进入MySQL设置页面。

![image10.png](/assets/mysql_az10.png)

一般默认状态是running，如果不是就点击**Start MySQL Server**进行启动。也可以把开机自启动勾选。

![image11.png](/assets/mysql_az11.png)

---

## 四、连接MySQL

先为PATH路径添加MySQL的bin目录，要不然终端无法识别mysql命令。

```shell
PATH="$PATH":/usr/local/mysql/bin
```

然后通过mysql命令登录，这里的密码就是安装时自己设置的密码。

```shell
mysql -u root -p
```

出现下面这个页面就代表MySQL安装成功并且可以使用了。

![image12.png](/assets/mysql_az12.png)
