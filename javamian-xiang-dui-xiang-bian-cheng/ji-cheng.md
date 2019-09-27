# 继承

#### 继承的语法和作用

* 子类继承了父类的方法和属性
* 使用子类的引用可以调用父类的公有方法
* 使用子类的引用可以访问父类的公有属性
* 就好像子类的引用可以一物二用 , 即可以当做父类的引用使用 , 又可以当做子类的引用使用

```java
package Extends.supermarket;

// >> TODO 继承的语法就是在类名后面使用extends加要继承的类名
// >> TODO 被继承的类叫做父类(Parent Class),比如本例中的MerchandiseV2
// >> TODO 继承者叫做子类(Sub Class),比如本例中的PhoneExtendsMerchandise
// >> TODO Java中只允许一个类又一个直接的父类(Parent Class),即所谓的单继承
// >> TODO 别的类也可以继承子类,比如有一个HuaweiPhone继承PhoneExtendsMerchandise
//    TODO 那么HuaweiPhone类就是PhoneExtendsMerchandise的子类
// >> TODO 子类继承了父类的所有属性和方法
// >> TODO 但是子类并不能访问父类的private成员
public class PhoneExtendsMerchandise extends MerchandiseV2 {
    // 给Phone增加新的属性和方法
    // 给Phone增加新的属性和方法
    private double screenSize;
    private double cpuHZ;
    private int memoryG;
    private int storageG;
    private String brand;
    private String os;

    public PhoneExtendsMerchandise(
            String name, String id, int count, double soldPrice, double purchasePrice,
            double screenSize, double cpuHZ, int memoryG, int storageG, String brand, String os
    ) {

        this.screenSize = screenSize;
        this.cpuHZ = cpuHZ;
        this.memoryG = memoryG;
        this.storageG = storageG;
        this.brand = brand;
        this.os = os;

        this.setName(name);
        this.setId(id);
        this.setCount(count);
        this.setSoldPrice(soldPrice);
        this.setPurchasePrice(purchasePrice);
    }
}

```



