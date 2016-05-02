---
title: chrome-xml加载本地文件
categories: [chrome]
tags: [chrome, xml]
date: 2015-01-22 17:19:50
---

# 原因

chrome为了安全，默认不允许加载本地文件

# 解决

添加启动参数`--allow-file-access-from-files`

# 参考

1.  <http://stackoverflow.com/questions/3828898/can-chrome-be-made-to-perform-an-xsl-transform-on-a-local-file>
