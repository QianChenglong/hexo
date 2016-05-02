---
title: arch下安装pandoc
categories: [pandoc]
tags: [pandoc, arch]
date: 2015-04-09 11:27:07
---

-   添加仓库

        gvim /etc/pacman.conf

        [haskell-core]
        Server = http://repo-hs.archlinuxcn.org/$arch

-   添加认证

        pacman-key -r 4209170B
        pacman-key --lsign-key 4209170B

-   更新仓库

        pacman -Syy

-   安装pandoc

        pacman -S haskell-pandoc
