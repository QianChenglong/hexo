---
title: ctags
categories: [ctags]
tags: [ctags]
date: 2015-04-03 16:47:34
---

# 选项

-   --list-kinds=python

    查看某种语言选项

-   -R

    递归处理

-  --format=level

    指定tag的输出格式，默认为2，level=2时，ex_cmd会追加`;"`(通过注释与老vi保持兼容)

-   −−fields=[+|−]flags

    用来控制`extension_fileds`中要包含的内容

# tag记录格式(<http://ctags.sourceforge.net/ctags.html#TAG FILE FORMAT>)

`tag_name<TAB>file_name<TAB>ex_cmd;"<TAB>extension_fields`

-   `tag_name` 用来检索的key

-   `file_name` tag所在的文件名

-   `ex_cmd` vim用来定位的命令
