---
title: "Linux去除文件夹背景色"
share: true
comments: true
slug: "Linux-dir-background"
images: ["https://cdn.jsdelivr.net/gh/Borber/PublicPic1/headImg/head.png"] 
description: "不去除的话好丑地说"
tags: ["Linux", "美化"]
date: 2020-09-03T11:36:04+08:00
---

 修改文件:

```shell
echo "OTHER_WRITABLE 01;34" >> $HOME/.dir_colors
```

添加 到 .bashrc 或者 .zshrc  .zshrc 注意添加到 `source $ZSH/oh-my-zsh.sh` 这句的后面 否则无效

```shell
eval `dircolors $HOME/.dir_colors`
```

立即生效

```shell
source ~/.bashrc
```

或者重启即可生效