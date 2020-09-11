---
title: "AppImage 修改"
share: true
comments: true
slug: "appimage_fix"
images: ["https://cdn.jsdelivr.net/gh/Borber/PublicPic1/headImg/head.png"] 
description: "想修改修改 嘿嘿嘿"
tags: ["AppImage"]
date: 2020-09-10T22:29:04+08:00
---

 解包：

```shell
./NAME.AppImage --appimage-extract
```

打包：

```shell
./appimagetool-x86_64.AppImage squashfs-root NAME_NEW.AppImage
```

