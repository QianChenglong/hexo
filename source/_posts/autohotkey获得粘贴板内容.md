---
title: autohotkey获得粘贴板内容
categories: [autohotkey]
tags: [autohotkey, 粘贴板]
date: 2015-01-07 10:54:42
---

```autohotkey
; 获取当前选中内容
GetSelectText()
{
    tmp = %ClipBoard% ; 保存原来内容
    ClipBoard = ; 清空粘贴板
    Send, ^c ; 获取当前选中内容
    Sleep, 100 ; 确保操作成功
    text = %ClipBoard%
    ClipBoard = %cmp% ; 复原
    return text
}

msgbox % GetSelectText()
```
