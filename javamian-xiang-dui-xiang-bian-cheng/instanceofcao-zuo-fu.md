# instanceof操作符

```java
package supermarket;

public class InstanceOfTestAppMain {
    public static void main(String[] args) {
        int merchandiseCount = 600;
        LittleSuperMarket superMarket = new LittleSuperMarket("大卖场", "回龙观", 500, merchandiseCount, 100);
        // TODO:instanceof操作符可以判断一个引用指向的对象是否是某一个类型或者其子类
        //      是则返回true,否则返回false.
        for (int i = 0; i < merchandiseCount; i++) {
//            MerchandiseV2 m = null;
            MerchandiseV2 m = superMarket.getMerchandiseOf(i);
            if (m instanceof Phone) {
                // TODO:通常会先判断,再强制类型转换,比较安全
                MerchandiseV2 ph = (MerchandiseV2) m;
                System.out.println(ph.getName());
            } else {
                System.out.println("not an instance");
            }
        }

        // TODO:如果引用是null,则肯定返回false
    }
}
```



