# Java概述

#### 什么是Java ?

Java 是 Sun Microsystems 于1995 年首次发布的一种`编程语言`和计算平台 . 编程语言还比较好理解 , 那么什么是`计算平台`呢 ?

> 计算平台是在电脑中运行应用程序（软件）的环境 , 包括`硬件环境`和`软件环境` . 一般系统平台包括一台电脑的硬件体系结构、操作系统、运行时库 .

Java 是快速 , 安全和可靠的 . 从笔记本电脑到数据中心 , 从游戏机到科学超级计算机 , 从手机到互联网 , Java 无处不在 . Java 主要分为三个版本 :

* JavaSE\(J2SE\)\(Java2 Platform Standard Edition , java平台标准版）
* JavaEE\(J2EE\)\(Java 2 Platform,Enterprise Edition , java平台企业版\)
* JavaME\(J2ME\)\(Java 2 Platform Micro Edition , java平台微型版\)

#### Java的特点

* Java 是一门`面向对象`的编程语言 . 

什么是面向对象 ? `面向对象(Object Oriented)`是一种软件开发思想 . 它是对现实世界的一种抽象 , 面向对象会把相关的数据和方法组织为一个整体来看待 .

相对的另外一种开发思想就是面向过程的开发思想 , 什么面向过程 ? `面向过程(Procedure Oriented)`是一种以过程为中心的编程思想。举个例子 : 比如你是个学生 , 你每天去上学需要做几件事情 ?

```java
class student {
    void student_wakeUp(){...}
    void student_cloth(){...}
    void student_wash(){...}
    void student_eating(){...}
    void student_gotoSchool(){...}
}
```

可以不用严格按照顺序来执行每个动作 , 这是特点一 .

Java 摒弃了 C++ 中难以理解的多继承、指针、内存管理等概念 . 不用手动管理对象的生命周期 , 这是特征二 .

Java 语言具有功能强大和简单易用两个特征 , 现在企业级开发 , 快速敏捷开发 , 尤其是各种框架的出现 , 使Java成为越来越火的一门语言 . 这是特点三 .

Java 是一门静态语言 , 静态语言指的就是在编译期间就能够知道数据类型的语言 , 在运行前就能够检查类型的正确性 , 一旦类型确定后就不能再更改 , 比如下面这个例子 :

```java
public void foo() {
    int x = 5;
    boolean b = x;
}
```

静态语言主要有**Pascal, Perl, C/C++, JAVA, C\#, Scala**等 . 

