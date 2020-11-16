---
title: "CentOS 安装 Tomcat"
gitinfo: true
share: true
comments: true
slug: "centos_Tomcat"
images: ["https://cdn.jsdelivr.net/gh/Borber/PublicPic1/headImg/head.png"] 
description: "常规 常规"
tags: ["Linux"]
date: 2020-06-23T23:00:04+08:00
---

```shell
cd /usr/local/ // 进入local文件夹
```

### 下载

```shell
wget https://mirror.bit.edu.cn/apache/tomcat/tomcat-9/v9.0.36/bin/apache-tomcat-9.0.36.tar.gz
```

没有 wget 请安装 

```shell
yum -y install wget // 安装wget
```

### 解压

```shell
tar -zxvf apache-tomcat-9.0.36.tar.gz
```

```shell
mv apache-tomcat-9.0.36 tomcat
```

### tomcat常用命令

```shell
/usr/local/tomcat/bin/startup.sh //启动
/usr/local/tomcat/bin/shutdown.sh //关闭
ps -ef|grep java //查看进程
kill -9 //杀死进程
tail -f /usr/local/tomcat/logs/catalina.out //查看日志
```

