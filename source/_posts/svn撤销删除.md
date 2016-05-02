---
title: svn撤销删除
categories: [svn]
tags: [svn, undo, delete]
date: 2014-12-09 16:49:56
---

-   通过`svn delete`删除的文件或目录

        svn revert DeletedDir --recursive

-   手动删除或`rmdir`

        svn update DeletedDir
# 参考

1.  <http://stackoverflow.com/questions/1786687/svn-undo-delete-before-commit>
1.  <http://svnbook.red-bean.com/nightly/en/svn.ref.svn.c.revert.html>
