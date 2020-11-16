---
title: "TiddlyWiki 静态部署方案"
gitinfo: true
share: true
comments: true
slug: "TiddlyWiki_deploy"
images: ["https://cdn.jsdelivr.net/gh/Borber/PublicPic1/%E5%8D%9A%E5%AE%A2%E5%9B%AD/wolai/wolai.png"] 
description: "TiddlyWiki 天下第一"
tags: ["TiddlyWiki"]
date: 2020-08-26T20:00:04+08:00
---

废话不多说 直接开搞

首先 github pages 是可行的 但是国内访问速度不友好 此处推荐vercel

### 建立Wiki仓库

![建立仓库](https://cdn.jsdelivr.net/gh/Borber/PublicPic1@master/teach/TiddlyWiki/1.png "建立仓库")



### 上传wiki

不管你以什么方式 把wiki的html文件放到github仓库里面去  建议直接起名 index.html 那样可以作为省略主页 即避免类似 .com/sb.html 这样的丑陋链接

git管理 我推荐 [GitKraken](https://www.gitkraken.com/)

![上传wiki](https://cdn.jsdelivr.net/gh/Borber/PublicPic1@master/teach/TiddlyWiki/2.png "上传wiki")

![成果](https://cdn.jsdelivr.net/gh/Borber/PublicPic1@master/teach/TiddlyWiki/3.png "成果")

### vercel拉取

[Vercel](https://vercel.com/) 注册不在此赘述 github账号可直接登录

![导入项目](https://cdn.jsdelivr.net/gh/Borber/PublicPic1@master/teach/TiddlyWiki/4.png "导入项目")

![步骤一](https://cdn.jsdelivr.net/gh/Borber/PublicPic1@master/teach/TiddlyWiki/5.png "步骤一")

![步骤二](https://cdn.jsdelivr.net/gh/Borber/PublicPic1@master/teach/TiddlyWiki/6.png "步骤二a")

![](https://cdn.jsdelivr.net/gh/Borber/PublicPic1@master/teach/TiddlyWiki/7.png "步骤二b")

![步骤三](https://cdn.jsdelivr.net/gh/Borber/PublicPic1@master/teach/TiddlyWiki/8.png "步骤三")

![步骤四](https://cdn.jsdelivr.net/gh/Borber/PublicPic1@master/teach/TiddlyWiki/9.png "步骤四")



#### 成功



![成功](https://cdn.jsdelivr.net/gh/Borber/PublicPic1@master/teach/TiddlyWiki/10.png "成功")

点击 `Visit` 即可查看

**你看到的时候 我可能已经删除该Demo**

![展示](https://cdn.jsdelivr.net/gh/Borber/PublicPic1@master/teach/TiddlyWiki/11.png "展示")

### 实现全平台编辑

![github设置](https://cdn.jsdelivr.net/gh/Borber/PublicPic1@master/teach/TiddlyWiki/12.png "github设置")



这里对应你的仓库(文章开头建立的 当然 你附属在你的静态博客上是一样的 但是 路径 和 仓库名不能错) token 需要给读写权限 这个可以谷歌一下

设置好之后 你只需要在新平台输入一次token (TiddlyWiki 本体不会保存你的token 不必担心) 即可实现保存自动push 到 Github 然后 vercel 自动拉取更新

至此结束 模糊之处评论询问 我会一一解答.