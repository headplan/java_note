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


