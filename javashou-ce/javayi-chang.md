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



