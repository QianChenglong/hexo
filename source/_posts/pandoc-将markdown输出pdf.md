---
title: pandoc-将markdown输出pdf
categories: [pandoc]
tags: [pandoc, markdown, pdf]
date: 2015-04-09 10:40:31
---

# 环境

-   win7

# 安装

-   [pandoc](https://github.com/jgm/pandoc/releases)

-   [MiKTex](http://miktex.org/)

    [下载](https://www.ctan.org/tex-archive/systems/win32/miktex/setup)

-   将`pandoc.exe`所在目录(`C:\Users\USERNAME\AppData\Local\Pandoc`)添加到`PATH`

-   查看当前系统字体

        fc-list > C:\fonts.txt

-   运行`miktex-update_admin.exe`更新

-   生成

        pandoc 简历.md -o 1.pdf --latex-engine=xelatex -V mainfont=SimSun

# 参考

1.  <http://johnmacfarlane.net/pandoc/faqs.html>
1.  [神器Pandoc的安装与使用](http://zhouyichu.com/misc/Pandoc.html)
1.  <http://sourceforge.net/p/miktex/bugs/2328/>
