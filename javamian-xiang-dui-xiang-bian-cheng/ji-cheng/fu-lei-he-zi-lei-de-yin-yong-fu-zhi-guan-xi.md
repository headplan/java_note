# 父类和子类的引用赋值关系

* 父类引用可以指向子类对象 , 子类引用不可以指向父类的对象 . 
* 可以进行强制类型转换 , 如果类型不对 , 会出错 . 
* 可以调用的方法 , 是受引用类型决定的 . 

```java
import supermarket.MerchandiseV2;
import supermarket.Phone;

public class ReferenceAssign {
    public static void main(String[] args) {
        Phone ph = new Phone(
                "手机001", "Phone001", 100, 1999, 999,
                4.5, 3.5, 4, 128, "索尼", "安卓"
        );

        // >> TODO 可以用子类的引用给父类的引用赋值,也就是说,父类的引用可以指向子类的对象
        //         这里MerchandiseV2是父类,Phone是子类.
        MerchandiseV2 m = ph;
        MerchandiseV2 m2 = new Phone(
                "手机002", "Phone002", 100, 1999, 999,
                4.5, 3.5, 4, 128, "索尼", "安卓"
        );

        // >> TODO 但是反之则不行,不能让子类的引用指向父类的对象.因为父类并没有子类的属性和方法.
        //         Phone notDoable = new MerchandiseV2();报错
        // >> TODO 因为子类继承了父类的方法和属性,所以父类的对象能做到的,子类对象也肯定能做到.
        //         也就是说,可以在子类的对象上,执行父类的方法
        // >> TODO 但是当父类的引用指向子类的实例时,只能通过父类的引用像父类一样操作子类的对象.
        //         例如,这里m2实例化了一个Phone对象,但却不能调用Phone的方法,因为其引用的是MerchandiseV2父类
        //         m.getMemoryG();报错,而ph.getMemoryG();则正常.

        // >> TODO 如果确定一个父类的引用指向的对象,实际上就是一个子类的对象(或者子类的子类的对象),那么可以强制类型转换
        Phone aPhone = (Phone) m2;
        System.out.println(aPhone.getMemoryG());
    }
}
```

#### 完整的例子

```java
import supermarket.MerchandiseV2;
import supermarket.Phone;

public class ReferenceAssign {
    public static void main(String[] args) {
        MerchandiseV2 m2 = new Phone(
            "手机002", "Phone002", 100, 1999, 999,
            4.5, 3.5, 4, 128, "索尼", "安卓"
        );
        // MerchandiseV2是Phone的父类,Phone是ShellColorChangePhone的父类
        ShellColorChangePhone shellColorChangePhone = new ShellColorChangePhone("手机002", "Phone002", 100, 1999, 999,
                4.5, 3.5, 4, 128, "索尼", "安卓");
        // TODO 父类的引用,可以指向子类的对象,即可以用子类(以及子类的子类)的引用给父类的引用赋值
        MerchandiseV2 ccm = shellColorChangePhone;

        // TODO 父类的引用,可以指向子类的对象
        // TODO 确定MerchandiseV2的引用ccm是指向的是Phone或者Phone的子类对象,那么可以强制类型转换
        Phone ccp = (Phone) ccm;

        // TODO 确定MerchandiseV2的引用ccm是指向的是ShellColorChangePhone或者ShellColorChangePhone的子类对象
        // TODO 那么可以强制类型转换
        ShellColorChangePhone scp = (ShellColorChangePhone) ccm;

        // TODO 会出错,因为m2指向的是一个Phone类型的对象,不是ShellColorChangePhone的对象
        ShellColorChangePhone notCCP = (ShellColorChangePhone) m2;
        notCCP.calculateProfit();
    }
}
```



