# 目录

1. ### Go语言流程控制概述

2. ### [if 条件判断语句](./golangController/golang-controller-if.md)

3. ### [switch分之语句](./golangController/golang-controller-switch.md)

4. ### [for循环语句](./golangController/golang-controller-for.md)

## 一  Go语言流程控制

### （一）概述

1. 流程控制是每种编程语言逻辑走向和执行次序的重要不服，流程控制是一门语言的经脉；

2. 流程控制有条件判断语句、条件分支语句及循环语句；

3. Go语言的基本流程口至语句包括：

    * if条件判断语句

    * switch分支语句

    * for循环语句

    * goto跳转语句

    * break和continue循环控制语句

### （二）Go语言提供以下几种条件判断分支语句

| 语句 | 描述 |
| :---| :---|
| if | if语句 有一个布尔表达式后紧跟一个或多个语句组成 |
| if...else | if语句后可以使用可选的else语句，else语句中的表达式在布尔表达式为fales时执行 |
| if嵌套语句 | 可以再if或else if |
| switch语句 | switch语句基于不同条件执行不同动作 |
| select | select语句类似switch语句，但是select会随机执行一个可运行的case。如果没有case可运行，它将阻塞，直到youcase可运行 |
|

### （三）Go语言提供一下几种循环语句

| 循环语句 | 描述 |
| :---| :---|
| for循环 | 重复执行的语句块 |
| 循环嵌套 | 在for循环中嵌套一个或多个for循环 |
|

### （四）Go语言支持以下几种循环控制语句

| 控制语句 | 描述 |
|:---| :---|
| break语句 | 经常用于中断当前for循环或跳出switch语句 |
| continue语句 | 跳过当前的循环的剩余语句，然后继续进行下一轮循环 |
| goto语句 | 将控制转移到被标记的语句 |
|



[返回上一级](./golang-basic-knowledge.md)          [Next](./golangController/golang-controller-if.md)