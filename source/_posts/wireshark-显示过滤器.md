---
title: wireshark-显示过滤器
categories: [wireshark]
tags: [wireshark, 过滤器]
date: 2015-02-06 16:38:45
---

-   根据帧序号

        frame.number >= 6

-   根据http内容类型

        http.content_type == “application/x-www-form-urlencoded”

