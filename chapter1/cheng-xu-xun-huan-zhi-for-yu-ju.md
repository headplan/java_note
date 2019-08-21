# 程序循环之for语句

#### 简化输出连续26个字符的程序

**for 语句**

* 让程序在满足某条件时 , 重复还行某个代码块 . for是java中的关键字
* for语句语法和简单的示例程序
* 初始语句在for循环开始前执行一次 , 以后不再执行 ; 
  * 循环体条件表达式在每次循环体执行前会执行 , 如果为true , 则执行循环体 , 否则循环结束 ; 
  * 循环体后语句会在每次循环执行后被执行;

```
for (初始语句;循环体条件表达式;循环体后语句) {
    for 循环体
}
```

```java
package Procedure;

public class SimpleFor {
    public static void main(String[] args) {
        for (int i = 0; i < 10; i++) {
            System.out.println("i的值是" + i);
        }
    }
}
```

```java
package Procedure;

public class PrintChars {
    public static void main(String[] args) {
        char ch = 'A';
        int startNum = ch;
        for (int i = 0; i < 26; i++) {
            int newNum = startNum + i;
            System.out.println(newNum + "\t" + ((char) newNum));
        }
    }
}
```

#### 简化并增强找整除数的程序

* 使用for语句让程序简洁
* 增强新功能 , 输出最多10个可以整除的数
* 条件布尔表达式可以用for语句外部的变量
* 循环体执行后的语句可以有多个表达式 , 用逗号分开

```java
package Procedure;

public class CalcDivForWithLimit {
    public static void main(String[] args) {
        int divided = 1;
        int divisor = 3;

        int found = 0;
        for (int i = 0; i < 100 && found < 10; i++) {
            if (divided % divisor == 0) {
                System.out.println(divided + "可以整除" + divisor + ", 商为" + divided);
                found++;
            }
            divided++;
        }
    }
}
```

#### break语句

**结束循环**

* break语句可以结束循环
* 在求整除程序中使用break提前结束循环

#### continue语句

**跳过不符合条件的循环**

* continue语句可以结束当次循环的执行 , 开始下一次循环体的执行



