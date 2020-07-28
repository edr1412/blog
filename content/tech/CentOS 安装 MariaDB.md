---
title: "CentOS 安装 MariaDB"
gitinfo: true
share: true
comments: true
slug: "centos_MariaDB"
images: ["https://cdn.jsdelivr.net/gh/Borber/PublicPic1/headImg/head.png"] 
description: ""
tags: ["Linux", "MariaDB"]
date: 2020-06-23T23:05:04+08:00
---

MariaDB 是MySQL的开源版本 一样用的


```shell
yum install mariadb mariadb-server
systemctl start mariadb   #启动mariadb
systemctl enable mariadb  #设置开机自启动
mysql_secure_installation #设置root密码等相关
mysql -uroot -p           #测试登录
```

