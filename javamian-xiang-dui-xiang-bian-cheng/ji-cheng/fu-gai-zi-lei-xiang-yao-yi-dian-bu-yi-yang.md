# 覆盖 : 子类想要一点不一样

**覆盖才是继承的精髓和终极奥义 .**

通过使用和父类方法签名一样 , 而且返回值也必须一样的方法 , 可以让子类覆盖\(override\)掉父类的方法 . 也就是说 , 子类并不是只能把父类的方法拿过来 , 而且可以通过覆盖来替换其中不适合子类的方法 .

所以 , 使用方法读写属性 , 要优于直接访问属性 . 属性是联动的 , 可能是有特殊意义的 . 所以直接给属性赋值是危险的 , 因为没有办法检查新的值是否有意义 , 也没法对这个修改做联动的修改 .

覆盖可以覆盖掉父类的方法 . 同一个方法 , 不同的行为 . 这就是多态 ! 方法可以覆盖 , 属性访问不可以 , 所以这也是使用方法的一个原因 . 方法不止眼前的代码 , 还有子类和覆盖 . 用方法才能覆盖 , 才能多态 .

```java
public double buy(int count) {
    if (count > MAX_BUY_ONE_ORDER) {
        System.out.println("购买失败，手机一次最多只能买" + MAX_BUY_ONE_ORDER + "个");
        return -2;
    }
    if (this.count < count) {
        System.out.println("购买失败，库存不够");
        return -1;
    }
    this.count -= count;
    double cost = count * soldPrice;
    System.out.println("购买成功，花费为" + cost);
    return cost;
}
```

如何替换掉和父类重合度较高的代码 ? 

如何覆盖并调用父类的方法 ? 

