---
title: "国内使用 github 图床"
gitinfo: true
share: true
comments: true
slug: "github_cdn"
images: ["https://cdn.jsdelivr.net/gh/Borber/PublicPic1/headImg/head.png"] 
description: "github 被撸坏了 我整个博客都是寄生在他身上"
tags: ["github", "CDN"]
date: 2020-07-20T17:59:04+08:00
---

自从 **github** 被巨硬收购之后 越来越良心了 私有库可是无限开了.

但是 github 一直良心的是,公开库一直都可以免费开 而且一个公开库就可以放2G的文件.这对于我们这些找图床的人来说是一个不错的选择(垃圾 gitee 所有仓库总容量 5G 有个卵用)

这里介绍一种方法 可以在国内这种社会主义环境下 使用 github 作为高速图床



### 1/3 建立一个 github 公开库 名字随便

你可以查看下面这张图的地址 就是用本文的方法加载的

![截图](https://cdn.jsdelivr.net/gh/Borber/PublicPic1/博客园/github图床/BORBER_2020-06-19_18-10-01.png "创建仓库")

### 2/3 上传你的图片到库中

这里可以 clone 仓库到本地 加入图片 提交 再上传 (推荐)

也可以直接在网站里点击上传

![截图](https://cdn.jsdelivr.net/gh/Borber/PublicPic1/博客园/github图床/uploadfile.png)



### 3/3 根据你的github仓库地址改为正确的CDN地址 

地址为 https://cdn.jsdelivr.net/gh/{你的github用户名}/{仓库名称}/{具体路径}

这里我写了一款 小工具 可以直接将复制的 github 转换为 CDN加速链接  [下载链接](https://github.com/Borber/GithubPic/releases/download/0.0.1/GithubPic.exe)  

![截图](https://cdn.jsdelivr.net/gh/Borber/PublicPic1/%E5%8D%9A%E5%AE%A2%E5%9B%AD/github%E5%9B%BE%E5%BA%8A/exe.png)

解析出来的CDN链接就可以作为图床链接了 就我测试来说 速度完全可以接受 而且 没有大小限制 无限空间 (一个满了就再开一个) 也方便管理



Quicker 动作

- md文件 全局替换

  

  ![全局替换](https://cdn.jsdelivr.net/gh/Borber/PublicPic1/%E5%8D%9A%E5%AE%A2%E5%9B%AD/github%E5%9B%BE%E5%BA%8A/quicker.png)

  全选md文件文字 运行动作即可 全部本地图片替换成 github cdn链接

- 单独替换链接

  [地址](https://getquicker.net/Sharedaction?code=c9cdaf09-febd-42fa-2e8e-08d82c48e4ae)

  选中 github 的链接 运行 即可转换成CDN链接