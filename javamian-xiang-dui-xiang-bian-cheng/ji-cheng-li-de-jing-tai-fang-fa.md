# 继承里的静态方法

```java
package supermarket;

public class StaticMethodDose {
    public static void main(String[] args) {
        LittleSuperMarket superMarket = new LittleSuperMarket("大卖场",
                "世纪大道1号", 500, 600, 100);

        System.out.println("-----1------");
        
        // >> TODO 静态方法可以被继承
        MerchandiseV2.staticMethod();
        Phone.staticMethod();
        ShellColorChangePhone.staticMethod();

        System.out.println("-----2------");

        MerchandiseV2 m = superMarket.getMerchandiseOf(100);

        // >> TODO 用引用调用静态方法没有覆盖
        m.staticMethod();
        ((Phone) m).staticMethod();
        ((ShellColorChangePhone) m).staticMethod();

        System.out.println("-----3------");

        ((MerchandiseV2) null).staticMethod();
        ((Phone) null).staticMethod();
        ((ShellColorChangePhone) null).staticMethod();
    }
}

```



