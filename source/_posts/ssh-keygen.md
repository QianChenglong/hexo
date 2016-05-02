---
title: ssh-keygen
tags: [ssh, sshk-keygen]
date: 2016-03-28 11:05:46
---

-   将pub格式转换为pem格式

         ssh-keygen -f id_rsa.pub -e -m pem >id_rsa.pub.pem
