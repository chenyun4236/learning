---
title: MySQL 索引与 SQL 优化入门
date: 2026-01-29
categories:
  - mysql
---

## 一、索引的作用

索引可以显著提升查询性能，但也会：

- 占用磁盘
- 影响写入速度

## 二、常见索引类型

- PRIMARY KEY
- UNIQUE
- 普通索引
- 组合索引

## 三、EXPLAIN 分析 SQL

```sql
EXPLAIN SELECT * FROM user WHERE id = 1;
