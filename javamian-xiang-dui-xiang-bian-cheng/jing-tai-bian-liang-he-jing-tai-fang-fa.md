# 静态变量和静态方法

* 尽量不要使用Magic Number
* VIP的折扣作为一个成员变量 , 有些浪费 , 可以写成静态变量
* 静态变量也叫类变量

```java
// >> TODO 静态变量使用 static 修饰符
// >> TODO 静态变量如果不赋值,Java也会给它赋以其类型的初始值
// >> TODO 静态变量一般使用全大写字母加下划线分割.这是一个习惯用法
// >> TODO 所有的代码都可以使用静态变量,只要根据防范控制符的规范,这个静态变量对其可见即可
//    TODO 比如public的静态变量,所有的代码都可以使用它
public static double DISCOUNT_FOR_VIP = 0.95;

//    TODO 但是如果没有public修饰符，只能当前包的代码能使用它
static int STATIC_VARIABLE_CURR_PACKAGE_ONLY = 100;
```

```java
import com.geekbang.supermarket.MerchandiseV2WithStaticVariable;
import static com.geekbang.supermarket.MerchandiseV2WithStaticVariable.*;

public class MerchandiseV2DescAppMain {
    public static void main(String[] args) {
        MerchandiseV2WithStaticVariable merchandise = new MerchandiseV2WithStaticVariable("书桌", "DESK9527", 40, 999.9, 500);

        merchandise.describe();

        // >> TODO 使用import static来引入一个静态变量,就可以直接用静态变量名访问了(比较新的语法)
        //    TODO import static也可以使用通配符*来引入一个类里所有静态变量
        System.out.println(DISCOUNT_FOR_VIP);
        System.out.println(MerchandiseV2WithStaticVariable.DISCOUNT_FOR_VIP);
    }
}
```

```java
// >> TODO 使用别的类的静态变量的时候,需要使用完整形态:类名.静态变量名字
MerchandiseV2WithStaticVariable.DISCOUNT_FOR_VIP = 0.5;
bigProfit.describe();
double cost2 = bigProfit.buy(10, true);
System.out.println("VIP 购买10个" + bigProfit.getName() + "的花费为" + cost2);

// >> TODO 静态变量在整个Java程序中只有一个.对比实例变量,是每个实例有一份
//    TODO 所以静态变量一旦变化,所有使用这个静态变量的地方的值都会变
MerchandiseV2WithStaticVariable m0 = littleSuperMarket.getMerchandiseOf(0);
```

#### 静态方法

静态方法也叫类方法 . 只能使用参数和静态变量 . 换言之 , 就是没有this自引用的方法 .

```java
// >> TODO 静态变量使用 static 修饰符
public static double DISCOUNT_FOR_VIP = 0.95;

// >> TODO 静态方法使用static修饰符
// 静态方法的方法名没有约定俗称全大写
public static double getVIPDiscount() {
    // >> TODO 静态方法可以访问静态变量,包括自己类的静态变量和在访问控制符允许的别的类的静态变量
    return DISCOUNT_FOR_VIP;
}

// >> TODO 除了没有this,静态方法的定义和成员方法一样,也有方法名,返回值和参数
// >> TODO 静态方法没有this自引用,它不属于某个实例,调用的时候也无需引用,直接用类名调用,所以它也不能直接访问成员变量
// >> TODO 当然在静态方法里面,也可以自己创建对象,或者通过参数,获得对象的引用,进而调用方法和访问成员变量
// >> TODO 静态方法只是没有this自引用的方法而已.
public static double getDiscountOnDiscount(LittleSuperMarket littleSuperMarket) {
    double activityDiscount = littleSuperMarket.activityDiscount;
    return DISCOUNT_FOR_VIP * activityDiscount;
}

public double buy(int count, boolean isVIP) {
    if (this.count < count) {
        return -1;
    }
    this.count -= count;
    double totalCost = count * soldPrice;
    if (isVIP) {
        // >> TODO 静态方法的访问和静态变量一样,可以带上类名,当前类可以省略类名
        return totalCost * getVIPDiscount();
    } else {
        return totalCost;
    }
}
```

#### 静态方法的重载

静态方法的重载和成员方法\(实例方法\)一样 .

```java
public class DiscountMgr {

    public static double BASE_DISCOUNT = 0.99;

    public static double VIP_DISCOUNT = 0.85;

    public static double SVIP_DISCOUNT = 0.75;

    // >> TODO 静态方法的重载也是一样的,方法签名不同即可:方法名+参数类型
    // >> TODO 判断调用哪个方法,也是根据调用时参数匹配决定的.
    public static double getDiscount() {
        return BASE_DISCOUNT;
    }

    public static double getDiscount(boolean isVIP) {
        // TODO 三元操作符的返回类型就是冒号两边的类型,两边的类型要和等号左边的变量类型兼容
        // double abc = true ? "" : 0;

        double svipDiscount = (isVIP ? VIP_DISCOUNT : 1);
        return getDiscount() * svipDiscount;
    }

    public static double getDiscount(int svipLevel) {
        double ret = getDiscount() * VIP_DISCOUNT;
        for (int i = 0; i < svipLevel; i++) {
            ret *= SVIP_DISCOUNT;
        }
        return ret;
    }

    // >> TODO 返回值不算是方法签名,重载的方法可以有完全不同的返回值类型
    public static void getDiscount(String s) {
        System.out.println(s);
    }

    public static int getDiscount(int a, int b) {
        return a > b ? a : b;
    }

    public static boolean getDiscount(int a, int b, int c) {
        return a > b && b > c;
    }

    public static String getDiscount(long abc) {
        return "" + abc;
    }

    public static void main(String[] args) {
        getDiscount(1, 2);
    }
}
```



