---
title: glog
tags: [glog]
date: 2016-03-23 15:37:36
---

# 要点

-   默认输出到`/tmp/<program name>.<hostname>.<user name>.log.<severity level>.<date>.<time>.<pid>`

-   重定向到标准出错

        GLOG_logtostderr=1 ./your_application
