---
title: pragma-once
categories: [C++]
tags: [C++, pragme once]
date: 2015-01-08 16:43:34
---

`#pragma once`是一条非标准的预处理指令，用来防止同一文件被多次包含，同`include guard`作用一样。
绝大多数编译器都提供支持。

具有的优点：

-   代码更少，不用`include`那么麻烦
-   更有效，更安全，由预处理器去维护判断是否已经包含过，而`include`需要程序员定义不同的宏名来保证，
    若宏名冲突，则导致编译失败
-   效率更高，预处理器针对其做了特殊的优化
-   **复制，修改代码更容易，当把一个头文件复制到另一个项目中，或改名时，不用按着命令规范去修改**

# 注意

当同一个文件，在项目内有符号链接或硬链接时，可能导致无法工作。

# 参考

1.  <https://en.wikipedia.org/wiki/Pragma_once>
1.  <http://stackoverflow.com/questions/1143936/pragma-once-vs-include-guards>
