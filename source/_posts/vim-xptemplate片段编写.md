---
title: vim-xptemplate片段编写
categories: [vim]
tags: [vim, xptemplate]
date: 2015-01-26 16:05:19
---

-   调用vim函数

```vim
~expand("%:r")^
```

-   可视模式下wrap

        XPT code wrap=cursor " ```language code ```
        ```~language^
        ~cursor^
        ```
