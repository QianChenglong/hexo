---
title: python-打印不追加换行
categories: [python]
tags: [python, 打印]
date: 2015-01-16 10:15:35
---

-   python2, 3

        import sys
        sys.stdout.write('hello world')

-   python3

        print('hello world', end="")

-   python2

        print('hello world', )

# 参考

1.  <http://www.zhihu.com/question/20390166>
1.  <http://stackoverflow.com/questions/493386/how-to-print-in-python-without-newline-or-space>
