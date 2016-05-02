---
title: vim-执行外部程序
categories: [vim]
tags: [vim]
date: 2015-03-17 15:59:23
---

# windows

## 版本1

```vim
exe '!cmd'
```

### 优点

-   达到初步要求

### 缺点

-   vim被阻塞

-   当文件名包含非ASCII字符，且vim内部编码(utf-8)与shell编码(gbk)不一致时，报错：找不到该文件

-   不支持参数化，不能方便复用

-   不支持传入参数

## 版本2

```vim
exe printf('!"%s"', filename)
```

### 优点

-   参数化


## 版本3

```vim
exe iconv(printf('%s "%s" "%s"',
            \ g:cmd_runner,
            \ b:interpreter,
            \ b:exec_filename,)
            \ 'utf-8', 'chinese')
```

### 优点

-   支持中文

## 版本4

```vim
exe '!start cmd'
```

### 优点

-   非阻塞执行

### 缺点

-   执行控制台一闪而过，无法看见程序输出

## 版本5

```
exe iconv(printf('%s "%s" "%s"',
            \ g:cmd_runner,
            \ b:interpreter,
            \ b:exec_filename,)
            \ 'utf-8', 'chinese')

```

### 优点

-   控制台显示

### 缺点

-   显示了命令字符串

## 版本6

```vim
exe iconv(printf('%s "%s" "%s" %s',
            \ g:cmd_runner,
            \ b:interpreter,
            \ b:exec_filename,
            \ b:args),
            \ 'utf-8', 'chinese')
```

#说明

## 前置代码

-   `.vimrc`

```vim
fun! IsWin()
    return has("win32") || has("win64")
endf

if IsWin()
    let g:cmd_runner = '!start E:/OS/Windows/bin/cb_console_runner.exe'
else
    let g:cmd_runner = '!gnome-terminal -x bash -c'
endif
```

-   `ftplugin/python.vim`

```vim
let b:python_version = '27-32'
let b:args = ''
let b:exec_filename = expand("%:p")
if IsWin()
    let b:interpreter = printf('c:/python%s/python.exe', b:python_version)
else
    let b:interpreter = 'python2 -B'
endif
```
