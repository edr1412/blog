---
title: "Linux Reached target Graphical Interface 卡住 解决方案"
share: true
comments: true
slug: "linux_fix_1"
images: ["https://cdn.jsdelivr.net/gh/Borber/PublicPic1/headImg/head.png"] 
description: "曾经坑的我很惨"
tags: ["linux"]
date: 2021-01-01T20:55:04+08:00
---

这个解决方法仅适用于 systemd 启动太快导致的 显卡加载不及时

在你的 dm.service（KDE sddm.service; Gnome gdm.service） 中添加一句 

```sh
ExecStartPre=/usr/bin/sleep 1
```

感谢 [依云仙子](https://blog.lilydjwg.me/) [Archlinuxcn-TG](https://t.me/archlinuxcn_group)