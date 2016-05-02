---
title: 编译安装google-C++-test-framework
categories: [单元测试]
tags: [单元测试, 编译]
date: 2015-01-07 17:12:00
---

# 环境

-   VS2010
-   cmake-3.1.0
-   gtest-1.7.0

# 编译

-   下载[官网](https://code.google.com/p/googletest/)，解压

-   新建`build`目录，并进入

-   生成`Makefile`

    -   静态库(默认C++运行库为静态链接)

            cmake -G "NMake Makefiles" ..

    -   静态库，C++运行库采用动态链接

            cmake -G "NMake Makefiles" -Dgtest_force_shared_crt=ON ..

    -   动态库(默认C++运行库为动态链接)

            cmake -G "NMake Makefiles"  -DBUILD_SHARED_LIBS=ON ..

注：

    -   编译示例，`-Dgtest_build_samples=ON`

-   编译

        nmake

# 注意事项

-   gtest本身的C++运行时库需要和项目保持一致，不然会出现类似`msvcprtd.lib(MSVCP100D.dll) : error LNK2005: already defined in gtestd.lib(gtest.obj)`！

# 参考

1.  <http://stanlearnswindows.blogspot.jp/2010/06/msvcprtdlibmsvcp100ddll-error-lnk2005.html>
1.  <http://www.cnblogs.com/ShaneZhang/p/3480502.html>
1.  <http://msdn.microsoft.com/zh-cn/library/abx4dbyh(v=vs.100).aspx>
