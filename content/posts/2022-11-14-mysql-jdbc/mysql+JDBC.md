---
title: Mysql+JDBC
author: ma
date: '2022-11-14'
slug: mysql+JDBC
categories: []
tags:
  - 大数据
layout: post
math: no
---

#                      大数据学习之SQL+JDBC总结

1. ### MySql字段类型

   - 常用的有：数值（int float ）,字符串(varchar,text),日期（date,datetime）.

2. ### MySql约束

   - 主键：primary  key
   - 外键：foreign key
   - 默认值：default
   - 唯一：unique
   - 非空： not null

3. ### 物理删除和逻辑删除

   - 物理删除就是把一条数据从数据库中永久的删除，不能在找到也不能在恢复。
   - 逻辑删除就是在设计的表中添加一列（例如：isdelete，设置默认值为0），当你想删除数据将这个字段设置为1，当在进行数据库操作时筛选数据即可。这样数据也不会丢失。

4. ### 数据库的基本操作（增删改查）

   - 创建数据库：

     CERATE DATABASE [IF NOT EXISTS]  dbname [CHARACTER SET utf8];

   - 查看数据库：

     SHOW DATABASES;

   - 查看数据库创建方式：

     SHOW CREATE DATABASES dbname;

   - 修改数据库编码方式

     ALTER DATABASE db_name [character set utf8]

   - 删除数据库

     DROP DATABASE [IF EXISTS]db_name;

   - 使用数据库

     USE db_name;

   - 查看当前使用数据库

     SELECT DADABASE();

5. ### 数据库管理

   - 通过grant命令，给test数据库，添加用户***，密码123456

     grant select,insert,updata,delete,create,drop on test to '***'@ 'localhost' identified by 'asdfasdf';

   - 修改用户密码

     grant select,insert,update,delete,create,drop on test to '***' @'localhost' identifiled 'asdfasdf';

   - 显示用户

     select user from mysql.user;

   - 删除用户

     drop user '***' @ 'localhost'

   

6. 数据表的基本操作

   - 查看数据库

     SHOW TABLES;

   - 创建数据表

     CERATE TABLE [IF NOT EXISTS] TABLE_NAME(

     字段名 数据类型，

     ....

     );

   - 查看表结构

     DESCRIBE TABLE_NAME;

   - 查看创建数据表语句

     SHOW CREATE TABLE TABLE_NAME;

   - 增加数据（列，字段）

     ALTER TABLE TABLE_NAME ADD 字段名 数据类型。

   - 增加多个字段

     ALTER TABLE TABLE_NAME ADD 字段名 数据类型，ADD 字段名 数据类型 约束等；

   - 修改列名

     ALTER TABLE TABLE_ANME CHANGE 字段名 新字段名 数据类型；

   - 修改一列类型

     ALTER TABLE TABLE_NAME MODIFY 字段名 新数据类型；

   - 删除一类

     ALTER TABLE TABLE_NAME DROP 字段名；

   - 修改表名

     RENAME TABLE TABLE_NAME TO 新表名；

   - 修改表所用字符集

     ALTER TABLE TABLE_NAME CHARACTER SET 字符集名；

   - 删除表

     DROP TABLE TABLE_NAME;

   - 添加主键（表已经创建完成）

     ALTER TABLE TABLE_NAEM ADD PROMARY KEY(字段名)；

   - 删除主键

     ​	ALTER TABEL TABEL_NAME DROP PRIMARY KEY;

   - 添加唯一索引

     ALTER TABLE TABLE_NAME ADD UNIQUE(字段名)；

   - 添加唯一索引设置索引名

     ALTER TABLE TABLE TABLE_NAME ADD UNIQUE KEY 索引名（字段名）;

   - 添加联合索引

     ALTER TABLE TABLE_NAME ADD UNIQUE INDEX 索引名（字段名1，字段名2）；

   - 删除索引

     ALTER TABLE TABLE_NAME DROP INDEX 索引字段名；

     

     

     

7. 

8. 

9. 

10. 

11. 

12. 

13. 

14. 

    

    

    

    

    

    

    

    

    

    

    

    

    

    

    

    

    

    

    

    

    

    