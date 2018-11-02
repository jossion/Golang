## 常量

### （一）声明方式

1. 相对于变量，常量是恒定比变得值，在程序运行时，不会被修变。

2. 常量中的数据类型**_只可以是：布尔型、数字型和字符串_**；

3. 敞亮的定义格式：

    + const 标识符 [类型] = 值

    + 可以省略类型说明符 [type]，因为编译器可以根据常量的值来自动推断

        + 显示类型定义： `const B string = "Steven"`

        + 隐式类型定义： `const C = "Steven"`

4. 多个相同类型的声明可以简写为：

    + `const width,height = value1,value2`

5. 常量定义后未被使用，不会在编译时出错。

### （二）常量用于枚举（常量组）

+ 例如以下格式：

    const(
        Unknown = 0
        Female = 1
        Male = 2
    )

+ 常量组中如果不指定类型和初始值，则与上一行非空常量的值相同：

    const(
        a = 10
        b
        c
    )

    打印输出时得到：10,10,10


### （三）iota

1. iota，特殊常量值，是一个系统定义的可以被编译器修改的常量值。**_iota经常使用在常量组中；iota出现时的值被系统默认赋值为该常量出现在常量组中的序列号减一_**

2. 在每一个const关键字出现时 iota将被重置为 0 ，然后每出现一个常量，iota所代表的数值就会自动加 1。iota可以理解成常量组中的计数器，不论该常量的值是什么，只要有有个常量，那么iota就加1 。

3. iota可以被用作枚举值：

    ```go
    package main

    import "fmt"

    const(
        a = iota
        b = iota
        c = iota
    )
    const(
        a1 = iota
        b1 
        c1 
    )

    func main(){
        fmt.Println(a,b,c)
        fmt.Println(a1,b1,c1)
        const (
            i = 1 << iota //表示为：1* 2^iota 此时 iota=0 输出应为：1
            j = 3 << iota // 3*2^iota次方  此时 iota=1 输出应为：6
            k = 3 << iota // 3*2^iota次方  此时 iota=2 输出应为：12
            l = 3 << iota // 3*2^iota次方  此时 iota=3 输出应为：24
            )
        const (
            a2 = `一`   //分析：``包裹的汉字一是个数值型 是unicode码中的19968，所以输出应为19968
            b2          // b2=a2  输出19968
            c2 = iota   // c2=iota -->2 ,iota=常量序号-1
            d2          // d2=c2+1 -->3
        )
    }
        
    /*
    输出：0,1,2
          0,1,2
    第一个iota等于0 ，每当iota在新的一行被使用时，它的值都会自动加1；所以：a=0,b=1,c=2
    */
    ``` 
[返回上一级](./golang-basic-knowledge.md)

[Next](golang-operator.md)