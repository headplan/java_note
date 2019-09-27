# 子类对象里藏着一个父类对象

#### 使用组合解决问题

```java
package Extends.supermarket;

public class PhoneHasAMerchandise {
    // 给Phone增加新的属性和方法
    private double screenSize;
    private double cpuHZ;
    private int memoryG;
    private int storageG;
    private String brand;
    private String os;

    // >> TODO 除了继承,也可以优化上面使用的拷贝所有代码的方法,在Phone中添加一个商品的引用
    //    TODO 可以实现类似的功能
    // >> TODO 这种在自己的类里,使用别的类的两类之间关系叫做"has-a",也称为组合
    //    TODO 具体到我们这个例子.在我们用类构造的世界中,"Phone中有一个商品,但是Phone本身不是商品"
    private MerchandiseV2 merchandise;

    public PhoneHasAMerchandise(double screenSize, double cpuHZ, int memoryG, int storageG,
                                String brand, String os, MerchandiseV2 merchandise) {

        this.screenSize = screenSize;
        this.cpuHZ = cpuHZ;
        this.memoryG = memoryG;
        this.storageG = storageG;
        this.brand = brand;
        this.os = os;
        this.merchandise = merchandise;
    }
}
```



