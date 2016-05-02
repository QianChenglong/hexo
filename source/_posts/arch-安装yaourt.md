---
title: arch-安装yaourt
categories: [arch]
tags: [arch,yaourt]
date: 2015-06-26 09:30:03
---


1.  添加源仓库到pacman

        vi /etc/pacman.conf

        [archlinuxfr]
        SigLevel = Never
        Server = http://repo.archlinux.fr/$arch

1.  更新安装

        pacman -Sy yaourt

1.  安装拓展

        yaourt -S aurvote customizepkg rsync
