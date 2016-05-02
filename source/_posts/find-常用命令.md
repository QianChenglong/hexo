---
title: find-常用命令
categories: [linux]
tags: [linux, find]
date: 2015-02-12 18:01:53
---

# 批量重命名

    find . -name '*命令理解' -exec rename -v 's/命令理解/-comprehension/' {} \;

# 删除vs2010的无用文件

    find . -regextype  posix-extended -regex ".*Debug|.*\.sdf" -exec rm -rf {} \;

# 批量添加.txt拓展名

    find . -type f -regextype posix-extended -regex "\\.*[^.]*$" -exec mv -v {} {}.txt \;

# 找出最近修改过的文件

    find . -mtime -4 | grep '循环'

# 批量删除文件

    find . -name <expr> -exec rm -v {} \;

# 批量删除.git目录

    find . -name ".git" -type d  -print0 | xargs -0 rm -vrf

# 多目录查找

    find src lib -name "*.[ch]"
