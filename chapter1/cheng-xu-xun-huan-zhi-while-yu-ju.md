# 程序循环之while语句

#### 用while语句增强找整除数的程序

**增强点 : 找出n个可以被整除的数**

**while语句的语法**

* 条件表达式的结果是一个boolean值 , 如果是true , 则执行循环体 , 如果是false , 则循环结束 . 
* while循环体是一个代码块 . 所以while循环也是可以嵌套别的语句的 , 包括while语句 , for语句 , if-else语句等 . 

```java
while (条件表达式) {
    while循环体
}
```

```java
package Procedure;

public class FindNDiv {
    public static void main(String[] args) {
        int n = 10;

        int dividend = 100;
        int divisor = 89;

        int found = 0;
        while (found < n) {
            if (dividend % divisor == 0) {
                System.out.println(dividend + "可以整除" + divisor + ".商是" + dividend);
                found++;
            }
            dividend++;
        }
    }
}
```

#### do-while语句 - 至少执行一次

* do-while语句语法
* do-while语句的循环体至少执行一次

```java
do {
    while循环体
} while (条件表达式)
```

```java
package Procedure;

public class DoWhileExample {
    public static void main(String[] args) {
        do {
            System.out.println("会执行一次");
        } while (false);
    }
}
```

#### 死循环 \(endless loop\)

* 死循环 : 无法结束的循环\(endless loop / infinite loop\)
* 一个死循环的例子
* 死循环是因为没有设置好结束条件 , 循环的结束条件很重要 , 要充分考虑各种边界情况 . 

#### 一个看似死循环却不是死循环的例子

* 用while找出5个能被2000000000整除的数
* 程序最终还是结束了 , 但是结果并不是我们想要的

```java
package Procedure;

public class FindNDivNotEndless {
    public static void main(String[] args) {
        int n = 5;
        int dividend = 100;
        int divisor = 2000000000;
        int found = 0;

        while (found < n) {
            if (dividend % divisor == 0) {
                System.out.println(dividend + "可以整除" + divisor + ".商是" + dividend);
                found++;
            }
            dividend++;
        }
    }
}
```

#### 使用break语句结束循环

* break语句可以结束任何循环
* 不考虑负数的情况 , 使用break改善程序
* 理解String start的内容 , 为什么不是从-2147483648开始递增



