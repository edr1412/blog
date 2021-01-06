---
title: "KDE 未知的协议“tg”"
share: true
comments: true
slug: "kde_fix_tg"
images: ["https://cdn.jsdelivr.net/gh/Borber/PublicPic1/headImg/head.png"] 
description: "有点蛋疼"
tags: ["linux"，"KDE"]
date: 2021-01-06T22:00:04+08:00
---

 KDE中，突然出现报错：`无法创建输入输出后端。klauncher 回应：未知的协议“tg”`  

修改 `~/.config/mimeapps.list` 

```shell
...
x-scheme-handler/tg=telegramdesktop.desktop
...
```

保存退出即可