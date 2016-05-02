## 选项

### 功能字符

必须指定1个，可以指定多个，多个可以连在一起，前面的'-'不是必需的

-A
    追加tar文件到一个archive

-r
    追加files到archive

-c
    创建新的archive

-x
    解包并解压

-t
    查看包内容

###选项

-a
    根据包名字后缀自动选择相应的压缩程序

-f archive

    指定包名字，打包就是目的包名字，解包就是要解包的包名字

-C dir
    解包到指定目录

-p
    保留文件权限，属性信息

-P
    不拿掉绝对路径前面的'/'

### 压缩选项

-z
    gzip

-j
    bzip2

-J
    xz

## 实例

-   解压，解包

        tar xf *.tar.gz

-   将当前目录打包，压缩

        tar vczf tar.tar.gz .

-   解开包中某一个文件

    -   先查看文件

            tar tf tar.tar.gz | grep tar

    -   再解压指定文件

            tar vxzf tar.tar.gz .tar实例.swp

-   给当前目录下，某个文件夹打包压缩

            tar vczf src.tar.gz src
