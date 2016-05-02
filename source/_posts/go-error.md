---
title: go-error
tags: [go, error]
date: 2015-09-24 14:37:08
---

# 要点

-   `error`是一个预定义的`interface`

    ```go
    type error interface {
        Error() string
    }
    ```

-   最常用的一个实现是`errors`中的`errorString`

    ```go
    errors.New("error message")
    ```

-   在`fmt`包中,通过反射得知是`error`类型时,则调用`error() string`方法

-   在`fmt`包中,提供了`Errorf(format string, a ...interface{}) error`来方便错误信息输出

-   在精细化的情况下(调用者需要知道错误(该错误是重新定义的的,包含其他信息)的详细信息,不只是错误字符串),
    这时可以通过**类型断言**来单独处理指定错误

    ```go
    if err := dec.Decode(&val); err != nil {
        if serr, ok := err.(*json.SyntaxError); ok {
            line, col := findLine(f, serr.Offset)
            return fmt.Errorf("%s:%d:%d: %v", f.Name(), line, col, err)
        }
        return err
    }
    ```

    ```go

    _, err := my.DB.Exec(sql)
        if err != nil {
            if driverErr, ok := err.(*mysql.MySQLError); ok { // Now the error number is accessible directly
                if driverErr.Number == 1062 {
                    return errDuplicate
                }
            }
            return &json2.Error{Code: 100, Message: "a"}
        }

    ```

# 参考

1.  <http://blog.golang.org/error-handling-and-go>
