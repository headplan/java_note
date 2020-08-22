# Java异常

异常是程序经常会出现的 , 发现错误的最佳时机是在编译阶段 , 也就是你试图在运行程序之前 . 但是 , 在编译期间并不能找到所有的错误 , 有一些 `NullPointerException`和`ClassNotFoundException`异常在编译期找不到 , 这些异常是 RuntimeException 运行时异常 , 这些异常往往在运行时才能被发现 . 

写 Java 程序经常会出现两种问题 , 一种是 java.lang.Exception , 一种是 java.lang.Error , 都用来表示出现了异常情况 . 

#### 认识Exception

Exception位于java.lang包下 , 它是一种顶级接口 , 继承于Throwable类 , Exception类及其子类都是Throwable的组成条件 , 是程序出现的合理情况 . 

在认识 Exception 之前 , 有必要先了解一下什么是`Throwable`.

#### 什么是Throwable

Throwable类是Java语言中所有错误\(errors\)和异常\(exceptions\)的父类 . 只有继承于Throwable的类或者其子类才能够被抛出 , 还有一种方式是带有Java中的@throw注解的类也可以抛出 . 

在[Java规范](https://docs.oracle.com/javase/specs/jls/se9/html/jls-11.html#jls-11.1.1)中 , 对非受查异常和受查异常的定义是这样的 : 

> The _unchecked exception classes _are the run-time exception classes and the error classes.



