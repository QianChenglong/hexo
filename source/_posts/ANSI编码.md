---
title: ANSI编码
categories: [字符编码]
tags: [编码, ANSI]
date: 2015-02-28 10:52:05
---

# ANSI编码是什么？

ANSI编码并不是一种编码！而是**美国国家标准学会(American National Standards Institute)**关于制作的ANSI C中关于区域字符编码的标准。

所以各地不同的编码方式统称为**ANSI编码**

在简体中文windows系统下，利用记事本等软件默认保存为`ANSI编码`，对应的代码页为`cp936`(GBK)。

ANSI编码采用1~4字节进行编码，是一种变长编码方案，又叫做多字节字符集(MBCS)。

# ANSI编码的缺陷

ANSI编码都是各区域针对本地的编码方式，是在兼容ASCII编码的基础上拓充而来的，如GB2312，BIG5等。
因为各地编码存在冲突，所以无法做到互通。

# ANSI编码怎么实现的？

-   原ASCII编码字符保持不变，仍然为占用1个字节。

-   对其他字符，采用多字节编码，第一字节(前导字节)具有一定特征来表明后续字节一起来表示一个字符，

    如在GBK编码中，前导字节范围为0x81-0xFE。

# 参考

1.  [维基-Windows(ANSI)代码页](http://zh.wikipedia.org/wiki/%E4%BB%A3%E7%A0%81%E9%A1%B5#Windows.EF.BC.88ANSI.EF.BC.89.E4.BB.A3.E7.A2.BC.E9.A0.81)
1.  <http://en.wikipedia.org/wiki/American_National_Standards_Institute>
1.  [遇到乱码不怕不怕啦——计算机字符编码详尽讲解](http://www.guokr.com/blog/763017/)
1.  [百度百科-ANSI编码](http://baike.baidu.com/view/1273097.htm)
1.  [msdn-支持多字节字符集](https://msdn.microsoft.com/zh-cn/library/vstudio/5z097dxa(v=vs.110).aspx)
