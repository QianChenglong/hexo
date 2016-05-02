---
title: UUID
categories: [programming]
tags: [UUID]
date: 2015-06-26 10:43:18
---

# 含义

通用唯一识别码 (Universally Unique Identifier)

# 作用

是让分布式系统中的所有元素，都能有唯一的辨识资讯，而不需要透过中央控制端来做辨识资讯的指定

# 表示方法

-   标准 4B-2B-2B-2B-6B(xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx)
-   微软(GUID) 4B-2B-2B-8B(xxxxxxxx-xxxx- xxxx-xxxxxxxxxxxxxxxx)

# 原理

MAC地址：故意情况下可重复；
机器标识：Java下就是JVM标识，故意情况下可重复；
纳秒级当前时间：故意情况下可重复；
随机数：小概率重复；
自增序列数（或时钟序列）：循环溢出时重复；
