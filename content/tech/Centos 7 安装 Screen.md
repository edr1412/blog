---
title: "CentOS 7 安装 Screen"
gitinfo: true
share: true
comments: true
slug: "centos_screen"
images: ["https://cdn.jsdelivr.net/gh/Borber/PublicPic1/%E5%8D%9A%E5%AE%A2%E5%9B%AD/wolai/wolai.png"] 
description: "这玩意不应该自带吗??"
tags: ["CentOS", "Linux"]
date: 2020-08-05T17:26:04+08:00
---

### 安装

```bash
yum install screen
```

### screen 命令常用参数

- -A 让所有视窗自动调整适应当前终端机的窗口大小
- -d <会话名称> 将指定的 screen 会话离线
- -r <会话名称> 将指定的 screen 会话恢复
- -h <行数> 指定视窗的缓冲区行数
- -S <会话名称> 指定 screen 会话的名称
- -x 恢复所有离线的会话
- -ls 或 -list 显示当前的 screen 会话
- --wipe 自动将无法使用的screen会话删除

### 创建会话

创建名称为borber的会话

```bash
screen -S borber
```

### 查看当前已存在的会话

```bash
screen -ls

There is a screen on:
        6262.borber     (Attached)
1 Socket in /var/run/screen/S-root.

```

