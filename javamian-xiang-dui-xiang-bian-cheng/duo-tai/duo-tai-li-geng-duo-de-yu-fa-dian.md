# 多态里更多的语法点

静态多态 : 重载 \(Overload\) 同一个类中的相同方法可以有不同的参数 .

动态多态 : 覆盖 \(Override\)

```java
package supermarket;

public class OverloadTestAppMain {
    public static void main(String[] args) {
        LittleSuperMarket superMarket = new LittleSuperMarket("大卖场", "回龙观", 500, 600, 100);
        MerchandiseV2 m = superMarket.getMerchandiseOf(100);

        MerchandiseTest merchandiseTest = new MerchandiseTest();

        System.out.println("-----1-----");
        // TODO:重载调用哪个方法,和参数的引用类型相关,和引用实际指向的类型无关
        merchandiseTest.testMerchandiseOverload(m);
        merchandiseTest.testMerchandiseOverload((Phone) m);
        merchandiseTest.testMerchandiseOverload((ShellColorChangePhone) m);
        // 参数可以为null,但是需要强制类型转换,需要告诉程序类型是什么,否则找不到方法调用
        merchandiseTest.testMerchandiseOverload("");
        merchandiseTest.testMerchandiseOverload((String) null);

        System.out.println("-----2-----");
        // TODO:引用本身是null没关系,确定调用哪个方法只需要引用的类型,也叫静态多态,即在编译期间就知道该调用哪个方法.
        m = null;
        merchandiseTest.testMerchandiseOverload(m);
        merchandiseTest.testMerchandiseOverload((Phone) m);
        merchandiseTest.testMerchandiseOverload((ShellColorChangePhone) m);

        System.out.println("-----3-----");
        // TODO:如果引用类型没有完全匹配,则会根据继承关系,沿着参数当前类型想上寻找
        merchandiseTest.testMerchandiseOverloadNotExactlyMatchType((ShellColorChangePhone) null);

        // TODO:重载总结:静态多态,调用的方法和参数实际指向的对象无关,只和引用本身的类型相关.
        // TODO:因为调用时参数类型是确定的,所以,在编译期间就可以明确的知道哪个方法会被调用.如果有多种可能,则会有编译错误.
        // TODO:如果没有类型完全匹配的候选,则根据类型的继承关系向上寻找,找到最贴近参数类型的那个方法.
        // TODO:无论是静态方法,还是成员方法,重载寻找方法的顺序是一样的.
        // TODO:Java没有多继承.
    }
}
```

```java
package supermarket;

public class OverloadAndOverrideTestAppMain {
    public static void main(String[] args) {
        LittleSuperMarket superMarket = new LittleSuperMarket("大卖场", "回龙观", 500, 600, 100);
        MerchandiseV2 m = superMarket.getMerchandiseOf(100);

        // TODO:让重载的归重载,剩下的是覆盖的舞台
        // TODO:重载决定了要调用参数为int的方法,这个方法要在m指向的对象上执行
        // TODO:分别用true,1,3,6做参数,运行结果是什么?
        m.buy(3);
    }
}
```

引用做参数时 , 只看引用类型 , 引用掉方法的时候 , 看指向的实际对象 .

程序的执行就是找到要执行的代码 , 并且知道执行的代码能访问哪些数据 , 数据从哪里来 . 多态的核心问题就是 , 要调用哪个类的哪个方法 , 这个方法用到的数据\(this引用\)是谁 .

> @Override是伪代码 , 表示重写 . 当然不写@Override也可以 , 不过写上有如下好处 :  
>
> 1. 可以当注释用,方便阅读 . 
> 2. 编译器可以验证@Override下面的方法名是否是父类中所有的,如果没有则报错 .



