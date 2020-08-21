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

```java
public interface Dog {
    void FurColor();
}

abstract class WhiteDog implements Dog {
    public void FurColor() {
        System.out.println("Fur is white");
    }
    
    abstract void SmallBody();
}
```

在抽象类中 , 具有如下特征 : 

* 如果一个类中有抽象方法 , 那么这个类一定是抽象类 , 也就是说 , 使用关键字abstract修饰的方法一定是抽象方法 , 具有抽象方法的类一定是抽象类 . 实现类方法中只有方法具体的实现 . 
* 抽象类中不一定只有抽象方法 , 抽象类中也可以有具体的方法 , 可以自己去选择是否实现这些方法 . 
* 抽象类中的约束不像接口那么严格 , 可以在抽象类中定义构造方法 , 抽象方法 , 普通属性 , 普通方法 , 静态属性和静态方法 . 
* 抽象类和接口一样不能被实例化 , 实例化只能实例化具体类 . 



