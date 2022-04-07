---
title: "【Web自动化测试】01-Web自动化入门"
date: 2022-04-01T12:22:08+08:00
draft: false
author: ""
description: "软件测试-Web自动化测试"
images: []

tags: ["软件测试","自动化测试定义","Selenium"]
categories: ["TP311 程序设计、软件工程"]

hiddenFromHomePage: false
hiddenFromSearch: false
ruby: true
fraction: true
fontawesome: true
linkToMarkdown: true
rssFullText: false

---

## 一、什么是自动化？

**概念：** 由机器设备代替人工自动完成指定目标的过程。

**优点：**

* 减少人工劳动力
* 提高工作效率
* 产品规格统一标准
* 规模化（批量生产）

---

## 二、什么是自动化测试？

**概念：** 让程序代替人工去验证系统功能的过程。

**自动化测试能解决的问题：**

1. 回归测试
2. 压力测试
3. 兼容性测试
4. 提高测试效率，保证产品质量

**优点：**

1. 较少的时间内运行更多的测试用例；
2. 自动化脚本可重复运行；
3. 减少人为的错误；
4. 克服手工测试的局限性。

**误区：**

1. 自动化测试可以完全替代手工测试；
2. 自动化测试一定比手工测试厉害；
3. 自动化测试可以发掘更多的BUG；
4. 自动化测试适用于所有功能。

**自动化测试分类**：

1. Web-自动化测试
2. App-自动化测试
3. 接口-自动化测试
4. 单元测试-自动化测试

---

## 三、什么是Web自动化测试？

**概念：** 让程序代替人工自动验证Web项目功能的过程。

**适合做自动化测试的Web项目：**

1. 需求变动不频繁
2. 项目周期长
3. 项目需要回归测试

**Web自动化测试在什么阶段开始：** 功能测试（手工测试之后）。

**Web自动化测试所属分类：** 黑盒测试（功能测试）。

---

## 四、自动化测试工具选择

### 4.1 主流Web自动化测试工具

**QTP：** 是一个商业化的功能测试工具，收费，支持web、桌面自动化测试。win32

**Selenium：** 是一个开源的web自动化测试工具，免费，主要做功能测试。

**Robot Framework：** 是一个基于Python可扩展地关键字驱动的测试自动化框架。（已淘汰）

### 4.2 什么是Selenium？

Selenium是一个用于Web应用程序的自动化测试工具。（硒）

特点：

1. 开源软件：源代码开放可以根据需要来增加工具的某些功能
2. 跨平台：Linux、Windows、MacOS
3. 支持多种浏览器：Firefox、Chrome、IE、Edge、Opera、Safari等
4. 支持多种语言：Python、Java、C# 、JavaScript、Ruby、PHP等
5. 成熟稳定：目前已经被google、百度、腾讯等公司广泛使用
6. 功能强大：能够实现类似商业工具的大部分功能，因为开源性，可实现定制化功能

### 4.3 Selenium发展史

**Selenium 1.0：**

* Selenium IDE：

  * 是嵌入到Firefox 浏览器中的一个插件，实现简单的浏览器操作的录制与回放功能。
  * IDE 录制的脚本可以可以转换成多种语言。
* Selenium Grid：

  * 支持分布式测试，即可以在不同平台、不同浏览器的多台远程机器上同时运行Selenium测试脚本。
  * 利用Grid，可以很方便地同时在多台机器上和异构环境中并行运行多个测试事例。
  * 其特点为：并行执行；通过一个主机统一控制用例在不同环境、不同浏览器下运行；灵活添加变动测试机。
* Selenium RC（Remote Control）：

  * Selenium RC是一个用JAVA语言编写的服务端，可以处理测试脚本发送过来的HTTP请求，来操作浏览器。
  * 是Selenium 家族的核心工具，Selenium RC 支持多种不同的语言编写自动化测试脚本，通过Selenium RC 的服务器作为代理服务器去访问应用从而达到测试的目的。
  * Selenium RC 使用分Client Libraries 和Selenium Server。

    * Client Libraries 库主要主要用于编写测试脚本，用来控制Selenium Server 的库。
    * Selenium Server 负责控制浏览器行为，总的来说，Selenium Server 主要包括3 个部分：Launcher、Http Proxy、Core。
* Selenium Core：

  * 是被Selenium Server 嵌入到浏览器页面中的。Selenium Core就是一堆JavaScript函数的集合。
* Launcher：

  * 用于启动浏览器，把Selenium Core 加载到浏览器页面当中，并把浏览器的代理设置为Selenium Server 的Http Proxy。
* 缺陷：

  * 不支持本机键盘和鼠标事件
  * 不支持同源策略XSS/HTTP(S)
  * 不支持弹出框，对话框（基本身份证，自签名的证书和文件上传、下载）

**Selenium 2.0：**

* Selenium2.0 = Selenium1.0 + WebDriver
* 基于调用Webdriver API来模拟用户操作
* WebDriver的速度更快，因为它直接交互使用
* 支持更多编程语言

**Selenium 3.0：**

* 去掉了对Selenium RC的支持
* 全面拥抱Java8
* 支持MacOS（Sierra or later），支持官方的SafariDriver
* 通过MS官方的WebDriver支持Edge浏览器
* 支持IE9.0版本以上
* 通过Mozilla官方的GeckoDriver来支持Firefox

---

## 五、环境搭建

基于Python环境搭建（由于自己的电脑是Mac所以通过虚拟机进行Windows行下的环境搭建，更符合生产环境）

1. Python开发环境
2. 安装Selenium包
3. 安装浏览器
4. 安装浏览器驱动

### 5.1 安装Selenium包

**前置条件：** Python3安装完毕且正常运行

**PIP工具：** 是一个通用的Pyhton包管理工具，提供了对Python包的查找、下载、安装、卸载的功能。

```shell
# 安装 selenium
pip install selenium	
# 查看安装的 selenium 的版本
pip show selenium	
# 卸载 selenium
pip uninstall selenium	
# 安装指定版本 selenium
pip install selenium==2.48.0	
```

### 5.2 安装浏览器驱动

##### 火狐浏览器

1. Firefox 48 以上版本

    selenium 3.x + Firefox驱动（geckodriver）
2. Firefox 48 以下版本

    selenium 2.x + 内置驱动

##### 谷歌浏览器

selenium 2.x/3.x + Chrome驱动（chromedriver）

根据自己浏览器的版本进行驱动下载，下载地址：http://npm.taobao.org/mirrors/chromedriver/

![image01.png](/assets/webtest_rm01.png)

![image02.png](/assets/webtest_rm02.png)

![image03.png](/assets/webtest_rm03.png)

下载完成解压放到浏览器的安装目录下：`C:\Program Files (x86)\Google\Chrome\Application` （根据自己的实际安装目录）

##### 配置环境变量

此电脑→右击属性→高级系统设置→环境变量→ 系统变量 →Path→编辑→新建

将安装目录放进去：`C:\Program Files (x86)\Google\Chrome\Application\`

---

## 六、第一个案例

安装PyCharm和Python环境，输入如下代码

```python
from time import sleep
# 导入webdriver包
from selenium import webdriver

# 获取谷歌浏览器对象
driver = webdriver.Chrome()

# 打开百度
driver.get("https://www.baidu.com")

# 暂停3秒
sleep(3)

# 关闭浏览器
driver.quit()
```

![image04.png](/assets/webtest_rm04.png)
