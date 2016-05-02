---
title: C-复合语句中的局部变量定义问题
categories: [C]
tags: [C, 复合语句, 局部变量, 内存， 开销]
date: 2015-02-10 11:56:00
---

在复合语句，如`while`，`for`等定义局部变量，不会造成额外的开销。

示例：
```asm
root@long-VirtualBox:/data/Test/c/for循环中定义变量/src# objdump -d -S main.o
main.o:     file format elf32-i386


Disassembly of section .text:

00000000 <main>:
#include <stdio.h>


int main(int argc, char* argv[])
{
   0:   55                      push   %ebp
   1:   89 e5                   mov    %esp,%ebp
   3:   83 e4 f0                and    $0xfffffff0,%esp
   6:   83 ec 20                sub    $0x20,%esp
    int i = 0;
   9:   c7 44 24 18 00 00 00    movl   $0x0,0x18(%esp)
  10:   00 
    for (; i < 10; ++i) {
  11:   eb 26                   jmp    39 <main+0x39>
        int j = 1;
  13:   c7 44 24 1c 01 00 00    movl   $0x1,0x1c(%esp)  // i的初始化语句
  1a:   00 
        ++j;
  1b:   83 44 24 1c 01          addl   $0x1,0x1c(%esp)
        printf("j = %d\n", j);
  20:   8b 44 24 1c             mov    0x1c(%esp),%eax
  24:   89 44 24 04             mov    %eax,0x4(%esp)
  28:   c7 04 24 00 00 00 00    movl   $0x0,(%esp)
  2f:   e8 fc ff ff ff          call   30 <main+0x30>


int main(int argc, char* argv[])
{
    int i = 0;
    for (; i < 10; ++i) {
  34:   83 44 24 18 01          addl   $0x1,0x18(%esp)
  39:   83 7c 24 18 09          cmpl   $0x9,0x18(%esp)
  3e:   7e d3                   jle    13 <main+0x13>   // 重复执行初始化语句
        int j = 1;
        ++j;
        printf("j = %d\n", j);
    }

    return 0;
  40:   b8 00 00 00 00          mov    $0x0,%eax
}
  45:   c9                      leave  
  46:   c3                      ret   
```

-   不会造成不停的给`i`分配空间的操作，因为局部变量都是在编译时刻确定空间的，是通过操作`esp`来实现的。

-   但初始化语句`i = 0`会重复执行！

# 总结

-   最好最变量使用的地方，定义变量，最小化作用域

# 参考

1.  <http://stackoverflow.com/questions/982963/is-there-any-overhead-to-declaring-a-variable-within-a-loop-c>
1.  <http://stackoverflow.com/questions/7959573/declaring-variables-inside-loops-good-practice-or-bad-practice-2-parter>
