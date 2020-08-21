# Java接口和抽象类

#### 接口

接口相当于就是对外的一种约定和标准 , 这里拿操作系统举例子 , 为什么会有操作系统 ? 就会为了屏蔽软件的复杂性和硬件的简单性之间的差异 , 为软件提供统一的标准 .

在Java语言中 , 接口是由`interface`关键字来表示的 , 比如我们可以向下面这样定义一个接口

```java
public interface HeadplanGoodJob {}
```

比如定义了一个 HeadplanGoodJob 的接口 , 然后就可以在其内部定义做哪些事情 : 

```java
public interface HeadplanGoodJob {
    void fuck();
}
```



