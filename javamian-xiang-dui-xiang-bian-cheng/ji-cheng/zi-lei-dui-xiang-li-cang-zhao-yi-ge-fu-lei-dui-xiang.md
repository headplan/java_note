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

#### 继承和组合的区别

继承其实表达的是一种**"is-a"**的关系 , 也就是说 , 在用类构造的世界中 , "子类是父类的一种特殊类别"

组合和继承是拿到一个问题 , 设计相应的Java类的时候不得不面对的来自灵魂的拷问 ? "XX到底是YY的一种 , 还是只是组合了YY ? " , "手机到底是手电筒的一种 , 还是组合了一个可以当手电的闪光灯 ? "

在组合的情况下 , 怎么限制一次只能买五个手机呢 ? 

* 首先不能修改MerchandiseV2这个类 , 否则会限制所有商品一次购买的数量
* 其次在现实情况下 , 这个类可能根本不受你控制 , 你无权修改其代码
* 在每次调用buy方法的地方做限制是不行的
  * 你无法控制别人怎么用你的类
  * 而且会面临到处复制代码的糟糕情况
  * 如果说限制改成10个 , 所有复制的代码都要改
* 在只能修改手机类的情况下 , 可以提供一个buyPhone的方法 , 实现限制购买数量的逻辑 . 但是这样并不能阻止别人像下面这样调用merchandise的buy方法 , 这个方法是会修改库存的 , 所以还是无法硬性的限制一次性购买手机的数量

所以 , 针对手机限制一次性购买的数量 . 必须限制死 , 必须不影响别的商品 , 必须只能改手机类的代码 . 这时候 , 组合就无能为力了 , 继承可以发挥其应有的作用 . 

**继承不是组合 , 继承也不只是为了能简单的拿来父类的属性和方法 . 如果仅仅如此 , 原封不动的拿来主义 , 组合也能做到 . **

**继承也不是通过组合的方式来实现的 . 和组合相比 , 继承更像是"融合"**

**所谓融合即合二为一 , 可以互相影响 . 父类影响子类没问题 , 子类怎么影响父类呢 ? 如何限制手机一次只能最多买五个 ? 即 , 覆盖 . **



