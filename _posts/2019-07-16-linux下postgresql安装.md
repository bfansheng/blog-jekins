---
layout: post
title: linux下postgresql安装
categories: [linux]
tags: [linux, postgresql]
---

## 1. 安装rpm包

```shell
yum install postgresql
yum install postgresql-server
yum install postgresql-contrib
yum install postgresql-libs
yum install postgresql-devel
```

## 2. 初始化数据库

1. 新建文件夹

   `mkdir -p /var/lib/pgsql/data `

2. 切换用户

   `su postgres`

3. 执行**initdb**

   `initdb -D /var/lib/pgsql/data/`

## 3. 外网访问配置

1. 修改postgresql.conf

   ```shell
   vim /var/lib/pgsql/data/postgresql.conf
   ```

   将listen_addresses = 'localhost' 改成listen_addresses = '*'

2. 修改pg_hba.conf

   ```shell
   vi /var/lib/pgsql/data/pg_hba.conf
   ```

   添加一行：

   ```
   host    all             all             0.0.0.0/0           trust
   ```

   

