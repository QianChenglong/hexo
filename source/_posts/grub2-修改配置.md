---
title: grub2-修改配置
categories: [grub2]
tags: [grub2]
date: 2015-06-17 15:53:19
---

# 步骤

1.  修改配置文件

        vi /etc/default/grub
        /etc/grub.d/

1.  更新配置

        grub2-mkconfig -o /boot/grub2/grub.cfg

# 参考

1.  <https://help.ubuntu.com/community/Grub2/Setup>
