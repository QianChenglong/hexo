---
title: python-global
tags: [python, global]
date: 2015-09-17 14:37:15
---

```python3
var = 1

def fun():
    var = 2
    print(var)

def main():
    fun()
    print(var)
    
>>> main()
2
1
```

在pytho中函数中,python将`var`处理成同名的局部变量!

所以,当执行复合赋值运算时,会报错!

```python3
var = 1

def main():
    var += 2
    print(var)

>>> main()
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
  File "<stdin>", line 2, in main
UnboundLocalError: local variable 'var' referenced before assignment
```

# 解决

添加`global`声明

```python3
var = 1

def main():
    global var
    var += 2
    print(var)

>>> main()
3
```

# 参考

1.  <http://stackoverflow.com/questions/10851906/python-3-unboundlocalerror-local-variable-referenced-before-assignment?lq=1>
1.  [python中在哪些情况下必须使用global来声明全局变量？](http://segmentfault.com/q/1010000000195730)
1.  <http://stackoverflow.com/questions/8934772/assigning-to-variable-from-parent-function-local-variable-referenced-before-as>
