---
title: git-常用命令
tags: [git]
date: 2015-07-24 10:45:41
---

# 选项

-   --git-dir 指定`.git`目录

-   --work-dir 指定工作目录

# 常用命令

-   丢弃未缓存的修改

        git checkout -- order.cpp

-   默认推送所有分支和tag

        git push --all origin -u

-   迁出到指定目录

        git --work-tree=../v0.03 checkout v0.03 .
