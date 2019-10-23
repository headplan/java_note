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

通过例程可以看出 , super\(\)为子类构造方法的第一个语句 . 前面还说过this\(\)重载构造函数的方法 , 同样要求在构造方法第一句 , 这里是冲突的 , 都写就会报错 , 可以使用一个自定义的方法 , 来解决冲突 . 

```java
public Phone(
        String name, String id, int count, double soldPrice, double purchasePrice,
        double screenSize, double cpuHZ, int memoryG, int storageG, String brand, String os
) {
    super(name, id, count, soldPrice * 1.2, purchasePrice);
    init(screenSize, cpuHZ, memoryG, storageG, brand, os);
}

public Phone() {
    super("无名", "000", 0, 1, 1.1);
    init(4.5, 4.6, 6, 128, "Uknown", "Uknown");
}

public void init(double screenSize, double cpuHZ, int memoryG, int storageG, String brand, String os) {
    this.screenSize = screenSize;
    this.cpuHZ = cpuHZ;
    this.memoryG = memoryG;
    this.storageG = storageG;
    this.brand = brand;
    this.os = os;
}
```

都是&lt;init&gt;方法，我们来看一下

