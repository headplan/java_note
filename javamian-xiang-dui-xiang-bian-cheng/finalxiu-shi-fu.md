# final修饰符

* final修饰类 : 不可被继承 .
* final修饰方法 : 不可被子类覆盖 .
* final修饰变量 : 不可被赋值 . 赋值只能在成员变量上 , 要么在构造方法 . 不赋值会报错 .  
* final修饰静态变量 : 和上面一样 , 也是不可在其他地方赋值 , 只能在静态变量上 , 或static块里赋值 . 
* final不能修饰构造方法 . 
* 用final修饰方法,方法不可被覆盖
* 用final修饰形参,形参不能被赋值
* 用final修饰局部变量,局部变量不能被赋值

```java
package supermarket;

// TODO:用final修饰类,则该类不能被继承.
public final class Phone extends MerchandiseV2 {
    // TODO:用final修饰成员变量
    private final double screenSize; // 屏幕大小
    private double cpuHZ;      // cup速度
    private int memoryG;       // 内存大小
    private int storageG;      // 硬盘大小
    private String brand;      // 品牌
    private String os;         // 系统
    // TODO:用final修饰引用
    private final MerchandiseV2 gift;
    // TODO:用final修饰静态变量
    private final static int MAX_BUY_ONE_ORDER; // 最大购买数量
    static {
        MAX_BUY_ONE_ORDER = 5;
    }
    // TODO:构造方法不能用final修饰
    public Phone(String name, String id, int count, double soldPrice, double purchasePrice, double screenSize, double cpuHZ, int memoryG, int storageG, String brand, String os, MerchandiseV2 gift) {
        super(name, id, count, soldPrice * 1.2, purchasePrice);
        this.screenSize = screenSize;
        this.cpuHZ = cpuHZ;
        this.memoryG = memoryG;
        this.storageG = storageG;
        this.brand = brand;
        this.os = os;
        this.gift = gift;
    }

    // TODO:用final修饰方法,方法不可被覆盖
    // TODO:用final修饰形参,形参不能被赋值
    // TODO:用final修饰局部变量,局部变量不能被赋值
    public double buy(int count) {
        System.out.println("Phone里的buy(int count)");
        if (count > MAX_BUY_ONE_ORDER) {
            System.out.println("购买失败，手机一次最多只能买" + MAX_BUY_ONE_ORDER + "个");
            return -2;
        }
        return super.buy(count);
    }
```

 

