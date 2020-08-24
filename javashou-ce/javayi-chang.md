# Java异常

异常是程序经常会出现的 , 发现错误的最佳时机是在编译阶段 , 也就是你试图在运行程序之前 . 但是 , 在编译期间并不能找到所有的错误 , 有一些 `NullPointerException`和`ClassNotFoundException`异常在编译期找不到 , 这些异常是 RuntimeException 运行时异常 , 这些异常往往在运行时才能被发现 .

写 Java 程序经常会出现两种问题 , 一种是 java.lang.Exception , 一种是 java.lang.Error , 都用来表示出现了异常情况 .

#### 认识Exception

Exception位于java.lang包下 , 它是一种顶级接口 , 继承于Throwable类 , Exception类及其子类都是Throwable的组成条件 , 是程序出现的合理情况 .

在认识 Exception 之前 , 有必要先了解一下什么是`Throwable`.

#### 什么是Throwable

Throwable类是Java语言中所有错误\(errors\)和异常\(exceptions\)的父类 . 只有继承于Throwable的类或者其子类才能够被抛出 , 还有一种方式是带有Java中的@throw注解的类也可以抛出 .

在[Java规范](https://docs.oracle.com/javase/specs/jls/se9/html/jls-11.html#jls-11.1.1)中 , 对非受查异常和受查异常的定义是这样的 :

> The \_unchecked exception classes \_are the run-time exception classes and the error classes.
>
> The _checked exception classes_ are all exception classes other than the unchecked exception classes. That is, the checked exception classes are `Throwable` and all its subclasses other than `RuntimeException` and its subclasses and `Error` and its subclasses.

也就是说 , 除了`RuntimeException`和其子类 , 以及`error`和其子类 , 其它的所有异常都是`checkException` .

那么 , 按照这种逻辑关系 , 可以对 Throwable 及其子类进行归类分析

![](/assets/throwableclass.png)这里 , Throwable位于异常和错误的最顶层 , 查看Throwable类中发现它的方法和属性有很多 , 这里讨论几个比较常用的 :

```java
// 返回抛出异常的详细信息
public string getMessage();
public string getLocalizedMessage();

// 返回异常发生时的简要描述
public String toString();

// 打印异常信息到标准输出流上
public void printStackTrace();
public void printStackTrace(PrintStream s);
public void printStackTrace(PrintWriter s);

// 记录栈帧的当前状态
public synchronized Throwable fillInStackTrace();
```

此外 , 因为Throwable的父类也是`Object` , 所以常用的方法还有继承其父类的`getClass()`和`getName()`方法 .

#### 常见的Exception

下面我们回到Exception的探讨上来 , 现在你知道了Exception的父类是Throwable , 并且Exception有两种异常 , 一种是`RuntimeException` ; 一种是`CheckedException` , 这两种异常都应该去`捕获` .

下面列出了一些 Java 中常见的异常及其分类 :

##### RuntimeException

| 异常名称 | 异常描述 |
| :--- | :--- |
| ArrayIndexOutOfBoundsException | 数组越界异常 |
| NullPointerException | 空指针异常 |
| IllegalArgumentException | 非法参数异常 |
| NegativeArraySizeException | 数组长度为负异常 |
| IllegalStateException | 非法状态异常 |
| ClassCastException | 类型转换异常 |

**UncheckedException**

| 异常名称 | 异常描述 |
| :--- | :--- |
| NoSuchFieldException | 表示该类没有指定名称抛出来的异常 |
| NoSuchMethodException | 表示该类没有指定方法抛出来的异常 |
| IllegalArgumentException | 不允许访问某个类的异常 |
| ClassNotFoundException | 类没有找到抛出异常 |

#### 与 Exception 有关的 Java 关键字

在 Java 中有这几个关键字**throws、throw、try、finally、catch . **

#### throws 和 throw

在 Java 中 , 异常也就是一个对象 , 它能够被程序员自定义抛出或者应用程序抛出 , 必须借助于`throws`和`throw`语句来定义抛出异常 .

throws 和 throw 通常是成对出现的 , 例如 :

```java
static void cacheException() throws Exception {
    throw new Exception();
}
```

throw 语句用在方法体内 , 表示抛出异常 , 由方法体内的语句处理 . throws 语句用在方法声明后面 , 表示再抛出异常 , 由该方法的调用者来处理 .

throws主要是声明这个方法会抛出这种类型的异常 , 使它的调用者知道要捕获这个异常 . throw 是具体向外抛异常的动作 , 所以它是抛出一个异常实例 .

#### try , finally , catch

这三个关键字主要有下面几种组合方式**try...catch 、try...finally、try...catch...finally . **

try...catch表示对某一段代码可能抛出异常进行的捕获 , 例如 :

```java
static void cacheException() throws Exception {
    try {
        System.out.println("1");
    } catch (Exception e) {
        e.printStackTrace();
    }
}
```

try...finally表示对一段代码不管执行情况如何 , 都会走finally中的代码 :

```java
static void cacheException() throws Exception {
    for (int i = 0; i < 5; i++) {
        System.out.println("enter: i=" + i);
        try {
            System.out.println("execute: i=" + i);
            coutinue;
        } finally {
            System.out.println("leave: i=" + i);
        }
    }
}
```

try...catch...finally也是一样的 , 表示对异常捕获后 , 再走finally中的代码逻辑 .

#### 什么是Error

Error是程序无法处理的错误 , 表示运行应用程序中较严重问题 . 大多数错误与代码编写者执行的操作无关 , 而表示代码运行时JVM\(Java虚拟机\)出现的问题 . 这些错误是不可检查的 , 因为它们在应用程序的控制和处理能力之外 , 而且绝大多数是程序运行时不允许出现的状况 , 比如`OutOfMemoryError` 和`StackOverflowError`异常的出现会有几种情况 .

先来看看JDK1.7的内存模型 :

![](/assets/neicunmoxing17.png)

其中包括两部分 , **由所有线程共享的数据区和线程隔离的数据区**组成 , 在上面的Java内存模型中 , **只有程序计数器**是不会发生 `OutOfMemoryError`情况的区域 , 程序计数器控制着计算机指令的分支、循环、跳转、异常处理和线程恢复 , 并且程序计数器是每个线程私有的 .

> 什么是线程私有的 : 表示的就是各条线程之间互不影响 , 独立存储的内存区域 .

如果应用程序执行的是 Java 方法 , 那么这个计数器记录的就是`虚拟机字节码`指令的地址 ; 如果正在执行的是`Native`方法\(原生方法\) , 这个计数器值则为`空(Undefined)` . 

除了程序计数器外 , 其他区域 : `方法区(Method Area)`、`虚拟机栈(VM Stack)`、`本地方法栈(Native Method Stack)`和`堆(Heap)`都是可能发生 OutOfMemoryError 的区域 . 

* 虚拟机栈 : 如果线程请求的栈深度大于虚拟机栈所允许的深度 , 将会出现`StackOverflowError`异常 ; 如果虚拟机动态扩展无法申请到足够的内存 , 将出现`OutOfMemoryError`. 
* 本地方法栈和虚拟机栈一样
* 堆 : Java堆可以处于物理上不连续 , 逻辑上连续 , 就像我们的磁盘空间一样 , 如果堆中没有内存完成实例分配 , 并且堆无法扩展时 , 将会抛出 OutOfMemoryError . 
* 方法区 : 方法区无法满足内存分配需求时 , 将抛出OutOfMemoryError异常 . 

在Java中 , 可以把异常理解为一种能够提高程序健壮性的机制 , 它能够让你在编写代码中注意这些问题 . 

