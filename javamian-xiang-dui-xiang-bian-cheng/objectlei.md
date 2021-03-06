# Object类

所有的类 , 都直接或者间接的继承自Object类 .

Object类中的方法与Object类引用 , Object没有成员变量 .

```java
package supermarket;

public class TouchObject {
    public static void main(String[] args) {
        Object obj = new Object();
        printObj(obj);

        LittleSuperMarket superMarket = new LittleSuperMarket("大卖场",
                "世纪大道1号", 500, 600, 100);
        printObj(superMarket);
        // TODO:Object引用可以指向任意类的对象
        printObj(superMarket.getMerchandiseOf(0));
        printObj(superMarket.getMerchandiseOf(10));
        printObj(superMarket.getMerchandiseOf(100));
    }

    private static void printObj(Object obj) {
        System.out.println("----" + obj + "的详细内容----");
        System.out.println(obj);
        System.out.println(obj.toString());
        System.out.println(obj.getClass());
        System.out.println(obj.hashCode());
        System.out.println(obj.equals(obj));
    }
}
```

```java
public final native Class<?> getClass();
```

Native说方法没有方法体 , 其方法是用本地代码实现的 , 本地代码可以是C或者Cpp实现的 , 只是一个映射机制 , native表示编译成仅适合当前平台的方法 .

Object可以理解为Java对对象的基本抽象 , 让每个类都有一个getClass方法 , 知道自己是什么类 , 还有hashCode方法 , 用来标识一个对象等等 .

```java
System.out.println("-");
```

最后调用的其实就是obj.toString\(\);

再来看看toString\(\)方法 : 

```java
public String toString() {
    return this.getClass().getName() + "@" + Integer.toHexString(this.hashCode());
}
```



