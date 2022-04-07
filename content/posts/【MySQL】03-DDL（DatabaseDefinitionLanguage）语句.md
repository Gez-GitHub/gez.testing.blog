---
title: "【MySQL】03-DDL（DatabaseDefinitionLanguage）语句"
date: 2022-04-01T12:25:20+08:00
draft: false
author: ""
description: "MySQL"
images: []

tags: ["MySQL","DDL数据库定义语言"]
categories: ["TP311 程序设计、软件工程"]

hiddenFromHomePage: false
hiddenFromSearch: false
ruby: true
fraction: true
fontawesome: true
linkToMarkdown: true
rssFullText: false

---

DDL（Database Definition Language）数据库定义语言。

## 一、数据库相关

**创建数据库**

语法：`create database [if not exists] 数据库名;`

```sql
create database `school`;
```

**删除数据库**

语法：`drop database [if exists] 数据库名;`

```sql
drop database `school`;
```

---

## 二、数据表相关

**创建数据表**

语法：`create table 表名(字段1 字段属性 字段约束 字段备注,字段2 字段属性 字段约束 字段备注,……) 引擎 默认编码`

```sql
CREATE TABLE `school`.`student` (
  `id` INT NOT NULL AUTO_INCREMENT COMMENT '学员id',
  `name` VARCHAR(100) NOT NULL COMMENT '学员姓名',
  `age` INT NOT NULL COMMENT '学员年龄',
  PRIMARY KEY (`id`),
  UNIQUE INDEX `id_UNIQUE` (`id` ASC) VISIBLE)
ENGINE = InnoDB
DEFAULT CHARACTER SET = utf8
```

**增加数据表字段**

语法：`alter table 数据表名 add 字段名 列属性;`

```sql
alter table people add sex VARCHAR(4)
```

**修改数据表名**

语法：`alter table 旧表名 rename as 新表名;`

```sql
alter table student rename as people
```

**修改数据表字段（修改约束）**

语法：`alter table 数据表名 modify 字段名 列属性;`

```sql
alter table people modify sex VARCHAR(2)
```

**修改数据表字段（重命名）**

语法：`alter table 数据表名 change 旧字段名 新字段名;`

```sql
alter table people change name pname;
```

**删除数据表字段**

语法：`alter table 数据表名 drop 字段名;`

```sql
alter table people drop sex
```

**删除数据表**

语法：`drop table [if exists] 数据表名;`

```sql
drop table `people`;
```
