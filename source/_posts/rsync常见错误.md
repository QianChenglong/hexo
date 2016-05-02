---
title: rsync常见错误
categories: [rsync]
tags: [rsync]
date: 2015-06-03 08:55:20
---

1.   

错误信息

    @ERROR: chroot failed
    rsync error: error starting client-server protocol (code 5) at main.c(1635) [Receiver=3.1.1]

原因：

    rsyncd.conf中的path路径所设的那个目录并不存在所致.
