# 方法的签名和重载

已经封装了不不同的方法去购买商品 , 例如 , 只买一个 , 买几个 , VIP会员购买95折 . 这些方法都不同 , 但又有重复 . 功能很相似 , 但又不完全一样 .

#### 方法重载\(overload\)

* 方法签名 : 方法名 + 依次参数类型 . 注意 , 返回值不属于方法签名 . 方法签名是一个方法在一个类中的唯一标识
* 同一个类中方法可以重名 , 但是签名不可以重复 . 一个类中如果定义了名字相同 , 签名不同的方法 , 就叫做方法的重载

```java
// >> TODO 重载的方法可以调用别的重载方法,当然也可以调用别的不重载的方法.
// >> TODO 实际上,像这种补充一些缺省的参数值,然后调用重载的方法,是重载的一个重要的使用场景.
// >> TODO 在这里举的例子就是这样的,但是并不是语法要求一定要这样.重载的方法的方法体内代码可以随便写,
//    TODO 可以不调用别的重载方法
public double buy() {
    return buy(1);
}

public double buy(int count) { return buy(count, false); }

// TODO 最后都补充好参数，调用参数最全的一个方法
public double buy(int count, boolean isVIP) {
    if (this.count < count) {
        return -1;
    }
    this.count -= count;
    double totalCost = count * soldPrice;
    if (isVIP) {
        return totalCost * 0.95;
    } else {
        return totalCost;
    }
}
```

#### 重载的参数匹配规则

```java
// >> TODO 方法调用的时候，参数就不必完全类型一样，实参数可以自动类型转换成形参类型即可
public double buyDouble(double count){
    System.out.println("buyDouble(double)被调用了");
    if (this.count < count) {
        return -1;
    }
    this.count -= count;
    double totalCost = count * soldPrice;
    return totalCost;
}
```



