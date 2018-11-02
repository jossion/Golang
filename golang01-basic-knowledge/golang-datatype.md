## 数据类型

- 基本数据类型（原生数据类型）：整形、浮点型、布尔型、字符串、字符（byte、rune）
- 复合数据类型（派生数据类型）：指针（pointer）、数组（Array）、切片（slice），映射（map）、函数（function）、结构体（struct）、通道（channel）

### （一）整形
 整形分两大类：

-  按长度分：int8,int16,int32,int64,int

-  无符号整形：unit8,uint16,uint32,uint64,uint

-  其中uint8就是byte型，int16对应C语言的short型，int64对应C语言long型。


|序号|类型和描述|
|:---:|:---|
|1|uint8 无符号8位整形（0-255）【2的8次方】|
|2|uint16 无符号16位整形（0-65535）【2的16次方】|
|3|uint32 无符号32位整形（0-4294967395）【2的32次方】|
|4|uint64 无符号64位整形（0-18446744073709551615）【2的64次方】|
|5|int8 有符号8位整形 （-128-127）|
|6|int16 有符号16位整形 （-32768-326767）|
|7|int32 有符号32位整形 （-2147483648-2147483647）|
|8|int64 有符号32位整形 （-9223372036854775808-9223372036854775807）|

还有其他数字类型

|序号|类型和描述|
|:---:|:---|
|1|byte 类似uint8|
|2|rune 类似int32|
|3|uint 32或64位，取决于运行的宿主机的位数|
|4|int 与uint一样大小|
|5|uintptr 无符号整形，用于存放一个指针|


### （二）浮点型

* Go语言支持4种浮点型数：float32 float64 complex64（32位实数和虚数）complex123（64位实数和虚数）

* float32的最大范围是3.4e38，用常量定义是：math.MaxFloat32

* float64的最大范围是1.8e308，用常量定义是：math.MaxFloat64
  
### （三）布尔型

* bool有两个值  true和flase

### （四）字符串

* 字符串在Go语言中是一基本数据类型出现的，是用字符串就像是使用其他原生基本数据int float32 float65 bool 一样

* 字符串中可以使用转移符：

    * \r 回车符return，返回行首

    * \n 换行符new line，直接跳到下一行的同列位置

    * \t 制表符TAB

    * \' 单引号

    * \" 双引号

    * \\ 反斜杠

* 定义多行字符串

    * **双引号书写字符串被称为字符串字面量，这种字面量不能跨行**

    * 多行字符串需要使用“`”，多用于内嵌源码和内嵌数据

    * 在反引号中的所有代码不会被编译器识别，而只是作为字符串的一部分

### （五）字符

字符串中的每一个元素叫做“字符”，**定义字符使用单引号**。Go语言中的字符有两种：

1. byte型：其实是uint8的别名，代表一个ASCII码的一个字符

2. rune型：其实就是int32.代表一个UTF-8字符。等需要处理中文等unicode字符集时需要用到rune型。

   * var a byte = 'a'

   * var b tune = '一'

例程：

```go
package main

import (
    "fmt"
)
func main(){
    a := 100
    var b byte = 100
    var c rune = 200
    fmt.Printf("%T,%v\n",a,a)
    fmt.Printf("%T,%v\n",b,b)
    fmt.Printf("%T,%v\n",c,c)
    //---------------------------
    var d byte = 'a'
    var e rune = 'b'
    fmt.Printf("%T,%v\n",d,d)
    fmt.Printf("%T,%v\n",e,e)
    //------------------------

}

//输出结果：
int ,100
uint8,100
int32,200
//------------------
uint8,97
int32,98
```

[返回上一级](./golang-basic-knowledge.md)

[Next](golang-fmtprint.md)