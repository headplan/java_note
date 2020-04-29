# Java编程基础

#### 安装Java

下载安装JDK : [https://www.oracle.com/technetwork/java/javase/downloads/index.html](https://www.oracle.com/technetwork/java/javase/downloads/index.html)

镜像资源 : [https://mirrors.tuna.tsinghua.edu.cn/](https://mirrors.tuna.tsinghua.edu.cn/) 社区版的JDK

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
public class IntType {
    public static void main(String[] args) {
        System.out.println(2147483647);
        System.out.println(2147483647 + 1);
    }
}
```

**关键字\(key word\)和标示符\(Identifier\)**

标示符 :

* 由大小写英文字符 , 数字和下划线\(\_\)组成的 , 区分大小写的 , 不以数字开头的文字 . 
* 可以用作Java中的各种东西的名字 , 比如类名 , 方法名等 . 
* 标示符是区分大小写的 . 

关键字是 Java 语法的保留字 , 不能用来做名字 .

前面提到的 : public class static void int 等 .

**用变量解决问题**

```java
public class Variable {
    public static void main(String[] args) {
        int a = 3;
        int b = 5;
        int c = 7;

        int x = 9;

        int y = a * x + b * x * x + c * x * x * x;

        System.out.println(y);
    }
}
```

#### 从加减乘除到代码块

```java
public class Variable {
    public static void main(String[] args) {

        int variable;

        variable = 999;

        int a = 3;
        int b = 5;
        int c = 7;

        int x = 9;

        int y = a * x + b * x * x + c * x * x * x;

        System.out.println(y);
    }
}
```

**Java代码三级跳 - 表达式 , 语句和代码块**

* **表达式\(expression\)** : Java中最基本的一个运算 . 比如一个加法运算表达式 . 1 + 2是一个表达式 , a + b也是 . 
* **语句\(statement\)** : 类似于平时说话时的一句话 , 由表达式组成 , 以;结束 . 1 + 2; 1 + 2 + 3; a + b;都是语句 . 
* **代码块** : 一个大括号括起来的就是一个代码块 . 

**Java是区分大小写的**

* 关键字和标识符都是区分大小写的
* 类名必须与文件名一致 , 包括大小写要求
* 使用变量时 , 名字必须和声明变量时的标识符大小写一致
* 方法名也区分大小写 . main和Main是两个名字
* 类型也区分大学写 . int是数据类型 , Int则不是
* System.out.println可以被Java认识 , SYSTEM.Out.Println就不可以

**字面值不简单**

* 整数的字面值类型默认是int
* 十六进制字面值和八进制的字面值
* 超过int的范围会怎么样 ? 需要使用取值范围更大的类型

**int x = 5; int y = x + 1; 包含多少语法点 ? **

**int x = 5;**

* 关键字
* 标识符
* 运算符
* 字面值
* 数据类型 , Java中的数据都有类型 , 数据类型有其取值范围
* 变量的创建和赋值

**int y = x + 1;**

* 变量的使用 , 标识符区分大小写
* 加法运算符
* 表达式 , 语句和代码块



