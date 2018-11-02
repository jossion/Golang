## 匿名函数

1. 概念：
    + Go语言支持匿名函数，即在需要使用函数时再定义函数；匿名函数没有函数名只有函数体，函数可以被作为一种类型被赋值给变量，匿名函数也往往页变量的方式被传递。

    + 匿名函数经常被用于实现回调函数、闭包等

2. 定义格式

    ```
    func (参数列表)（返回值列表）{
        //函数体
    }
    ```

3. 定义匿名函数：

    (1).在定义时调用匿名函数
    
    ```go
    package main

    import "fmt"

    func main () {
        //1.定义时调用无参匿名函数
        func(data int) {
            fmt.Println("Hello",data)
        }(100)

        //2.定义时调用有参匿名函数
        result := func(data float64) float64{
            return math.Sqrt(data)
        }(250)
        fmt.Println("参数平均值：",result)
    }
    ```

    (2). 将匿名函数赋值给变量，需要时再调用

    ```go
    package main

    import "fmt"

    func main () {
        
        f := func(data string) string{
            return data
        }
        fmt.Println(f("欢迎学习Go语言"))
    }
    ```

4. 匿名函数的用法---回调函数

    ```go
    package main

    import (
        "fmt"
        "math"
    )
    type myFuncs func(float64) string

    func main(){
        //定义一个slice，对其中的数据进行求平方根和求平方的运算
        //求平方根
        arr := []float64{1, 9, 16, 25, 30}
	    result := Filterslice(arr, func(val float64) string {
		    val = math.Sqrt(val)
		    return fmt.Sprintf("%.2f", val)
	    })
	    fmt.Print(result)
	    //求平方
	    result = Filterslice(arr, func(val float64) string {
            val = math.Pow(val,2)
            return fmt.Sprintf("%.2f", val)
	    })
	    fmt.Print(result)
    }

    //遍历切片，对其中元素进行运算
    func Filterslice(arr []float64, f myFuncs) []string {
	    var result []string
	    for _, value := range arr {
		result = append(result, f(value))
        }
        return result
    }
    ``` 
#### 说明:匿名函数回调使用时，定义的函数和匿名函数，但没有对匿名函数的具体方法做定义。也就是说，这类函数在调用是用户可以随机的定义此函数的函数体






[Previous](golang-func-as-a-value.md)

[Next](golang-closure-difinition&usage.md)

[返回本章目录](golang-intermediate-knowledge.md)