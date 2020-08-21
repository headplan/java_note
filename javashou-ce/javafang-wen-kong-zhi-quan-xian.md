# Java访问控制权限

访问控制权限其实最核心就是一点 : 只对需要的类可见 .

Java中成员的访问权限共有四种 , 分别是public , protected , default , private .

|  | private | default | protected | public |
| :--- | :--- | :--- | :--- | :--- |
| 同一类 | ✅ | ✅ | ✅ | ✅ |
| 同一包中的类 |  | ✅ | ✅ | ✅ |
| 子类 |  |  | ✅ | ✅ |
| 其他包中的类 |  |  |  | ✅ |

#### 继承

继承是所有OOP语言和Java语言都不可或缺的一部分 . 只要我们创建了一个类 , 就隐式的继承自Object父类 , 只不过没有指定 . 如果你显示指定了父类 , 那么你继承于父类 , 而你的父类继承于Object类 .

![](/assets/extends.png)

继承的关键字是extends , 如上图所示 , 如果extends显示指定了继承 , 那么可以说Father是父类 , 而Son是子类 , 用代码表示如下 :

```java
class Father{}

class Son extends Father{}
```

继承双方拥有某种共性的特征

```java
class Father {
    public void feature() {
        System.out.println("父亲的特征");
    }
}

class Son extends Father {

}
```

如果Son没有实现自己的方法的话 , 那么默认就是用的父类的feature方法 . 如果子类实现了自己的feature方法 , 那么就相当于是重写了父类的feature方法 , 就是我们上面提到的重写 .

#### 多态

多态指的是同一个行为具有多个不同表现形式 . 是指一个类实例\(对象\)的相同方法在不同情形下具有不同表现形式 . 封装和继承是多态的基础 , 也就是说，多态只是一种表现形式而已。

如何实现多态 ? 多态的实现具有三种充要条件 :

* 继承
* 重写父类方法
* 父类引用指向子类对象

```java
public class Fruit {
    int num;
    public void eat() {
        System.out.println("eat Fruit");
    }
}

public class Apple extends Fruit {
    @Override
    public void eat() {
        super.num = 10;
        System.out.println("eat " + num + " Apple");
    }

    public static void main(String[] args) {
        Fruit fruit = new Apple();
        fruit.eat();
    }
}
```

可以发现 `main`方法中有一个很神奇的地方 , `Fruit fruit = new Apple()` , Fruit 类型的对象竟然指向了Apple对象的引用 , 这其实就是多态 -&gt; 父类引用指向子类对象 , 因为 Apple 继承于 Fruit , 并且重写了 eat 方法 , 所以能够表现出来多种状态的形式 .

#### 组合

组合其实不难理解 , 就是将对象引用置于新类中即可 . 组合也是一种提高类的复用性的一种方式 . 如果你想让类具有更多的扩展功能 , 需要记住一句话**多用组合 , 少用继承 . **

```java
public class SoccerPlayer {
    private String name;
    private Soccer soccer;
}

public class Soccer {
    private String soccerName;
}
```

代码中SoccerPlayer引用了Soccer类 , 通过引用Soccer类 , 来达到调用soccer中的属性和方法 .

#### 代理

除了继承和组合外 , 另外一种值得探讨的关系模型称为`代理` . 代理的大致描述是 , A想要调用B类的方法 , A不直接调用 , A会在自己的类中创建一个B对象的代理 , 再由代理调用B的方法 .

```java
public class Destination {
    public void todo() {
        System.out.println("control...");
    }    
}

public class Device {
    private String name;
    private Destination destination;
    private DeviceController deviceController;

    public void control(Destination destination) {
        destination.todo();
    }
}

public class DeviceController {
    private Device name;
    private Destination destination;

    public void control(Destination destination) {
        destination.todo();
    }
}
```

#### 向上转型

向上转型代表了父类与子类之间的关系 , 其实父类和子类之间不仅仅有向上转型 , 还有向下转型 , 它们的转型后的范围不一样

* **向上转型** : 通过子类对象\(小范围\)转化为父类对象\(大范围\) , 这种转换是自动完成的 , 不用强制 . 
* **向下转型** : 通过父类对象\(大范围\)实例化子类对象\(小范围\) , 这种转换不是自动完成的 , 需要强制指定 . 

#### static

static是Java中的关键字 , 它的意思是**静态的** , static可以用来修饰成员变量和方法 , static用在没有创建对象的情况下调用**方法/变量** . 

* 用static声明的成员变量为静态成员变量 , 也称为类变量 . 类变量的生命周期和类相同 , 在整个应用程序执行期间都有效 . 

```java
static String name = "headplan";
```

* 使用static修饰的方法称为静态方法 , 静态方法能够直接使用**类名.方法名**进行调用 . 由于静态方法不依赖于任何对象就可以直接访问 , 因此对于静态方法来说 , 是没有 this 关键字的 , 实例变量都会有 this 关键字 . 在静态方法中不能访问类的非静态成员变量和非静态方法 . 



