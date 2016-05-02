---
title: go-import
tags: [go, import]
date: 2015-09-23 11:23:32
---

# 正则文法

    ImportDecl       = "import" ( ImportSpec | "(" { ImportSpec ";" } ")" ) .
    ImportSpec       = [ "." | PackageName ] ImportPath .
    ImportPath       = string_lit .

# 导入路径(ImportPath)

-   相对路径

```go
import "./test"
```

-   绝对路径(`gopath`)

```go
import "fmt"
```

# 包名(PackageName)


-   `.`

```go
import . "fmt"
```

这样导入后,在使用的时候无须包名

-   `_`

```go
import _ "github.com/go-sql-driver/mysql"
```

不直接使用该包内的导出标识符

-   `别名`

```go
import f "fmt"
```

通过别名访问("f.Println")

-   默认形式

```go
import "fmt"
```


# 参考

1.  <https://golang.org/ref/spec#Import_declarations>
