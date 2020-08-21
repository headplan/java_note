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

这里隐含了一些接口的特征 :

* `interface`接口是一个完全抽象的类 , 不会提供任何方法的实现 , 只是会进行方法的定义 . 
* 接口中只能使用两种访问修饰符 , 一种是`public` , 它对整个项目可见 ; 一种是default缺省值 , 它只具有包访问权限 . 
* 接口只提供方法的定义 , 接口没有实现 , 但是接口可以被其他类实现 . 也就是说 , 实现接口的类需要提供方法的实现 , 实现接口使用`implements`关键字来表示 , 一个接口可以有多个实现 . 

```java
class HeadplanWriteWell implements HeadplanGoodJob {
    @Override
    public void writeWell() {
        System.out.println("Headplan Team");
    }
}
```

* 接口不能被实例化 , 所以接口中不能有任何构造方法 , 定义构造方法编译会出错 . 
* 接口的实现必须实现接口的全部方法 , 否则必须定义为抽象类 . 

#### 抽象类

抽象类是一种抽象能力弱于接口的类 , 在Java中 , 抽象类使用`abstract`关键字来表示 . 

```

```



