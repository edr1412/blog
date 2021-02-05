---
title: "Linux系统查看系统安装时间"
gitinfo: true
share: true
comments: true
slug: "system_create_time"
images: ["https://cdn.jsdelivr.net/gh/Borber/PublicPic1/%E5%8D%9A%E5%AE%A2%E5%9B%AD/wolai/wolai.png"] 
description: "别忘了起点"
tags: ["linux"]
date: 2021-02-06T00:21:04+08:00
---

1. 首先查看硬盘

    ```shell
    ls /dev | grep sd
    ```

2. 其次查看系统盘 我的电脑上是 `/dev/sda2` 

    ```shell
    sudo dumpe2fs /dev/sda2 | grep "Filesystem created"
    ```

    ![截图](https://cdn.jsdelivr.net/gh/Borber/PublicPic1@master/teach/linux/system_create_time.png "截图")

