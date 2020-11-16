---
title: "Scrapy xpath 特性"
gitinfo: true
share: true
comments: true
slug: "Scrapy_xpath"
images: ["https://cdn.jsdelivr.net/gh/Borber/PublicPic1/%E5%8D%9A%E5%AE%A2%E5%9B%AD/wolai/wolai.png"] 
description: "坑爹啊! 鬼知道这玩意还有这特性"
tags: ["Scrapy", "爬虫", "python"]
date: 2020-08-05T14:00:04+08:00
---

Scrapy 的 Response.xpath 有一个坑爹特性 在处理表格的时候 如果你在 xpath 地址中 有tbody 那么他就解析不出来 得转变写法

例如

```shell
//table[2]/tbody/tr[1]/td[1]/b
```

应该写成

```
//table[2]//tr[1]/td[1]/b
```

这样就可以正常解析了 血的教训