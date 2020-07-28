---
title: "CentOS 安装 JDK8"
gitinfo: true
share: true
comments: true
slug: "centos_JDK8"
images: ["https://cdn.jsdelivr.net/gh/Borber/PublicPic1/headImg/head.png"] 
description: ""
tags: ["Linux", "Java"]
date: 2020-06-23T22:51:04+08:00
---

均为 root 账户操作

### 检查系统中的jdk版本

```shell
java -version
```

没有的话直接下一步 有就卸载

### 查询自带的openjdk

```shell
rpm -qa | grep -i java
```

没有的话直接跳过下一步 有就卸载

### 检查系统环境

```shell
uname -a //i686表示32位  x86_64表示是64位
```

### 下载

前往 [injdk](https://www.injdk.cn/) 下载对应 jdk 没有wget 请安装

```shell
yum -y install wget //安装wget
```

```shell
wget https://d2.injdk.cn/oracle/8/jdk-8u251-linux-x64.tar.gz
```

解压

```shell
mkdir -p /usr/local/java 
tar zxvf jdk-8u251-linux-x64.tar.gz -C /usr/local/java
```



### 配置环境变量

```shell
vi /etc/profile
```

不会用的话去查 或者用别的也行

文件最后添加

```shell
JAVA_HOME=/usr/local/java/jdk1.8.0_251
export CLASSPATH=$:CLASSPATH:$JAVA_HOME/lib/ 
export PATH=$PATH:$JAVA_HOME/bin 
```

重新加载配置文件，使配置生效

```shell
source /etc/profile
```

### 检查是否安装成功

查看java版本

```shell
java -version
```

显示

```shell
java version "1.8.0_251"
Java(TM) SE Runtime Environment (build 1.8.0_251-b08)
Java HotSpot(TM) 64-Bit Server VM (build 25.251-b08, mixed mode)
```

成功!