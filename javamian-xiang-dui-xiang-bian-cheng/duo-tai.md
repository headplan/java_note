# 多态

#### 多态到底调用的哪个方法 ?

可以调用那些方法 , 取决于引用类型 . 具体调用哪个方法 , 取决于实例所属的类是什么 .

```java
import supermarket.LittleSuperMarket;

public class PolymorphismAppMainSimple {
    public static void main(String[] args) {
        LittleSuperMarket superMarket = new LittleSuperMarket("大卖场",
                "世纪大道1号", 500, 600, 100);

        // >> TODO 虽然是用的父类的引用指向的不同类型的对象,调用getName方法时,实际执行的方法
        //         取决于对象的类型,而非引用的类型.
        // >> TODO 也就是说,能调用哪些方法,是引用决定的,具体执行哪个类的方法,是引用指向的对象决定的.
        // >> TODO 这就是覆盖的精髓.覆盖是多态的一种,是最重要的一种.

        // >> TODO 以getName为例,父类里有这个方法,所以肯定都可以调用,但是Phone覆盖了父类的getName方法.
        // >> TODO 之前我们使用子类的引用指向子类的对象,调用子类里覆盖父类的方法
        //         比如getName,执行的是子类的getName方法,我们觉得很自然.
        //         现在变换的是,使用父类的引用指向子类的对象,调用被子类覆盖的方法,实际还是子类里的方法.

        // >> TODO 前面引用赋值关系主要是引用赋值之后,对象就不能调用本身类的方法,只能调用引用赋值类的方法.
        //         如果子类中有覆盖,则调用覆盖的方法.

        System.out.println(superMarket.getMerchandiseOf(0).getName());
        System.out.println();
        System.out.println(superMarket.getMerchandiseOf(10).getName());
        // TODO 如果子类里没有覆盖这个方法,就去父类里找,父类里没有,就去父类的父类找.反之只要能让一个引用指向这个对象
        // TODO 就说明这个对象肯定是这个类型或者其子类的的一个实例(否则赋值会发生ClassCastException)总归有父类兜底
        System.out.println();
        System.out.println(superMarket.getMerchandiseOf(100).getName());
    }
}
```

总结 : 无论一个方法是使用哪个引用被调用的 , "它都是在实际的对象上执行的" . 执行的任何一个方法 , 都是这个对象所属的类的方法 . 如果没有就去父类找 , 再没有就去父类的父类找 , 依次寻找直到找到 .

换个角度理解 , 一直说子类里有一个\(特殊的\)父类的对象 . 这时候 , 这个特殊的父类的对象里的this自引用是子类的引用 . 那么自然的即使是在继承自父类的代码里 , 去调用一个方法 , 也是先从子类开始 , 一层层继承关系的找 .

这也是Java选择单继承的重要原因之一 . 在多继承的情况下 , 如果使用不当 , 多态可能会非常复杂 , 以至于使用的代价超过其带来的好处 .

> 1.父类引用指向子类对象 , 可以调用只在父类中的方法\(继承\)
>
> 2.父类引用指向子类对象 , 可以调用子类覆盖了父类的方法\(覆盖 , 多态\)
>
> 3.父类引用指向子类对象 , 在1.和2.这两种情况下 . 如果这个方法的代码中又调用了别的方法 , 那么还是会遵循这个规则 . 举个例子 , 如果父类中有m1 , m2两个方法 . 子类覆盖了m2方法 . 那么如果调用m1 , 则m1中调用的m2还是子类中定义的m2 .



