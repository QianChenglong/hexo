---
title: CGI环境变量列表
categories: [CGI]
tags: [CGI, 环境变量]
date: 2015-04-01 09:48:58
---

| 键                | 值                                                 |
|-------------------+----------------------------------------------------|
| DOCUMENT_ROOT     | http服务器根目录                                   |
| GATEWAY_INTERFACE | CGI版本                                            |
| HTTP_COOKIE       | COOKIE值(若存在的话)                               |
| HTTP_HOST         | 尝试获取的页面所在服务器的主机名                   |
| HTTP_USER_AGENT   | 客户端代理类型(浏览器类型)                         |
| QUERY_STRING      | GET请求中的查询字符串                              |
| REMOTE_ADDR       | 客户端IP                                           |
| REMOTE_HOST       | 客户端主机名(需要开启reverse-name-lookup)          |
| REMOTE_PORT       | 客户端连接服务器的端口                             |
| REQUEST_METHOD    | 请求方法(GET，POST)                                |
| REQUEST_URI       | URL中去除主机名的部分(相对于服务器的document root) |
| SCRIPT_FILENAME   | 访问资源在服务器中的完全路径名                     |
| SCRIPT_NAME       | 访问资源的路径,URL中的路径部分                     |
| SERVER_ADDR       | 服务器IP                                           |
| SERVER_ADMIN      | 服务器管理员邮箱                                   |
| SERVER_NAME       | 服务器域名                                         |
| SERVER_PORT       | 服务器监听端口                                     |
| SERVER_PROTOCOL   | 服务器http协议版本                                 |
| SERVER_SOFTWARE   | 服务器软件名称                                     |

# 示例

```
http://localhost/cgi-bin/debug/print_all?a

Environment
COMSPEC: C:\Windows\system32\cmd.exe
DOCUMENT_ROOT: E:/Work/Project/WifiClient/branches/br_ZSAC_v1.0.11_r565/src/httpd/www
GATEWAY_INTERFACE: CGI/1.1
HTTP_ACCEPT: text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,*/*;q=0.8
HTTP_ACCEPT_ENCODING: gzip, deflate, sdch
HTTP_ACCEPT_LANGUAGE: en-US,en;q=0.8,zh-CN;q=0.6,zh;q=0.4
HTTP_CONNECTION: keep-alive
HTTP_COOKIE: CNZZDATA1253757582=110588724-1425953082-%7C1427333981
HTTP_DNT: 1
HTTP_HOST: localhost
HTTP_USER_AGENT: Mozilla/5.0 (Windows NT 6.1; WOW64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/41.0.2272.101 Safari/537.36
PATH: C:\Program Files (x86)\Microsoft Visual Studio 10.0\VSTSDB\Deploy;C:\Program Files (x86)\Microsoft Visual Studio 10.0\Common7\IDE\;C:\Program Files (x86)\Microsoft Visual Studio 10.0\VC\BIN;C:\Program Files (x86)\Microsoft Visual Studio 10.0\Common7\Tools;C:\Windows\Microsoft.NET\Framework\v4.0.30319;C:\Windows\Microsoft.NET\Framework\v3.5;C:\Program Files (x86)\Microsoft Visual Studio 10.0\VC\VCPackages;C:\Program Files (x86)\HTML Help Workshop;C:\Program Files (x86)\HTML Help Workshop;C:\Program Files (x86)\Microsoft SDKs\Windows\v7.0A\bin\NETFX 4.0 Tools;C:\Program Files (x86)\Microsoft SDKs\Windows\v7.0A\bin;C:\Windows\system32;C:\Windows;C:\Windows\System32\Wbem;C:\Windows\System32\WindowsPowerShell\v1.0\;C:\Program Files\TortoiseSVN\bin;d:\Program Files (x86)\Git\cmd;E:\OS\Windows\lnk;E:\OS\Windows\bin;E:\Work\bin;E:\Soft\pandoc\bin\pandoc-1.12.4;D:\Program Files (x86)\Git\bin\;E:\Soft\cmake\bin\cmake-3.1.0-rc2-win32-x86\bin;E:\Soft\Doxygen\bin\doxygen-1.8.7\bin;E:\Soft\GraphViz\bin\graphviz-2.39.20140813\bin;C:\Python27-32\Scripts;E:\Soft\MinGW\bin\MinGW-w64-builds\x64-4.8.1-posix-seh-rev5\mingw64\bin;C:\Python27-32
PATHEXT: .COM;.EXE;.BAT;.CMD;.VBS;.VBE;.JS;.JSE;.WSF;.WSH;.MSC;.py;.lnk
QUERY_STRING: a
REMOTE_ADDR: 127.0.0.1
REMOTE_PORT: 50252
REQUEST_METHOD: GET
REQUEST_URI: /cgi-bin/debug/print_all?a
SCRIPT_FILENAME: E:/Work/Project/WifiClient/branches/br_ZSAC_v1.0.11_r565/src/httpd/cgi-bin/debug/print_all
SCRIPT_NAME: /cgi-bin/debug/print_all
SERVER_ADDR: 127.0.0.1
SERVER_ADMIN: [no address given]
SERVER_NAME: localhost
SERVER_PORT: 80
SERVER_PROTOCOL: HTTP/1.1
SERVER_SIGNATURE: 
SERVER_SOFTWARE: Apache/2.2.25 (Win32)
SYSTEMROOT: C:\Windows
WINDIR: C:\Windows
```

# 参考

1.  <http://www.cgi101.com/book/ch3/text.html>
