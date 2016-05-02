---
title: python-相对导入
categories: [python]
tags: [python, 相对导入]
date: 2015-04-01 16:10:27
---

-   相对导入是基于当前模块的名称(`__name__`)，其实就是`. <=> __name__`

-   当一个模块作为主模块时，它的名称为`__main__`，所以在主模块中，不能使用相对导入！

-   当一个模块不作为主模块时，也就是说被主模块引用，必须使用相对导入(因为模块的搜索)

#参考

1.  <https://docs.python.org/2/tutorial/modules.html#intra-package-references>
