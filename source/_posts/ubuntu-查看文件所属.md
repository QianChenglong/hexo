---
title: ubuntu-查看文件所属
categories: [ubuntu]
tags: [ubuntu, 文件, apt]
date: 2015-01-28 13:59:12
---

-   安装`apt-file`

        sudo apt-get install apt-file

-   更新数据库

        sudo apt-file update

-   查询

        apt-file search /usr/include/arpa/inet.h

# 参考

1.  <http://superuser.com/questions/10997/find-what-package-a-file-belongs-to-in-ubuntu-debian>
