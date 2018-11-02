## 打印格式化

### （一）通用：

1. %v 值的默认格式表示\(value\)

2. %+v 输出结构体同时会添加字段名

3. %\#v 输出值的Go语法表示

4. %T 输出值的类型（type）

### （二）布尔值

* %t 单词true或false\(true\)

### （三）整数

1. %b 表示为二进制

2. %c 对应的是unicode码值

3. %d 表示为十进制值\(digital\)

4. %8d 表示该整形长度是8，不足8则在数值前补空格。超出8，则以实际长度为准

5. %08 表示该整形长度是8，不足8则在数值前补0。超出8，则以实际长度为准

6. %o 表示为8进制

7. %q 该值对应的单引号括起来的Go语法字符字面值，不要是会采用安全的转义表示（quotation）

8. %x 表示为16进制，使用a-f

9. %X 表示为16进制，使用A-F

10. %U 表示为unicode格式：U+1234，等价于“U+%04X”

### （四）复数和浮点数的两个组分

1. %b 无效书部分、二进制指数的科学计数法，如 -123456p-78；参见strconv。FormatFloat

2. %e （=%.6e）有6位小数部分的科学计数法，如 1234.4564+78

3. %E 科学计数法，如 1234.4564+78

4. %f （=%.6f）有6位小数，如：123.456123 float型数值

5. %F 等价于%f

6. %g 根据实际情况蚕蛹%e或%f格式（以获得更简洁、准确的输出）

7. %G 根据实际情况蚕蛹%E或%F格式（以获得更简洁、准确的输出）

### （五）字符串和\[\]byte

1. %s 直接输出字符串或\[\]byte \(string\)

2. %q 该值对应的双引号快扩起来的Go语法字符串字面值，必要时会采用安全的转义表示

3. %x 每个字节用两字符十六进制数表示（使用a-f）

4. %X 表示为16进制，使用A-F

### （六）指针

1. %p 表示为十六进制，并加上前导0x point

   。。。。。。。。

### 例程：

```go
package main

import "fmt"

type Point struct {
    x, y int
}    

func main() {
    //通用
    str := "stever"
    fmt.Printf("%T,%v\n", str, str)      p := Point{1, 2}
    fmt.Printf("%T,%v\n", p, p)

    var a rune = '一'
    fmt.Printf("%T,%v\n", a, a)
    //  布尔
    fmt.Printf("%T,%t\n", true, true)
    //  整形
    fmt.Printf("%T,%d \n", 123, 123.234) //错误
    fmt.Printf("%T,%5d \n", 123, 123)
    fmt.Printf("%T,%0d \n", 123, 12356)
    fmt.Printf("%T,%b \n", 123, 123)
    rst := fmt.Sprintf("%b,\n", 123)
    fmt.Println(rst)
    fmt.Printf("%x \n", 123) //转换成16进制
    fmt.Printf("%X \n", 123) //转换成16进制
    fmt.Printf("%U \n", 'a') //转换成unicode ASXII
    fmt.Printf("%U \n", '一') //转换成unicode ASXII
    //  浮点
    fmt.Printf("%f \n", 123.1)        //转换成unicode ASXII
    fmt.Printf("%.2f \n", 123.1)      //转换成unicode ASXII
    fmt.Printf("%e \n", 123.1)        //转换成科学计数法
    fmt.Printf("%10e \n", 123.123567) //转换科学计数法
    //  字符串
    fmt.Printf("%s \n", "学习Go语言")
    fmt.Printf("%q \n", "学习Go语言")
    arr:=[3]byte{65,66,67}
    fmt.Printf("%T,%s\n",arr,arr)
    fmt.Printf("%T,%p\n",arr,&arr)
}
```

[返回上一级](./golang-basic-knowledge.md)

[Next](golang-const.md)