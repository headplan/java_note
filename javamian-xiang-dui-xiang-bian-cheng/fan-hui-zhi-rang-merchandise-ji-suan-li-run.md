# 返回值 : 让Merchandise计算利润

#### 让商品自己计算利润的方法

```java
package com.supermarket.market;

public class MerchandiseV2 {
    public String name;
    public String id;
    public int count;
    public double soldPrice;
    public double purchasePrice;
    public String madein;

    // >> TODO 访问修饰符
    // >> TODO 返回值类型:无需返回值则用void表示,void是Java中的关键字
    // >> TODO 方法名:任意合法的标识符都可以
    // >> TODO 参数列表
    // >> TODO 方法体:方法的代码
    // >> TODO 方法体内部定义的变量叫局部变量
    public void describe() {
        double netIncome = soldPrice - purchasePrice;
        System.out.println(
                "商品名字叫做" + name + "." +
                        "id是" + id + "." +
                        "商品售价是" + soldPrice + "." +
                        "商品进价是" + purchasePrice + "." +
                        "销售一个的毛利润是" + netIncome + '.' +
                        "产地" + madein
        );
    }

    // >> TODO 在方法定义中指定方法的返回值类型
    // >> TODO Java中一个方法只能有一种返回值,如果不需要返回值则用void表示
    // >> TODO 如果定义了返回值,则必须使用return语句返回方法的返回值,return是Java的关键字
    // >> TODO 可以认为,返回值必须要能够用来给返回值类型的变量赋值
    public double calculateProfit() {
        double profit = soldPrice - purchasePrice;
        // >> TODO 这个return是代码块里的return,是return所在代码块的最后一个语句
        if (profit <= 0) {
            return 0;
        }
        // >> return 语句必须是所在代码块的最后一个语句,否则就是语法错误
        return profit;
        // >> TODO 一个方法可以有多个返回语句
    }

    // >> TODO 返回值如果是基本类型,则要类型完全相同,或者符合类型自动转换规则
    public double getCurrentCount() {
        return count;
    }

    // >> TODO 如果不符合规则,可以使用强制类型转换
    public int getIntSoldPrice() {
        return (int) soldPrice;
    }
}
```

```java
package com.supermarket.market;

public class LittleSuperMarket {
    public String superMarketName;
    public String address;
    public int parkingCount;
    public double incomingSum;
    public MerchandiseV2[] merchandises;
    public int[] merchandiseSold;

    // >> 返回值类型可以是类名,这时候实际返回的值就是这个类的引用
    public MerchandiseV2 getBiggestProfitMerchandise() {
        MerchandiseV2 curr = null;
        for (int i = 0; i < merchandises.length; i++) {
            MerchandiseV2 m = merchandises[i];
            if (curr == null) {
                curr = m;
            } else {
                if (curr.calculateProfit() < m.calculateProfit()) {
                    curr = m;
                }
            }
        }
        return curr;
    }
}
```



