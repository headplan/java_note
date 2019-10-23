# super : 调用父类的构造方法

使用super调用父类的构造方法 , 必须是子类构造方法的第一个语句 . 

可以使用表达式 , 但是super调用构造方法 , 不可以使用super访问父类的属性和方法 , 不可以使用子类成员变量和方法 . 可以使用静态变量和方法 . 

```java
public Phone(
        String name, String id, int count, double soldPrice, double purchasePrice,
        double screenSize, double cpuHZ, int memoryG, int storageG, String brand, String os
) {
    super(name, id, count, soldPrice * 1.2, purchasePrice);
}
```

都是&lt;init&gt;方法，我们来看一下

