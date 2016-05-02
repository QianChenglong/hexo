---
title: tuple
categories: [理论]
tags: [理论, tuple, 元组, python]
date: 2014-12-26 17:40:53
---

# 形式定义

元组是**个数有限**的对象的**序列**。元组由三部分组成：边界符、分隔符和元素。通常采用的边界符是小括号"(  )"，分隔符是逗号","。

特性：

-   个数有限

-   有序

-   用来表示一组相关联数据

# 背景

-   在数学中，**元组**被用来描述对象的属性，例如，有向图被定义成一个二元组（V, E），这里V是节点的集合，E是V × V的子集，表示边。

-   在计算机科学中，**元组**被用来描述一组相关联的数据，常通过位置关系来隐式说明值得意义。

# python中的tuple

python中的tuple元素类型不要求一致，即意味着可以各种嵌套使用。如`([1, 2], {'a': 1}, (1, 2))`

# 与list对比

## 存储对象

-   tuple存储的元素是异构的(heterogeneous)，有点类似C中的结构体，是用来表达对象的组成

-   list，存储的元素是同构的(homogeneous )，是一种序列的存储方式(链式存储)，是用来做数据的容器

## 可变性

-   tuple是不可变的

-   list是可变的

## 提供的操作

-   tuple无增删改

-   list提供增删改

# 优势

逻辑清晰，代码安全，健壮性更好！

# 何时使用

根据数据本质特征

# 参考

1.  <http://en.wikipedia.org/wiki/Tuple>
1.  <http://zh.wikipedia.org/wiki/%E5%A4%9A%E5%85%83%E7%BB%84>
1.  <http://en.wikipedia.org/wiki/List_(abstract_data_type)>
1.  <http://stackoverflow.com/questions/626759/whats-the-difference-between-list-and-tuples>
1.  <http://stackoverflow.com/questions/1708510/python-list-vs-tuple-when-to-use-each>
1.  [Understanding tuples vs. lists in Python](http://news.e-scribe.com/397)
1.  <https://docs.python.org/dev/library/collections.html#collections.namedtuple>
