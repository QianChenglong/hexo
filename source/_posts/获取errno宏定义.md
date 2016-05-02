---
title: 获取errno宏定义
tags: [errno]
date: 2016-03-11 16:56:57
---

    cpp -dM /usr/include/errno.h | grep 'define E' | sort -n -k 3

# 参考

1.  <http://stackoverflow.com/questions/503878/how-to-know-what-the-errno-means>
