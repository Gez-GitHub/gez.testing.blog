---
title: "【MySQL】02-数据库的基本内容"
date: 2022-04-01T12:24:46+08:00
draft: false
author: ""
description: "MySQL"
images: []

tags: ["MySQL","字段属性","数据库引擎","数据库基本命令"]
categories: ["TP311 程序设计、软件工程"]

hiddenFromHomePage: false
hiddenFromSearch: false
ruby: true
fraction: true
fontawesome: true
linkToMarkdown: true
rssFullText: false

---

## 一、连接数据库

命令行连接数据库

```shell
mysql -u root -p 
```

---

## 二、列类型

**数值：**

|关键字|占位|备注|
| ------------| -------| ----------------------------------|
|tinyint|1字节||
|smallint<br />|2字节||
|mediumint|3字节||
|int|4字节||
|bigint|8字节||
|float|4字节||
|double|8字节||
|decimal||字符串形式的浮点数，一般金融计算|

**字符：**

|关键字|大小|备注|
| ----------| ----------| ----------------|
|char|0～255|字符串固定大小|
|varchar|0～65535|可变字符串|
|tinytext|2^8 - 1|微型文本|
|text|2^16 - 1|文本串|

**时间日期：**

|关键字|格式|备注|
| -----------| ------------------------| ------------------|
|date|YYYY-MM-DD|日期格式|
|time|HH:mm:ss|时间格式|
|datetime|YYYY-MM-DD HH:mm:ss|最常用的时间格式|
|timestamp|1970.1.1到现在的毫秒数|时间戳|
|year||年份表示|

**null：**

没有值，未知。不要使用NULL进行运算，结果为NULL。

---

## 三、数据库的字段属性

**Unsigned：**

* 无符号的整数
* 声明了该列不能声明为负数

**ZeroFill：**

* 0填充
* 不足的位数，使用0来填充
* 例：int(3)，5——005

**Auto Increment：**

* 自增，自动在上一条记录的基础上+1（默认）
* 通常用来设计唯一的主键，必须是整数类型
* 可自定义自增的起始值和步长

**Not NULL：**

* 非空，不允许为空

**Default：**

* 设置默认值

**扩展：**

```sql
/*每一个表都必须存在以下5个字段，表示一个记录存在意义
id         主键
`version`  乐观锁
is_delete  伪删除
gmt_create 创建时间
gmt_update 修改时间
*/
```

---

## 四、数据库引擎

|<br />|MYISAM|INNODB|
| --------------| ----------------| -----------------------|
|事务支持|不支持|支持|
|数据行锁定|不支持（表锁）|支持|
|外键约束|不支持|支持|
|全文索引|支持|不支持|
|表空间的大小|较小|较大，约为MYISAM的2倍|

常规使用操作：

* MYISAM：节约空间，速度较快
* INNODB：安全性高，事务的处理，多表多用户操作

---

## 五、数据库基本命令

修改用户密码

```sql
update mysql.user set authentication_string=password('123456') where user='root' and Host='localhost';
```

刷新权限

```sql
flush privilegs;
```

查看所有数据库

```sql
show databases;
```

使用数据库

```sql
use `数据库名`
```

查看数据库中所有的表

```sql
show tables;
```

查看表结构

```sql
desc 表名;
```

退出连接

```sql
exit
```

注释

```sql
-- 单行注释

/*
多行注释
*/
```

查看创建数据库的语句

```sql
show create database 数据库名;
```

查看创建数据表的语句

```sql
show create table 数据表名;
```
