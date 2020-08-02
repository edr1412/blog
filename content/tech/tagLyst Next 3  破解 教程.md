---
title: "tagLyst Next 3.717 破解 教程"
gitinfo: true
share: true
comments: true
slug: "tagLyst_Next_3"
images: ["https://github.com/Borber/PublicPic1/blob/master/ST/2x.jpg"] 
description: "但其实不知道怎么用这玩意"
tags: ["破解"]
date: 2020-08-02T21:56:04+08:00
---

此破解过程需要 mvn node electron 环境 请自行搜索 如何安装

博主的环境:

```json
{
	OS:"Window10 2004 内部预览 快速通道",
    mvn:"1.1.7",
    node:"v12.18.0",
    npm:"cnpm",
    electron:"v9.0.4",
    asar:"3.0.3",
    prettier:"2.0.5",
}
```

# 准备工作

前往[官网](http://www.taglyst.com/download-next)下载最新的 便携版本(网页最下方) 我没有使用安装版本 理论上来说是一样的

# app.asar 解包

app.asar 在 解压后的 run/resources 文件夹中

此处可取巧 使用 [打包好的软件](https://github.com/nwdxlgzs/asar-manager) 解析 asar 使用方法请自行摸索 若实在不懂可留言 博主再开一帖

```shell
npm install -g asar
asar extract app.asar ./app
```

# 代码格式化

vscode自带的格式化…. 就是个屎 此处推荐 **prettier** 

安装 prettier

```shell
npm install --g prettier
```

# 具体代码

进入 app/js 格式化 app1.js

```shell
prettier --write app1.js
```

打开 app1.js 找到下方代码块

```js
n = nz(t.userID, "");       
i = nz(t.expiringDate, "");
s = nz(t.error, "");      
```

替换为

```js
t.userID = "BORBER";
t.expiringDate = "2999/1/1";
t.error = "";
t.isBusinessClass = 1;
n = nz(t.userID, "");
i = nz(t.expiringDate, "");
```

其余不动

# app.asar 打包

```shell
asar pack app app.asar
```

替换掉 原来的 app.asar

同样地 此处可以使用文章开头 说的软件 打包

# 破解成果图

![截图](https://cdn.jsdelivr.net/gh/Borber/PublicPic1/%E5%8D%9A%E5%AE%A2%E5%9B%AD/tagLystNext/3717.png)



**本项目只做个人学习研究之用，不得用于商业用途！**

**若资金允许，请购买正版，谢谢合作！**