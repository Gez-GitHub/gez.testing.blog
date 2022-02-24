---
title: "Web前端基础知识"
date: 2022-02-04T14:50:58+08:00
lastmod: 2022-02-04T14:50:58+08:00
draft: false
author: ""
description: "HTML基础知识"
images: []

tags: ["TP393.0 一般性问题","Web"]
categories: ["TP393 计算机网络"]

hiddenFromHomePage: false
hiddenFromSearch: false
ruby: true
fraction: true
fontawesome: true
linkToMarkdown: true
rssFullText: false

---
Web前端基础知识，html基础语法规则、css基础语法规则等。
<!--more-->
## 1 Web前端标准

html：结构标准，负责网页结构的搭建。

css：样式标准/表现标准：负责网页的美化工作。

js：行为标准，负责网页的行为动作。

---

## 2 行业词条

1. internet：互联网
2. www：万维网（World Wide Web）
3. URL：统一资源定位符
4. HTTP：超文本传输协议
5. W3C：万维网联盟
6. 网站：多个网页的集合
7. 网页：网页问价就是后缀名以 .htm或者 .html结尾的文件。
8. 浏览器：浏览网页的平台

    1. IE（Internet Explore）
    2. 谷歌浏览器（google chrome）
    3. 火狐浏览器（Firefox）
    4. 苹果浏览器（Safari）
    5. 欧朋浏览器（Opera）

---

## 3 HTML

定义：超文本标记语言

HTML的发展历史：

* HTML：1991
* HTML +：1993
* HTML 2.0：1995
* HTML 3.2：1997
* HTML 4.0.1：1999
* XHTML 1.0：2000
* HTML 5：2012
* XHTML 5：2013

### 3.1 HTML语法规则

```html
<!DOCTYPE html> <!-- 声明HTML版本，默认HTML5 -->
<html> <!-- HTML页面的根元素 -->
<head> <!-- 头部元素 -->
	<meta charset="UTF-8"> <!-- 定义网页编码 -->
	<title>网页标题</title> <!-- 文档标题 -->
</head>
<body> <!-- 包含可见的页面内容 -->
	<h1>1级标题</h1>
	<h2>2级标题</h2>
	<h3>3级标题</h3>
	<p>段落</p>
	<a href="http://www.baidu.com">链接</a>
	<a href="http://www.baidu.com" target="_blank">新窗口打开链接</a>
	<a href="###">空链接</a>
	<a href="javascript:void(0);">空链接</a>
	<p id="md">目标段落</p>
	<a href="#md">锚点链接</a>
	<b>加粗</b>
	<strong>加粗 强调语义</strong>
	<u>下划线</u>
	<br> <!-- 换行 -->
	<hr> <!-- 水平线 -->
	<i>斜体</i>
	<em>斜体 强调语义</em>
	<s>删除线 - 已淘汰</s>
	<del>删除线 强调语义</del> 
	<small>小号字</small>
	<sub>下标字</sub>
	<sup>上标字</sup>
	<img str="*.jpg" /> <!-- 原图 -->
	<img str="*.jpg" width="200" height="100" /> <!-- 设置宽高的图片 -->
	<img str="*.jpg" width="100" /> <!-- 等比例缩放图片,只设置宽度或高度 -->
	<img str="*.jpg" title="图片提示文字" /> <!-- 鼠标悬停有提示文本的图片 -->
	<img str="*.jpg" alt="图片加载失败提示文字" /> <!-- 图片加载失败时的提示文字 -->
</body>
</html>
```

### 3.2 HTML表单

HTML 表单用于收集不同类型的用户输入。

```html
<form name="input" action="html_form_action.php" method="get">
	<!-- 文本域 -->
	First name: <input type="text" name="firstname"><br>
	Last name: <input type="text" name="lastname">
	<!-- 带提示的文本域 -->
	昵称: <input type="text" name="name" placeholder="请输入昵称">

	<!-- 多行文本域 -->
	<textarea rows="10" cols="30" placeholder="请输入文字">
		我是一个文本框。
	</textarea>

	<!-- 密码字段 -->
	Password: <input type="password" name="pwd">

	<!-- 单选按钮 -->
	<input type="radio" name="sex" value="male">Male<br>
	<input type="radio" name="sex" value="female">Female
	<!-- 点击文字也可选择单选按钮 -->
	<input type="radio" name="sex" value="male" id="male"><lable for="male">Male</lable><br>
	<input type="radio" name="sex" value="female" id="female"><lable for="female">Female</lable>
	<!-- 带预选的单选按钮 -->
	<input type="radio" name="sex" value="male" checked="checked">Male<br>
	<input type="radio" name="sex" value="female">Female

	<!-- 复选框 -->
	<input type="checkbox" name="vehicle" value="Bike">I have a bike<br>
	<input type="checkbox" name="vehicle" value="Car">I have a car

	<!-- 提交按钮 -->
	<input type="submit" value="Submit">

	<!-- 下拉列表 -->
	<select name="cars">
		<option value="volvo">Volvo</option>
		<option value="saab">Saab</option>
		<option value="fiat">Fiat</option>
		<option value="audi">Audi</option>
	</select>
	<!-- 预选下拉列表 -->
	<select name="cars">
		<option value="volvo">Volvo</option>
		<option value="saab">Saab</option>
		<option value="fiat" selected="selected">Fiat</option>
		<option value="audi">Audi</option>
	</select>
	<!-- 带分组的下拉列表 -->
	<select>
		<optgroup label="Swedish Cars">
			<option value="volvo">Volvo</option>
			<option value="saab">Saab</option>
		</optgroup>
		<optgroup label="German Cars">
			<option value="mercedes">Mercedes</option>
			<option value="audi">Audi</option>
		</optgroup>
	</select>
</form>
```

### 3.3 分组标签

```html
<body>
	<!-- div定义了文档的区域，块级 (block-level) -->
	<div style="color:#0000FF">
		<h3>这是一个在 div 元素中的标题。</h3>
		<p>这是一个在 div 元素中的文本。</p>
	</div>
	<!-- span用来组合文档中的行内元素， 内联元素(inline) -->
	<p>我的母亲有 
	<span style="color:blue">蓝色</span> 
	的眼睛。</p>
</body>
```

---

## 4 CSS

CSS（Cascading Style Sheets）

CSS通常称为CSS样式表或层叠样式表（级联样式表），主要用于设置HTML页面中的文本内容（字体、大小、对齐方式等）、图片的外形（宽高、边框样式、边距等）以及版面的布局等外观显示样式。

CSS以HTML为基础，提供了丰富的功能，如字体、颜色、背景的控制及整体排版等，而且还可以针对不同的浏览器设置不同的样式。

### 4.1 CSS基本语法

书写位置：head标签内部

环境：`<style type="text/css"></style>`

书写css属性：控制的对象（css键值对）

css键值对语法：k:v;

### 4.2 CSS常用文字控制属性

字体：font-family

字号：font-size

颜色：color

内容水平对齐方式：text-align:left ｜ center ｜ right

首行缩进：text-indent

文字粗细：font-weight:normal | bold

文字倾斜：font-style:normal | italic

文字修饰属性：text-decoration:underline下划线 | overline上划线 | line-through删除线 | none

强制字母换行：word-break:break-all

首行缩进：text-indent:2em

行高：line-height

盒子模型：border: 1px solid实线 | dashed虚线 red

* 顶部边框线：border-top
* 右侧边框线：border-right
* 底部边框线：boeder-bottom
* 左侧边框线：border-left

```html
<head>
	<style type="text/css">
		body {background-color:yellow;}
		p {color:blue; font-size:30px;}
	</style>
</head>
```

### 4.3 实体化三属性

宽度：width

高度：height

背景色：backgroun

```html
<head>
	<style type="text/css">
	p {width:30px; height:40px; background:pink; color:blue; font-size:30px;}
	</style>
</head>
```

### 4.4 选择器

标签选择器：`div`

id选择器：`#id` 不可重复

class选择器：`.class` 可复用

选择器权重：class选择器>id选择器>标签选择器

```html
<head>
	<style type="text/css">
	<!-- 标签选择器 -->
	p {font-size:30px;}
	<!-- id选择器 -->
	#p2 {color:red;}
	<!-- class选择器 -->
	.p3 {color:black;}
	<!-- class选择器 可有多个类名 -->
	.p4 {background:pink;}
	</style>
</head>
<body>
	<p>111111</p>
	<p id="p2">22222222</p>
	<p class="p3">3333333333</p>
	<p class="p3 p4">444444444444</p>
</body>
```

### 4.5 CSS引入方式

内部样式表

优点：加载速度快

缺点：html和css代码未分离，不方便修改

```html
<head>
	<style type="text/css">
		body {background-color:yellow;}
		p {color:blue;}
	</style>
</head>
```

外部样式表

优点：实现html和css代码的分离，方便修改和管理

缺点：加载速度慢

```html
<head>
	<link rel="stylesheet" type="text/css" href="mystyle.css">
</head>
```

## 5 HTML5新标签

HTML5中的新标签，ie低版本不识别

```html
<body>
	<header>头部</header>
	<nav>导航条</nav>
	<aisde>侧导航</aside>
	<article>文章块</aeticle>
	<footer>底部</footer>
</body>
```

