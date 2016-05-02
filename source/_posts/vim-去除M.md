---
title: vim-去除^M
categories: [vim]
tags: [vim]
date: 2015-01-16 17:12:32
---

-   方法1

```
:%s;<Ctrl-V><Ctrl-M>;;g
```

-   方法2

```
:%s;<Ctrl-K>CR;;g
```

# 参考

1.  <http://stackoverflow.com/questions/811193/how-to-convert-the-m-linebreak-to-normal-linebreak-in-a-file-opened-in-vim>
