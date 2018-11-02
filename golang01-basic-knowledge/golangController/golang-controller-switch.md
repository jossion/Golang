# switch分支语句

## （一）语法
    
Go语言中switch语句的语法如下：

```go
switch var1 {
    case val1:
    ...
    case val2:
    ...
    default:
    ...
}
```
 * switch语句由于基于不同条件执行不同动作，每一个case分支都是唯一的，从上至下逐一测试，直到找到匹配的条件，匹配条件后面不需要再加break语句。
 * 变量var1可以是任何类型，而val1和val2则可以是同类型的任意值。类型不被局限于常量或整数，但必须是相同类型；或者最终结果为相同类型的表达式
 * 可以**_同时测试多个符合条件的值_**，使用逗号分隔他们，例如：val1，，val2，val3。
 * Go语言中的**_switch后的表达式可以省略_**，那么默认值是true       


## 案例:


```go
package main

import "fmt"

func main() {
	//ScoreGrade()
	//Month()
}
//判断成绩
func ScoreGrade() {
	score := 90.5
	grade := ""
	switch {
	case score >= 90:
		grade = "A"
	case score >= 80:
		grade = "B"
	case score >= 70:
		grade = "C"
	case score >= 60:
		grade = "D"
	default:
		grade = "E"
	}
	fmt.Printf("你的等级是：%s \n", grade)
	fmt.Print("你的评价是：")
	switch grade {
	case "A":
		fmt.Println("优秀")
	case "":
		fmt.Println("良好")
	case "C":
		fmt.Println("中等")
	case "D":
		fmt.Println("及格")
	default:
		fmt.Println("不及格")
	}

}

```


```
输出结果：
你的等级是：A 
你的评价是：优秀
```
[返回目录](../golang-controller.md) [Next](golang-controller-for.md)

