---
title: GetTickCount
date: 2014-12-31 10:51:01
categories: windows
tags: [windows, GetTickCount, API]
---

## 精度

这个函数并非实时发送，而是由系统每18ms发送一次，因此其最小精度为18ms。当需要有小于18ms的精度计算时，应使用StopWatch方法进行。

*   连续触发200次，实测下来，最小间隔在15ms。
