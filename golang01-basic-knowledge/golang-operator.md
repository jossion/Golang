## Go语言运算符

运算符用于程序运行时执行数学或逻辑运算。

Go语言内置的运算符有：

+ 算数运算符

+ 关系运算符

+ 逻辑运算符

+ 位运算符

+ 赋值运算符

+ 其他运算符

### （一）算数运算符（Arihtmetic operator）

下表列出了所有Go语言的算数运算符；假定A=10、B=20

|运算符|描述|实例|结果|
|:---|:---|:---|:---|
|-|相加|A + B输出结果：|30|
|+|相减|A - B输出结果：|-10|
|*|相乘|A * B输出结果：|200|
|/|相除|B / A输出结果：|2|
|%|求余数|B / A输出结果：|0|
|++|自增|A++ 输出结果：|11|
|--|自减|A-- 输出结果：|9|

### （二）关系运算符（Relational operator）

下表列出了所有Go语言的关系运算符；假定A=10、B=20

|运算符|描述|实例|结果|
|:---|:---|:---|:---|
|==|检查两个值是否相等，如果相等返回True否则返回False。|A==B |False|
|!=|检查两个值是否不相等，如果不相等返回True否则返回False。|A!=B |True|
|>|检查左边的值是否大于右边值，如果是返回True否则返回False|A>B|False|
|<|检查左边的值是否小于右边值，如果是返回True否则返回False|A<B|True|
|>=|检查左边值是否大于等于右边值，如果是返回True否则返回False|A>=b|False|
|<=|检查左边值是否小于等于右边值，如果是返回True否则返回False|A>=b|True|

### （三）逻辑运算符（Logical operator）

下表列出了所有Go语言的逻辑运算符；假定A=true、B=false

|运算符|描述|实例|结果|
|:---|:---|:---|:---|
|`&&`|逻辑and运算符。如果两边的操作都是true，则条件true否则false|A&&B|false|
|`||`|逻辑or运算符。如果两边的操作都是true，则条件true否则false|A`||`B|true|
|`！`|逻辑Not运算符。如果两边的操作都是true，则逻辑not条件false否则true|!(A&&B)|true|


### (四)位运算符（Bitwise operator）

位运算符对整数在内存中的二进制位进行操作。

位运算比一般的算数运算速度快，而前可以实现一些算数运算不能实现的功能。如果要开发高效率程序，位运算是必不可少的。位运算符用来对二进制进行操作，包括：按位与（&）、按位或（|）、按位异或（^）、按位左移（<<）、按位右移（>>）.

**假定 A=60；B=13；其二进制数转换为：**

A = 0011 1100
----------------------------
B = 0000 1101
----------------------------

+ A & B = 0000 1100
+ A | B = 0011 1101
+ A ^ B = 0011 0001

|运算符|描述|实例|结果|
|:---|:---|:---|:---|
|`&`|**按位与**运算符`“&”`；功能是将参与运算的两个数对应的二进制位相与|A`&`B|0000 1100|
|`|`|**按位或**运算符`“|”`；功能是将参与运算的两个数对应的二进制位相或|A`|`B|0011 1101|
|`^`|**按位异或**运算符`"^"`是双弩运算符；功能室将参与运算的两个数对用的二进制位相异或，当二进制位相异时，结果为1|A`^`B|0011 0001|
|`<<`|**左移**运算符`"<<"`是双目运算符；左移n位就是乘以2的n次方；其功能把`"<<"`左边的运算数的各二进制位全部左移若干位，由`"<<"`右边的数制定移动的位数，高位丢弃，地位补0|A`<<`B|1111 0000|
|`>>`|**右移**运算符`">>"`是双目运算符；右移n位就是乘以2的n次方；其功能把`">>"`左边的运算数的各二进制位全部右移若干位，由`">>"`右边的数制定移动的位数，高位丢弃，地位补0|A`>>`B|0000 1111|

1. 按位与

+ 按位与（&）：对两个数进行操作，然后返回一个新数，这个数的每个位都需要两个输入数的同一位都为1时才为1。简单地说：同一位同时为1则为1

2. 按位或

+ 按位或（|）：比较两个数，然后返回一个新数，这个数的每一位为1的条件是任意一个数的同一位为1则为1。简单地说：同一位其中一个为1则为1

3. 按位异或

+ 按位异或（^）：比较两个数然后返回一个数，这个数的每个位设为1的条件是两个输入的数的同一位不同则为1，相同则为0。简单说就是：同一位不同是返回1

4. 按位左移（<<）

+ 按二进制形式把所有数字向左移动对应的位数，高位移出（舍弃），低位的空位补 0 。

    4.1 语法格式：

    + 需要移动的数组`<<`移位的次数

    + 例如：`3<<4`,则是将数字3左移4位

    4.2 计算过程：

    + `3<<4`

    + 首先把3转换为二进制数字0000 0000 0000 0000 0000 0000 0000 0011，然后把该数字高位（左侧位）的两个0000 0000 移出，其他数字向左移动4位，最后在低位（右侧位）的两个空位补 0.则得到最终结果是：0000 0000 0000 0000 0000 0000 0011 0000，转换为十进制是48.

    4.3 数学意义：
    + 在数字没有溢出的前提下，对于整数和复数，左移一位都相当于乘以2的1次方，左移n位就相当于乘以2的n次方

5. 按位右移（>>）

+ 按二进制形式把所有数字向右移动对应的位数，低位移出（舍弃），高位的空位补符号位，即整数补 0 ，复数补1 。

    5.1 语法格式：

    + 需要移位的数字`>>`移位次数

    + 例如：11>>2，则是将数字11右移2位

    5.2 计算过程：

    + 11的二进制数是：0000 0000 0000 0000 0000 0000 0000 1011，然后把低位的左后两个数字移除，因为该数字是整数，所以在高位补 0 。则得到的结果是：0000 0000 0000 0000 0000 0000 0000 0010 ；转换为十进制是2

    5.3 数学意义：

    + 右移一位相当于除2，右移n位相当于除以2的n次方


### （五）赋值运算符（Assignment operator）

下表列出了所有Go语言的赋值运算符

|运算符|描述|实例|
|:---|:---|:---|
|`=`|简单的赋值运算符，讲一个表达式的值赋给一个左值|c=a+b,将a+b表达式的结果赋值给c|
|`+=`|相加后再赋值|c `+=` a 等于 c = c + a|
|`-=`|相减后再赋值|c `-=` a 等于 c = c - a|
|`*=`|相乘后再赋值|c `*=` a 等于 c = c * a|
|`/=`|相除后再赋值|c `/=` a 等于 c = c / a|
|`%=`|求余后再赋值|c `%=` a 等于 c = c % a|
|`<<=`|左移后再赋值|c `<<=` 2 等于 c = c << 2|
|`>>=`|左移后再赋值|c `>>=` 2 等于 c = c >> 2|
|`&=`|按位`&=` 后再赋值|c `&= `2 等于 c = c & 2|
|`^=`|按位`^=` 后再赋值|c `^=` 2 等于 c = c ^ 2|
|`|=`|按位`|=` 后再赋值|c `|= 2` 等于 c = c `|`2|
|||| 

### （六）其他运算符

下表列出了所有Go语言的其他运算符

|运算符|描述|实例|
|:---|:---|:---|
|`&`|返回变量存储的地址|&a：将给出变量的实际地址| 
|`*`|指针变量|*a：是一个指针变量| 
||||



以下实例演示各个运算符的用法

```go
package main

import "fmt"

var a = 21.0
var b = 5.0
var c float64

func main() {
	Arithmetic()
	Relational()
	Logical()
	Bitwise()
	Assignment()
}

//运算符Arithmetic
func Arithmetic() {
	c = a + b
	fmt.Printf("第一行 - C的值为a+b：%.2f\n", c)
	c = a - b
	fmt.Printf("第二行 - C的值为a-b：%.2f\n", c)
	c = a * b
	fmt.Printf("第三行 - C的值为a*b：%.2f\n", c)
	c = a / b
	fmt.Printf("第四行 - C的值为a/b：%.2f\n", c)
	//c = a % b
	d := fmt.Sprintf("取模值：%d\n", int(a)%int(b))
	fmt.Printf("第五行 - C的值为a/b的余数： %d\n", int(a)%int(b))
	fmt.Printf("第五行 - C的值为a/b的余数： %s\n", d)
	a++
	fmt.Printf("第六行 -A的自增值为：%.2f\n", a)
	a = 21
	a--
	fmt.Printf("第七行 -A的自减值为：%.2f\n", a)
}

//关系运算符Relational
func Relational() {
	if a == b {
		fmt.Printf("第一行 - a 等于 b\n")
	} else {
		fmt.Printf("第一行 - a 不等于 b\n")
	}
	if a < b {
		fmt.Printf("第二行 - a 小于 b\n")
	} else {
		fmt.Printf("第二行 - a 不小于 b\n")
	}
	if a > b {
		fmt.Printf("第三行 - a 大于 b\n")
	} else {
		fmt.Printf("第三行 - a 不大于 b\n")
	}
	if a <= b {
		fmt.Printf("第四行 - a 小于等于 b\n")
	} else {
		fmt.Printf("第四行 - b小于等于 a\n")
	}
	if a >= b {
		fmt.Printf("第五行 - a 大于等于 b\n")
	} else {
		fmt.Printf("第五行 - b 大于等于 a\n")
	}

}

//逻辑运算符Logical Operator
func Logical() {
	a := false
	b := true
	if a && b {
		fmt.Printf("第一行逻辑值为：true\n")
	} else {
		fmt.Printf("第一行逻辑值为：false\n")
	}
	if a || b {
		fmt.Printf("第二行逻辑值为：true\n")
	} else {
		fmt.Printf("第二行逻辑值为：false\n")
	}
}

//位运算符 Bitwise operator
//包括：按位与（&），按位或（|），按位异或（^）,按位左移（<<）,按位右移（>>）
func Bitwise() {
	fmt.Println(252 & 63)
	fmt.Println(178 | 94)
	fmt.Println(20 ^ 5)
	fmt.Println(3 << 4)
	fmt.Println(11 >> 2)
}

//赋值运算符 Assignment operator包括：（=、 +=、 -=、*=、/=、%=、<<=、>=、&=、^=、|=、）
func Assignment() {
	c = a
	fmt.Printf("第1个C等于：%f\n", c)
	c += a
	fmt.Printf("第2个C等于：%f\n", c)
	c -= a
	fmt.Printf("第3个C等于：%f\n", c)
	c *= a
	fmt.Printf("第4个C等于：%f\n", c)
	c /= a
	fmt.Printf("第5个C等于：%f\n", c)
	d := 200
	d <<= 2
	fmt.Printf("第1个d= %d\n", d)
	d >>= 2
	fmt.Printf("第2个d= %d\n", d)
	d &= 2
	fmt.Printf("第3个d= %d\n", d)
	d |= 2
	fmt.Printf("第4个d= %d\n", d)
	d ^= 2
	fmt.Printf("第5个d= %d\n", d)
}

//指针运算


```
[返回上一级](./golang-basic-knowledge.md)

[Next](golang-controller.md)