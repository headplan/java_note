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

**类\(class\)语法元素**

```java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello World!");
    }
}
```

* HelloWorld - 类名
* public class - 告诉Java类名要与代码文件名一致
* 大括号内是类的内容 , 就是class body . 

**main方法\(main method\)语法元素**

* public static void main\(String\[\] args\) - main方法的定义 . 告诉Java这是程序入口 , 也就是程序开始执行的地方 . 
* 大括号内是方法的内容 , 又称方法体 , 就是method body . 
* main方法最为特殊的一点是 , 它是Java程序的入口 . 

**System.out.println**

* System.out.println是Java提供的内置功能 , 可以将内容输出 . 
* 小括号里的内容是参数\(parameter\)
* 没有参数的情况下 , System.out.println\(\)会输出一行空行



