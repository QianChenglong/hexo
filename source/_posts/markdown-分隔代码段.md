---
title: markdown-分隔代码段
categories: [markdown]
tags: [markdown]
date: 2015-04-08 10:52:49
---

因为markdown本身语法，两个代码段之间若不存在任何非空白字符，则视为同一代码段，
所以为了分隔代码段，而又不影响实际内容，可以插入html注释。

```markdown
code block 1

<!-- -->

code block 2
```

# 参考

1.  <http://meta.stackexchange.com/questions/152358/separating-consecutive-code-blocks>
