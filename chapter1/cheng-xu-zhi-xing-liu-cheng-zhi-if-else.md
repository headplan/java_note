# 程序执行流程之if-else

#### 顺序执行

* 代码块的执行是顺序执行
* 只要程序运行过程中不出错 , 就会一行行的向下顺序执行

#### 怎么能多买几个热包子 ? 用if-else

**买包子问题**

买3个肉包子

如果是刚出笼的热肉包子 , 就多买两个呢 ?

**if-else语法**

```java
if (boolean) {
    if 语句块
} else {
    else 语句块
}
```

* if-else语法 , 只有一个语句块被执行
* if和else都是Java中的关键字
* if语句
* 把if-else看做一个表达式 , 程序整体还是顺序执行的
* 使用if-else来多买两个包子

#### 增强寻找可以被整除的程序

**增强点**

* 只输出可以整除的数
* 输出商

#### if-else的嵌套

**求最大的数**

* if-else就是一个语句 , 可以是另一个语句的一部分 , 也可以是if-else的一部分 , 即嵌套 . 
* 求a , b和c三个数的最大数 . 

```java
package Procedure;

public class IfElseNestSimple {
    public static void main(String[] args) {
        int a = 10;
        int b = 999;
        int c = 999;

        System.out.println("a=" + a + ". b=" + b + ". c=" + c);
        if (a == b && b == c) {
            System.out.println("a,b和c相等.");
        } else if (a > b && a > c) {
            System.out.println("a的值最大.");
        } else if (b > a && b > c) {
            System.out.println("b的值最大.");
        } else if (c > a && c > b) {
            System.out.println("c的值最大.");
        } else if (a == b && b > c) {
            System.out.println("a和b相等且最大.");
        } else if (b == c && b > a) {
            System.out.println("b和c相等且最大.");
        } else if (a == c && a > b) {
            System.out.println("a和c相等且最大");
        }
    }
}
```

#### if-else的简化

**if-else省略大括号**

* 如果if或者else的语句块只有一个语句 , 可以省略大括号
* 简化求最大数的程序

```java
if (boolean)
    if 语句块
else
    else 语句块

if (boolean) {
    if 语句块
} else if () {
    if 语句块
} else {
    else 语句块
}
```



