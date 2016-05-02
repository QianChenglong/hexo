---
title: gcc-链接库顺序
tags: [gcc, link]
date: 2015-08-26 17:44:34
---

# 说明

在gcc编译时,链接库的指定顺序会影响编译行为!

gcc手册说明:

```
-l library
       Search the library named library when linking.  (The second alternative with the library as a separate argument is only for POSIX compliance and is not
       recommended.)

       It makes a difference where in the command you write this option; the linker searches and processes libraries and object files in the order they are
       specified.  Thus, foo.o -lz bar.o searches library z after file foo.o but before bar.o.  If bar.o refers to functions in z, those functions may not be
       loaded.

       The linker searches a standard list of directories for the library, which is actually a file named liblibrary.a.  The linker then uses this file as if
       it had been specified precisely by name.

       The directories searched include several standard system directories plus any that you specify with -L.

       Normally the files found this way are library files---archive files whose members are object files.  The linker handles an archive file by scanning
       through it for members which define symbols that have so far been referenced but not defined.  But if the file that is found is an ordinary object file,
       it is linked in the usual fashion.  The only difference between using an -l option and specifying a file name is that -l surrounds library with lib and
       .a and searches several directories.
```

理解:

假设C依赖库A,B,库B依赖于库A,则链接的时候要写为:

   gcc -o C -lB -lA

若写成:

   gcc -o C -lA -lB

# 链接时,符号寻找过程

1.  根据库路径列表,依次找到需要链接的库

    -   若一个库在该路径列表中存在多个,则使用第一个找到的

1.  从左向右,依次找寻符号定义

    -   `gcc -o C -lB -lA`,符号搜寻过程是C=>B, B=>A

# 结论!

在项目开发过层中尽量让lib是垂直关系,避免循环依赖,越是底层的库,越是往后面写

    g++ ...  obj($?) -l(上层逻辑lib) -l(中间封装lib) -l(基础lib) -l(系统lib) -o $@

# 参考

1.  [折腾gcc/g++链接时.o文件及库的顺序问题](http://www.cnblogs.com/OCaml/archive/2012/06/18/2554086.html)
