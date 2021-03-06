## 函数

(一). 什么是函数

1. 函数是组织好的、可重复使用的执行特定任务的代码块。它可以提高应用程序的模块性和代码的重复利用率。

2. Go语言支持普通函数、匿名函数和闭包，从设计上对函数进行了优化和改进，让函数使用起来更加方便。

3. Go语言的函数属于一等公民（first-class）:

    * 函数本身可以作为值进行传递；

    * 支持匿名函数和闭包（closure）;

    * 函数可以满足接口。

(二). 声明函数

1. 函数声明的作用

    * 普通函数需要先声明才能调用，一个函数的声明包括参数和函数名。编译器通过声明才能了解函数应该怎样在调用代码和函数体之间传递参数和返回值。

2. 语法格式：

        func name(参数列表) （返回值列表）{
        //函数体
        }

    ```go
    func funcname(parametename type,parametename type ...) (output1 type,output2 type ...){
        //逻辑代码
        //返回多个值
        return value1,value2 ...
    }
    ```

3. 函数定义解析：

* func： 函数关键字

    * 函数由func 开始声明

* funcname: 函数名

    * 函数名和参数列表一起构成了函数签名。

    * 函数名由字母、数字和下划线组成。函数名的第一个字母不能为数字。在同一个包内，函数名称就不能重名。

* Parametename：参数列表

    * 参数就像是一个占位符，定义函数是的参数叫做形式参数，简称：形参，形参变量是函数的局部变量，当函数被调用时，你可以将值传递给这个参数，这个值被称为实际参数，简称：实参。

    * 参数列表指定的是参数类型、顺序、及参数个数；

    * 参数是可选的，也就是说函数可以不包括参数

    * 参数类型的简写：

        * 在参数列表中，如果有多个参数变量，则以 `,`分隔；如果相邻变量是同类型，则可以将类型省略。

        * 例如：func add (a,b int) {}

    * Go 语言的函数支持可变参数，接收变参的函数有着不定数量的参数。func myfunc(arg ... int){};arg...int是告诉Go这个函数接收不定数量的参数。注意：这些参数的类型全部是int。。在函数体中，变量arg是一个int的slice。

* output1 type，output2 type: 返回值列表。

    * Go语言的函数可以返回多个值。

    * 返回值可以是：返回数据的数据类型，或者是：变量名+数据类型 

    * 如果只要一个返回值且不生命返回值变量，那么可以省略包括返回值的括号。

* 函数体：函数定义的代码集合，是能够被重复调用的代码片段

(三). 变量作用域

1. 概述

* 作用域是变量、常量、类型、函数的作用范围。

* Go语言中的变量可以在三个地方声明：

    * 函数体内定义的变量称为局部变量

    * 函数体外定义的变量称为全局变量

    * 函数体定义的参数称为形式参数

2. 局部变量

    * 在函数体内声明的变量是局部变量，它们的作用域只在函数体内，参数和返回值变量也是局部变量

3. 全局变量

* 在函数体外声明的变量称之为全局变量，全局变量可以在整个包甚至外部包（被导出后）使用。

全局变量可以在任何函数中使用。Go语言程序中全局和局部变量名称可以相同，但是函数体内的局部变量会被优先

4. 形式参数

* 形式参数会作为函数的局部变量来使用

5. 案例分析

```go
package main

import "fmt"

//声明全局变量
var a int = 7
var b = 9

func main()  {
	a,b,c :=10,20,0
	fmt.Printf("main()函数中 a = %d\n",a)
	fmt.Printf("main()函数中 b = %d\n",b)
	fmt.Printf("main()函数中 c = %d\n",c)
	c=sum(a,b)
	fmt.Printf("main()函数中 c = %d\n",c)
}

func sum(a,b int)int  {
	return a+b
}
```
[Previous](../golang01-basic-knowledge/golangController/golang-controller-break&continue&goto.md)

[Next](golang-func-as-a-value.md)

[返回本章目录](golang-intermediate-knowledge.md)