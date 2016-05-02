---
title: sudo unable to resolve host ubuntu
categories: [sudo]
tags: [sudo]
date: 2015-01-29 15:17:39
---

# 原因

通过更改`/etc/hostname`，修改了主机名，而`/etc/hosts`中没有更改


# 解决

修改`/etc/hosts`

    127.0.0.1   当前主机名

# 参考

1.  <http://ubuntuguide.net/fix-ubuntu-sudo-errorunable-to-resolve-host>
