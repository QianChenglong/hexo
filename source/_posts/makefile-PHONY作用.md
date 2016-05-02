---
title: makefile-.PHONY作用
categories: [makefile]
tags: [makefile, .PHONY]
date: 2015-01-08 14:21:17
---

先看makefile核心规则

```makefile
target: prerequisites
    command
```

make解析执行makefile判断过程：

-   若`target`不存在，则根据`prerequisites`，执行`commond`
-   若`target`已存在，则比较`target`和`prerequisites`修改时间
    -   **若`prerequisites`不存在，则不执行`commond`!**
    -   若`prerequisites`比`target`新，则执行`commond`(说明在生成`target`后，对依赖文件进行了修改)
    -   若`prerequisites`没有`target`新，则不执行`commond`

# 为什么需要伪目标

-   假设当前目录下已有`clean`文件，则根据make解析过程，不会执行后续`commond`

# 什么是伪目标(`.PHONY`)

伪目标相对于目标而言，其不会生成实体**文件**

# 伪目标的作用

显式告诉make不要跟实体文件进行关联判断，以便执行相应的命令

