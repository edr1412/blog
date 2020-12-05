---
title: "ArchLinux StarUML 4.0 安装"
share: true
comments: true
slug: "StarUML4_0"
images: ["https://cdn.jsdelivr.net/gh/Borber/PublicPic1/headImg/head.png"] 
description: "因为AUR的作者没有更新"
tags: ["Linux"]
date: 2020-11-05T11:25:04+08:00
---

新建一个目录 `~/.cache/yay/staruml`  并进入

新建文件 `PKGBUILD` 并粘贴进下面的代码

```shell
pkgname=staruml
pkgver=4.0.0
pkgrel=1
pkgdesc="A sophisticated software modeler"
arch=('x86_64')
url="http://staruml.io/"
license=('custom:staruml')
depends=('libxss' 'libxtst' 'nss' 'alsa-lib' 'gtk2')
source=("$pkgname-${pkgver}_amd64.deb::https://staruml.io/download/releases-v4/StarUML_${pkgver}_amd64.deb")
sha256sums=('cb0ab6a19c2e03aac0f92191dfcfed20d480460b68abc17544b40deaa4aad088')

package() {
    # Extract package data
    tar xf data.tar.xz -C "${pkgdir}"

    install -D -m644 "${pkgdir}/opt/StarUML/LICENSES.chromium.html" "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
    chmod 4755 "${pkgdir}/opt/StarUML/chrome-sandbox"
    mkdir "${pkgdir}/usr/bin"
    ln -s '/opt/StarUML/staruml' "${pkgdir}/usr/bin/staruml"
}
```

退出编辑 并运行 `makepkg -si ` 打包安装

注: 网络不太好可以 通过蓝奏云下载我提供的官网 DEB 安装包放入上述目录再运行命令 -> [下载地址](https://borber.lanzous.com/iFeTBj2fdnc)

