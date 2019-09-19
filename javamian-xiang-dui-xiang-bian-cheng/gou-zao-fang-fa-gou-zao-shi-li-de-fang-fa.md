# 构造方法 : 构造实例的方法

```java
public class MerchandiseV2WithConstructor {

    public String name;
    public String id;
    public int count;
    public double soldPrice;
    public double purchasePrice;

    // >> TODO 构造方法(constructor)的方法名必须与类名一样,而且构造方法没有返回值.这样的方法才是构造方法.
    // >> TODO 构造方法可以有参数,规则和语法于普通方法一样.使用时,参数传递给new语句后类名的括号后面.
    // >> TODO 如果没有显示的添加一个构造方法,Java会给每个类都会默认自带一个无参数的构造方法.
    //    TODO 如果我们自己添加类构造方法,Java就不会再添加无参数的构造方法.而是调用自己定义的构造方法.
    // >> TODO 所以我们一直都在使用构造方法,这也是为什么创建对象的时候类名后面要有一个括号的原因.
    // >> TODO 构造方法无法被点操作符调用或者在普通方法里调用,只能通过new语句在创建对象的时候,间接调用.
    //    TODO 理解一下为什么构造方法不能有返回值,因为有返回值也没有意义,new语句永远返回的是创建出来的对象的引用
    public MerchandiseV2WithConstructor(String name, String id, int count,
                                        double soldPrice, double purchasePrice) {
        this.name = name;
        this.id = id;
        this.count = count;
        this.soldPrice = soldPrice;
        this.purchasePrice = purchasePrice;
    }
}
```

#### 构造方法的重载和互相调用

```java
public class MerchandiseV2 {

    public String name;
    public String id;
    // >> TODO 构造方法执行前,会执行给局部变量赋初始值的操作
    // >> TODO 所有的代码都必须在方法里,那么这种给成员变赋初始值的代码在哪个方法里呢?
    //    TODO 其实构造方法在内部变成了<init>方法.
    public int count = 999;// 999/0;
    public double soldPrice;
    public double purchasePrice;

    // >> TODO 构造方法(constructor)的重载和普通方法一样
    public MerchandiseV2(String name, String id, int count, double soldPrice, double purchasePrice) {
        this.name = name;
        this.id = id;
        this.count = count;
        this.soldPrice = soldPrice;
        this.purchasePrice = purchasePrice;
        // soldPrice = 9/0;
    }

    // >> TODO 在构造方法里才能调用重载的构造方法.语法为this(实参列表)
    // >> TODO 构造方法不能自己调用自己,这会是一个死循环
    // >> TODO 在调用重载的构造方法时,不可以使用成员变量.因为用语意上讲,这个对象还没有被初始化完成,处于中间状态.
    // >> TODO 在构造方法里才能调用重载的构造方法时,必须是方法的第一行.后面可以继续有代码
    public MerchandiseV2(String name, String id, int count, double soldPrice) {
        this(name, id, count, soldPrice, soldPrice * 0.8);
        // double purPrice = soldPrice * 0.8;
        // this(name, id, count, soldPrice, purchasePrice);
        // double purPrice = soldPrice * 0.8;
    }

    // >> TODO 因为我们添加了构造方法之后,Java就不会再添加无参数的构造方法.如果需要的话,可以自己添加这样的构造方法
    public MerchandiseV2() {
        this("无名", "000", 0, 1, 1.1);
    }

    public void describe() {
        System.out.println("商品名字叫做" + name + "，id是" + id + "。 商品售价是" + soldPrice
            + "。商品进价是" + purchasePrice + "。商品库存量是" + count +
            "。销售一个的毛利润是" + (soldPrice - purchasePrice));
    }

    public double calculateProfit() {
        double profit = soldPrice - purchasePrice;
//        if(profit <= 0){
//            return 0;
//        }
        return profit;
    }

    public double buy(int count) {
        if (this.count < count) {
            return -1;
        }
        return this.count -= count;
    }
}
```



