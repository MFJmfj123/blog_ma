---
title: MySQL
author: 马福俊
date: '2022-11-14'
slug: MySQL
categories:
  - R
tags:
  - Say Hi
layout: post
math: no
draft: yes
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

4. 数据库的基本操作（增删改查）