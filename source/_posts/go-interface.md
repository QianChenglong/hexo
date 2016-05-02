---
title: go-interface
tags: [go, interface]
date: 2015-11-10 17:14:19
---

# 要点

1.  `interface`是一组`method`的集合(而不是`function`, 因为`function`没有`reciver`)

1.  若某个类型实现了`interface`内所有`method`,则该类型对象与该`interface`对象转换

1.  `interface`是一种语义上的抽象,该对象提供了某种**语义抽象**功能,而该功能的具体实现不同

    如`coder(编码器)`,存在编码,解码功能,但具体可能有`json`,`xml`等多种方式实现

1.  赋值给`interface`

    -   若为值,则该类型`method`的`reciver`也必须是值类型

    -   若为指针值,则该类型`method`的`reciver`也必须是指针类型

    因为`method`的`reciver`是否为指针,代表的语义功能可能完全不一样

    `reciver`为指针类型,意味着在该`method`中,很可能会改变该对象自身(具体由实现决定)

    若一个`method`要求的是指针类型,而在给`interface`赋值时,只是传值的话,是无法改变该对象的!

# 参考

1.  <https://github.com/astaxie/build-web-application-with-golang/blob/master/zh/02.6.md>
