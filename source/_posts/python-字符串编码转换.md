---
title: python-字符串编码转换
categories: [python]
tags: [python, 字符串, 编码, 转换]
date: 2014-12-10 10:11:21
---

# 概念

python使用`unicode`作为字符串内部编码，所有转换应通过`unicode`进行

编码(encode)，将中间对象(`unicode object`)转为其他编码对象

解码(decode)，将其他编码对象转为中间对象(`unicode object`)

# 非`unicode object`转`unicode object`

前提必须清楚字符串是什么编码，假设`str`为`gbk`编码

    u = str.decode('gbk')

或

    u = unicode(str, 'gbk')

# `unicode object`转非`unicode object`

假设转为`utf-8`

    utf8 = u.encode('utf-8')
