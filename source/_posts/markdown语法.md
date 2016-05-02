---
title: markdown语法
categories: markdown
tags: [markdown]
date: 2014-12-19 11:42:19
---

## 文件名后缀

采用*.md

<!--more-->

## 区块元素

### 标题

- Atx语法格式(**采用这种**)

    用1~6个'#'来表示1～6阶标题

        # 一级标题
        ## 二级标题

- Setext语法格式

    用'='或'-'在文字下部标注

        大标题
        ======
        小标题
        ------

### 段落

一个或多个连续的文本行组成，以空行(**空白符组成的行**)作为分界符

理解：在markdown文件中，一个段落中的换行符和多个连续的空白符都无效，所以若是需
要强制换行(类似与在html文件中插入`<br \>`标签)，需要在该行尾输入2个以上的空格
。

        这是
    一个段落

### 列表

-   无序列表

    项目标记[-,*,+] + 空格(总共1个TAB)，所以最好的方式是，**- 3个空格**(按下TAB键即可)

        -    足球
        -    篮球
        或
        *    足球
        *    篮球
        或
        +    足球
        +    篮球

-   有序列表

    项目标记[-,*,+] + . + 空格(总共1个TAB)，所以最好的方式是，**1. 2个空格**(按下TAB键即可)

    -   用一个数字加空格标记

            1.  起床
            1.  刷牙
            1.  洗脸

    -   数字的顺序没有作用，但最好从`1`开始，有些编译器支持start属性

-   列表项目含有多个段落(**记得段落间需要空行！**)

    该段落比列表项目多缩进1次

        -   吃饭

            先拿筷子，在吃饭，
            然后记得擦嘴！

- 列表项目含有块引用(**同段落处理一样**)

        *   A list item with a blockquote:

            > This is a blockquote
            > inside a list item.

- 列表项目含有代码

    代码比列表项目多缩进2次

        -   吃饭

            段落

                getChopsticks();
                eat();
                cleanMouse();

### 代码区块

比段落多缩进1次，连续相同缩进的行构成代码区块

    吃饭

        getChopsticks();
        eat();
        cleanMouse();

### 引用

以'>'加一个空白加文字组成

- 只在整个段落的第一行最前面加上 >

        > This is a blockquote with two paragraphs. Lorem ipsum dolor sit amet,
        consectetuer adipiscing elit. Aliquam hendrerit mi posuere lectus.
        Vestibulum enim wisi, viverra nec, fringilla in, laoreet vitae, risus.

        > Donec sit amet nisl. Aliquam semper ipsum sit amet velit. Suspendisse
        id sem consectetuer libero luctus adipiscing.

- 区块引用可以嵌套（例如：引用内的引用），只要根据层次加上不同数量的 > ：

        > This is the first level of quoting.
        >
        > > This is nested blockquote.
        >
        > Back to the first level.

- 引用的区块内也可以使用其他的 Markdown 语法，包括标题、列表、代码区块等：

        > ## 这是一个标题。
        >
        > 1.   这是第一行列表项。
        > 2.   这是第二行列表项。
        >
        > 给出一些例子代码：
        >
        >     return shell_exec("echo $input | $markdown_script");

### 分隔线

3个以上的'_'或'='或'*'

    吃饭
    ---
    学习

## 内联元素

### 链接

-   行内式

    -   万维网资源：

            [HOME](www.qianchenglong.com "TITLE")

    -   要链接到本机资源，可以使用相对路径：

            [localfile](Markdown语法简记.mkd)

-   参考式(**多链接时，优先使用！**)

    参考式链接[Baidu][Baidu_ID]

        [Baidu_ID]: www.baidu.com 'TITLE'

### 自动链接

用'<'和'>'包含起来(**不需要描述链接时采用**)

    <http://www.google.com>
    <qian_cheng_long@163.com>

### 图片(地址指定同链接一样)

    ![图片描述]( 图片地址 "TITLE" )

### 强调

用'*'(**优先采用**)或'_'包含起来的文字，1个等于`<em />`，2个等于`<strong />`

    _吃饭_
    **学习**

### 行内代码

用'`'包含起来

    这是代码`puts("hello world")`
