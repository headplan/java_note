# 方法 : 让Merchandise对象有行为

#### 方法\(Method\) - 让商品可以描述自己

方法英文名叫method , 又称作function .

```java
package com.supermarket.market;

public class MerchandiseV2 {
    public String name;
    public String id;
    public int count;
    public double soldPrice;
    public double purchasePrice;

    // >> TODO 访问修饰符
    // >> TODO 返回值类型:无需返回值则用void表示,void是Java中的关键字
    // >> TODO 方法名:任意合法的标识符都可以
    // >> TODO 参数列表
    // >> TODO 方法体:方法的代码
    public void describe() {
        double netIncome = soldPrice - purchasePrice;
        System.out.println(
                "商品名字叫做" + name + "." +
                "id是" + id + "." +
                "商品售价是" + soldPrice + "." +
                "商品进价是" + purchasePrice + "." +
                "销售一个的毛利润是" + netIncome
        );
    }
}
```

**方法的调用**

* 通过引用的点操作符 , 可以调用对象的方法 ; 
* 方法调用要用括号 , 即使没有参数 ; 
* 方法可以使用的数据 : 对象的成员变量\(member variable\) ; 



