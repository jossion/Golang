#  if条件判断语句

## （一）语法

1. Go语言中的if语句语法如下：

```go
if bool {
    bool=true 
    fmt.Println("This is true")

}
```

* if 在布尔表达式为true时，其后紧跟的语句块执行，如果为false则不执行。

2. Go语言中if...else语句的语法如下：

```go
if bool {
    bool=true 
    fmt.Println("This is true")
} else {
    boll = false
    fmt.Println("Thi is false")
}
```

3. Go语言中if...else if ...else语句语法如下

```go
if bool {
    bool=true 
    fmt.Println("This is true")
} else if{
    bool = false
    fmt.Println("This is false")
}else {
    fmt.Println("choose other")
}
```

## （二）if语句注意事项

1. **不需使用括号将条件语句包含起来**

2. **大括号`{}`必须存在，即使只有一行语句**

3. **左括号`{`不许在`if or else`的用一行**

4. **在`if`只后，条件语句之前，可以添加变量初始化语句，使用`;`进行分隔**

## （三）案例

1. 用if语句判断数据的奇偶性

```go
package main

import “fmt”

func main() {
    EvenOdd()
}



func EvenOdd() {
    num := 30
    if num%2 == 0 {
        fmt.Println(num, "偶数")
    } else {
        fmt.Println(num, "奇数")

    }

}
```

```
输出结果：
30 偶数

Process finished with exit code 0
```

2. 判断学生平均成绩。有：优、良、中、及格、不及格

只用`if`语句

```go
package main

import “fmt”

func main() { 
    ScoreMark1()
}

func ScoreMark() {
    score := 78
    if score >= 90 {
        fmt.Println("优秀")
    }
    if score >= 80 && score < 90 {
        fmt.Println("良好")
    }
    if score >= 70 && score < 80 {
        fmt.Println("中等")
    }
    if score >= 60 && score < 70 {
        fmt.Println("及格")
    }
    if score < 60 {
        fmt.Println("不及格")
    }
}
```

```
输出结果：

中等

Process finished with exit code 0
```

3. 用 `if...else if`

```go
package main

import “fmt”

func main() { 
    ScoreMark()
}

func ScoreMark()  {
    score:=81
    if score>=90{
        fmt.Println("优秀")
    }else if score>=80{
        fmt.Println("良好")
    }else if score>=70{
        fmt.Println("中等")
    }else if score>=60{
        fmt.Println("及格")
    }else {
        fmt.Println("不及格")
    }
```

```
输出结果：

良好

Process finished with exit code 0
```

4. 用`if ...else` 嵌套

```go
package main

import “fmt”

func main() { 
    ScoreMark()
}

func ScoreMark()  {
    score:=98
    if score>=60{

        if score>=70{
            if score>=80{
                if score>=90{
                    fmt.Println("优秀")
                }else {
                    fmt.Println("良好")
                }
            }else {
                fmt.Println("中等")
            }
        }else {
            fmt.Println("及格")
        }
    }else {
        fmt.Println("不及格")
    }
```

```
输出结果：

优秀

Process finished with exit code 0
```


[返回目录](../golang-controller.md) [Next](golang-controller-switch.md)
