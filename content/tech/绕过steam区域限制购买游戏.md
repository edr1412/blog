---
title: "绕过steam区域限制购买游戏"
gitinfo: true
share: true
comments: true
slug: "buy_galgame"
images: ["https://cdn.jsdelivr.net/gh/Borber/PublicPic1/headImg/head.png"] 
description: "小黄油 我来啦!"
tags: ["游戏"]
date: 2020-06-25T00:00:04+08:00
---



本方法 转自 知乎 [Firkraag](https://www.zhihu.com/people/Firkraag) 回答 在此感谢



### 查询游戏ID

前往 [**SteamDB**](https://steamdb.info/) 搜索游戏名称 获取 ID (一串数字)

![SteamDB](https://cdn.jsdelivr.net/gh/Borber/PublicPic1/cnblogs/Steam/steamdb.png)

### 添加游戏至愿望单

1. 登录 网页版本 Steam
2. 在Steam页面内 按F12 打开控制台 点击  Console
3. 替换 ID 并运行

```javascript
javascript:AddToWishlist( 要买的ID, 'add_to_wishlist_area','add_to_wishlist_area_success','add_to_wishlist_area_fail','1_5_9__407' );
```

![Steam](https://cdn.jsdelivr.net/gh/Borber/PublicPic1/cnblogs/Steam/steam.png)

### 购买

点击愿望单 找到刚刚添加的游戏 即可购买 (我之前已购买 故无法再添加愿望单 所以 请自行测试)

### 小技巧

创意工坊内容可以网页访问 订阅之后 本地 Steam 客户端会自行下载

> 请遵守中华人民共和国法律 本文只做学习讨论 不对任何人完全或部分地依据本网站的全部或部分内容从事的任何事情和因其任何作为或不作为造成的后果承担任何责任