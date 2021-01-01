---
title: "Flameshot 截图美化"
share: true
comments: true
slug: "flameshot_beautify"
images: ["https://cdn.jsdelivr.net/gh/Borber/PublicPic1/headImg/head.png"] 
description: "Linux？ NO！-> Mac！"
tags: ["linux"]
date: 2021-01-01T23:50:04+08:00
---

 项目原地址： [千玄子](https://gitlab.com/zjuyk/user-scripts/-/blob/master/.local/bin/addshadow)

改进 Flameshot 截图之后自动美化

screenshot

```shell
#!/bin/bash 
flameshot gui --raw > /home/x/BORBER/Download/Temp/temp.png & #这里的地址 自定义 但需要与下一个脚本中匹配
BPID=$!
wait $BPID                                                                                               /home/x/BORBER/shell/addshadow # 自己更改为你的地址
```

addshadow

```shell
#!/bin/bash

# Get the picture from clipboard
cp /home/x/BORBER/Download/Temp/temp.png /tmp/clipboard.png #此处需要匹配上一个脚本中的地址
# Add round corner
convert /tmp/clipboard.png \
          \( +clone  -alpha extract \
      -draw 'fill black polygon 0,0 0,8 8,0 fill white circle 8,8 8,0' \
      \( +clone -flip \) -compose Multiply -composite \
      \( +clone -flop \) -compose Multiply -composite \
    \) -alpha off -compose CopyOpacity -composite /tmp/output.png
# Add shadow
convert /tmp/output.png \( +clone -background black -shadow 100x15+0+0 \) +swap -background transparent -layers merge +repage /tmp/des.png
# Add border
convert /tmp/des.png -bordercolor white -border 20 /tmp/des.png
# Add watermark
composite -gravity SouthEast /home/x/BORBER/Git/PublicPic1/watermark/borber.png /tmp/des.png /tmp/des.png # 此处定义的是右下角的水印 可以自行设置 或者注释此行 以 不使用
# Send picture to clipboard
xclip -selection clipboard -t image/png -i /tmp/des.png
# remove the left pictures
rm /tmp/clipboard.png /tmp/des.png /tmp/output.png

```

上述两个脚本都需要基于运行权限 `chmod +x` 

在你的系统中 设置截图快捷键的命令为 screenshot 的绝对地址即可使用 手动使用也可

#### 效果图：

![shot](https://cdn.jsdelivr.net/gh/Borber/PublicPic1@master/teach/Flameshot/shot.png)