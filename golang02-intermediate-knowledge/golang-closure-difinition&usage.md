## 闭包 ---closure

1. 概念：
    + 闭包不是什么新奇的感念，它早在高级语言开始发展的年代就产生了。闭包（Closure）是词法闭包（Lexical Closure）的简称。对比报的具体定义有很多说法，答题可以分为两类：

        + 一种说法认为闭包是符合一定条件的函数，不如这样定义闭包：闭包是财气词法上下文中引用了自由变量的函数。

        + 另一种说法是：不报是有函数和与其相关的引用环境组合而成的实体。比如这样的定义：在实现深约束时，需要创建一个能显示表示引用环境的东西，并将它与相关的子程序捆绑在一起，这样捆绑起来的整体被称为闭包。函数+引用环境 = 闭包

    + 上面的定义，一个认为闭包是函数，另一个认为闭包是函数和引用环境组成的整体。显然，第二种说法更确切。闭包知识在形式和表现上像函数，但实际上不是函数。

        + 函数是一些可以执行的代码，这些代码在函数北定以后就确定了，不会在执行时发生变化，所以一个函数只有一个实例

        + 闭包在运行时可以有多个实例，不同的引用环境和相同的函数组合可以产生不同的实例。

    + 闭包在某些编程语言中被简称为：lanbda表达式

    + 函数本身不存储任何信息，只要与引用环境借号后形成闭包才具有“记忆性”。函数是编译器静态的概念，而闭包是运行期动态的概念。

    + 对象是富有行为的数据，而不报是富有数据的行为。

2. 闭包的价值

    (1).加强模块化

    + 闭包有益于模块化编程，它能以简单的方式开发娇小的模块，从而提高开发速度和程序的可复用性。和没有使用必报的程序相比，使用闭包可将模块划分的更小。

    + 比如我们要计算一个数组中所有数字的和，这只需要循环遍历数组，把遍历到的数字加起来就行了。 如果现在要计算所有元素的乘积呢？要打印所有元素呢？解决这些问题都要对数组进行遍历，如果是在不支持闭包的语言中，我们不得不一次又一次重复的写循环语句。二这在支持必报的语言中是不不要的。这种处理方法多少有点像回调函数，不过要比回调函数写法更简单，功能更强大。

    (2). 抽象

    + 闭包是数据和行为的组合，这使得闭包具有较好的抽象能力。

    (3). 简化代码

3. 一个编程语言需要哪些特性来支持闭包呢？

    + 函数是一价值，及函数可以作为另一个函数的返回值或参数，还可以作为一个变量的值。

    + 函数可以嵌套定义，即在一个函数内部可以定义另一个函数。

    + 允许定义匿名函数

    + 可以捕获引用环境，并把引用环境和函数代码组成一个可调用的实体。

4. 案例代码：

    (1).没有使用闭包进行计算的代码：

    ```go
    package main
    //不用闭包实现累加计数器函数？？？
    import "fmt"

    func main(){
        for i:=1;i<10;i++ {
            fmt.Printf("i=%d \t",i)
            fmt.Pringln(add(i))
        }
    }

    func add (num int)int{
        sum := 0
        sum += num
        return sum
    }

    /*
    运行结果：
    i=0 0
    i=1 1
    ...
    i=9 9
    */
    ```
    #### 结论：不能实现累加计数函数

    (2).使用闭包实现累加计数器函数：

    ```go
    package main

    import "fmt"

    func main(){
        result：= adder()
        for i:=0;i<=5;i++{
            fmt.Printf("i=%d \t",i)
            fmt.Println(result(i))
        }
    }
    //用闭包实行计数器函数
    func adder() func(int)int {
        sum := 0
        result:= func(num int)int {
            sum += num
            return sum
        }
        return result
    }
    /*
    输出结果：
    i= 0  0
    i= 1  1
    i= 2  3
    i= 3  6
    i= 4  10
    */
    /*
    将adder（）中定义的sum用一个匿名函数包裹形成闭包，并把匿名函数作为返回值返回，这样被包裹的变量sum就不会被清除
    */
    ```



[Previous](golang-anonymousfunction&back-to-the-calling.md)

[Next](golang-closure-case.md)

[返回本章目录](golang-intermediate-knowledge.md)