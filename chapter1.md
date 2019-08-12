# Java编程基础

#### 安装Java

下载安装JDK : [https://www.oracle.com/technetwork/java/javase/downloads/index.html](https://www.oracle.com/technetwork/java/javase/downloads/index.html)

检测JDK安装是否成功

```
java -version
javac -version
```

编写运行Hello World

```java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello World!");
    }
}
```

#### HelloWorld代码解析

```java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello World!");
    }
}
```

**类\(class\)语法元素**

* public class - 告诉Java类名要与代码文件名一致
* HelloWorld - 类名
* 大括号内是类的内容 , 就是class body . 

**main方法\(main method\)语法元素**

* public static void main\(String\[\] args\) - main方法的定义 . 告诉Java这是程序入口 , 也就是程序开始执行的地方 . 
* public static void 是方法修饰符
* 小括号内是方法的参数 \(parameter\)
* String\[\] args 是方法参数
* 大括号内是方法的内容 , 又称方法体 , 就是method body . 
* main方法最为特殊的一点是 , 它是Java程序的入口 . 

**System.out.println**

* System.out.println是Java提供的内置功能 , 可以将内容输出 . 
* 小括号里的内容是参数\(parameter\)
* 没有参数的情况下 , System.out.println\(\)会输出一行空行

#### 从加减乘除到变量

**计算加减乘除**

```java
public class MathCalc {
    public static void main(String[] args) {
        System.out.println(5 + 6);
        System.out.println(5 - 6);
        System.out.println(5 * 6);
        System.out.println(5 / 6.0);

        System.out.println((1 + 2 + 3) * 4 / 5.0);
        System.out.println(2 * 5 + 2 * 5 * 5 + 2 * 5 * 5 * 5);
    }
}
```

* 字面值\(literal value\)
* 加减乘除运算符

**基本数据类型\(int\)**

Java中所有的数据都有类型 , 类型决定了存储的形式和占用的存储空间 . 

int用来表示一个整数 , 取值范围在 -2^31 ~ 2^31-1 . 计算出来是-2147483648 ~ 2147483647 . 

```java
public class Int {
    public static void main(String[] args) {
        System.out.println(2147483647);
        System.out.println(2147483647 + 1);
    }
}
```

**关键字\(key word\)和标示符\(Identifier\)**

**用变量解决问题**



