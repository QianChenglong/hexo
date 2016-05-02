---
title: cmake-macro-vs-function
categories: [cmake]
tags: [cmake, macro, function]
date: 2015-01-09 10:43:17
---

cmake中，`macro`类似于C中的宏函数，会进行参数替换，而`function`类似于C中的函数，
参数是一个变量，可以进行赋值等操作。

示例：
```cmake
set(var "ABC")

macro(Moo arg)
  message("arg = ${arg}")
  set(arg "abc")
  message("# After change the value of arg.")
  message("arg = ${arg}")
endmacro()
message("=== Call macro ===")
Moo(${var})

function(Foo arg)
  message("arg = ${arg}")
  set(arg "abc")
  message("# After change the value of arg.")
  message("arg = ${arg}")
endfunction()
message("=== Call function ===")
Foo(${var})
```

输出：
```
=== Call macro ===
arg = ABC
# After change the value of arg.
arg = ABC
=== Call function ===
arg = ABC
# After change the value of arg.
arg = abc
```

# 参考

1.  <http://stackoverflow.com/questions/24297999/function-vs-macro-in-cmake>
1.  <http://www.cmake.org/cmake/help/v3.0/command/macro.html>
1.  <http://www.cmake.org/cmake/help/v3.0/command/function.html>
