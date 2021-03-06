# Java面向对象

面向对象的思想已经逐步取代了过程化的思想 , Java 是面向对象的高级编程语言 , 面向对象语言具有如下特征 :

* 面向对象是一种常见的思想 , 比较符合人们的思考习惯 ; 
* 面向对象可以将复杂的业务逻辑简单化 , 增强代码复用性 ; 
* 面向对象具有抽象 , 封装 , 继承 , 多态等特性 . 

### 类也是一种对象

面向对象的基本概念 , 类 . 它相当于一个系列对象的抽象 , 就比如书籍一样 , 类相当于是书的封面 , 大多数面向对象的语言都使用class来定义类 , 它告诉你它里面定义的对象都是什么 .

```java
class ClassName {
    // body;
}
```

上面声明了一个 class 类 , 现在就可以使用 new 来创建这个对象 :

```
ClassName classname = new ClassName();
```

一般 , 类的命名遵循驼峰原则 , 定义如下 :

> 骆驼式命名法（Camel-Case）又称驼峰式命名法 , 是电脑程式编写时的一套命名规则\(惯例\) . 正如它的名称 CamelCase 所表示的那样 , 是指混合使用大小写字母来构成变量和函数的名字 . 程序员们为了自己的代码能更容易的在同行之间交流 , 所以多采取统一的可读性比较好的命名方式 .

#### 对象的创建

在 Java 中 , **万事万物都是对象** . 这句话相信你一定不陌生 , 尽管一切都看作是对象 , 但是你操纵的却是一个对象的 `引用(reference)` . 在这里有一个很形象的比喻 : 你可以把车钥匙和车看作是一组**对象引用和对象**的组合 . 当你想要开车的时候 , 你首先需要拿出车钥匙点击开锁的选项 , 停车时 , 你需要点击加锁来锁车 . 车钥匙相当于就是引用 , 车就是对象 , 由车钥匙来驱动车的加锁和开锁 . 并且 , 即使没有车的存在 , 车钥匙也是一个独立存在的实体 , 也就是说 , **你有一个对象引用 , 但你不一定需要一个对象与之关联 , **也就是

```
Car carKey;
```

这里创建的只是一你用 , 而并非对象 , 如果想要使用这个引用 , 会返回一个异常 , 告诉你需要一个对象和这个引用进行关联 . 安全的做法是创建对象引用时 , 同时把一个对象赋给它 .

```
Car carKey = new Car();
```

在 Java 中 , 一旦创建了一个引用 , 就希望它能与一个新的对象进行关联 , 通常使用`new`操作符来实现这一目的 .

#### 属性和方法

类的一个最基本的要素就是有属性和方法 .

属性也被称为字段 , 它是类的重要组成部分 , 属性可以是任意类型的对象 , 也可以是基本数据类型 .

```java
class A {
    int a;
    Apple apple;
}
```

类中还应该包括方法 , 方法表示的是**做某些事情的方式** . 方法其实就是函数 , 只不过 Java 习惯把函数称为方法 . 这种叫法也体现了面向对象的概念 .

方法的基本组成包括**方法名称 , 参数 , 返回值和方法体** , 例如

```java
public int getResult() {
  // ...
  return 1;
}
```

其中 , `getResult`就是方法名称、`()`里面表示方法接收的参数、`return`表示方法的返回值 , 注意 : 方法的返回值必须和方法的`参数`类型保持一致 . 有一种特殊的参数类型 - `void`表示方法无返回值 . `{}`包含的代码段被称为方法体 .

#### 构造方法

在 Java 中 , 有一种特殊的方法被称为`构造方法` , 也被称为构造函数、构造器等 . 在 Java 中 , 通过提供这个构造器 , 来确保每个对象都被初始化 . 构造方法只能在对象的创建时期调用一次 , 保证了对象初始化的进行 . 构造方法比较特殊 , 它没有参数类型和返回值 , 它的名称要和类名保持一致 , 并且构造方法可以有多个 , 下面是一个构造方法的示例 :

```java
class Apple {
    int sum;
    String color;

    public Apple() {}
    public Apple(int sum) {}
    public Apple(String color) {}
    public Apple(int sum, String color) {}
}
```

上面定义了一个 Apple 类 , 你会发现这个 Apple 类没有参数类型和返回值 , 并且有多个以 Apple 同名的方法 , 而且各个 Apple 的参数列表都不一样 , 这其实是一种多态的体现 . 在定义完成构造方法后 , 我们就能够创建 Apple 对象了 .

```java
class createApple {
    public static void main(String[] args) {
        Apple apple1 = new Apple();
        Apple apple2 = new Apple(1);
        Apple apple3 = new Apple("red");
        Apple apple4 = new Apple(2, "color");
    }
}
```

如上面所示 , 我们定义了四个 Apple 对象 , 并调用了 Apple 的四种不同的构造方法 , 其中 , 不加任何参数的构造方法被称为默认的构造方法 , 也就是

```
Apple apple1 = new Apple();
```

如果类中没有定义任何构造方法 , 那么JVM会自动生成一个构造方法 , 如下 :

```java
class Apple {
    int sum;
    String color;
}

class createApple {
    public static void main(String[] args) {
        Apple apple1 = new Apple();
    }
}
```

上面代码不会发生编译错误 , 因为 Apple 对象包含了一个默认的构造方法 .

默认的构造方法也被称为默认构造器或者无参构造器 .

这里需要注意的一点是 , 即使JVM会为你默认添加一个无参的构造器 , 但是如果你手动定义了任何一个构造方法 , **JVM就不再为你提供默认的构造器 , 你必须手动指定 , 否则会出现编译错误 . **

#### 方法重载

在 Java 中一个很重要的概念是方法的重载 , 它是类名的不同表现形式 . 我们上面说到了构造函数 , 其实构造函数也是重载的一种 . 另外一种就是方法的重载 :

```java
public class Apple {
    int sum;
    String color;

    public Apple(){}
    public Apple(int sum){}

    public int getApple(int sum) {
        return 1;
    }

    public String getApple(String color) {
        return "color";
    }
}
```

上面的例子 , 有两种重载的方式 , 一种是Apple构造函数的重载 , 一种是getApple方法的重载 .

这里涉及到一个问题 , 要是有几个相同的名字 , Java如何知道你调用的是那个方法呢 ? 这里记住一点即可 , **每个重载的方法都有独一无二的参数列表** . 其中包括参数的类型 , 顺序 , 参数数量等 , 满足一种一个因素就构成了重载的必要条件 .

**重载的条件**

* 方法名称必须相同 . 
* 参数列表必须不同\(个数不同 , 或类型不同 , 参数类型排列顺序不同等\) . 
* 方法的返回类型可以相同也可以不相同 . 
* 仅仅返回类型不同不足以成为方法的重载 . 
* 重载是发生在编译时的 , 因为编译器可以根据参数的类型来选择使用哪个方法 . 

#### 方法的重写

方法的重写与重载虽然名字很相似 , 但却完全是不同的东西 . 方法重写的描述是对子类和父类之间的 . 而重载指的是同一类中的 . 代码如下 :

```java
class Fruit {
    public void eat() {
        System.out.printl('eat fruit');
    }
}

class Apple extends Fruit {
    @Override
    public void eat() {
        System.out.printl('eat apple');
    }
}
```

上面这段代码描述的就是重写的代码 , 可以看到 , 子类 Apple 中的方法和父类 Fruit 中的方法同名 . 所以重写的原则是 :

* 重写的方法必须要和父类保持一致 , 包括返回值类型 , 方法名 , 参数列表也都一样 . 
* 重写的方法可以使用`@Override`注解来标识 
* 子类中重写方法的访问权限不能低于父类中方法的访问权限

### 初始化

#### 类的初始化

在使用new关键字创建一个对象的时候 , 其实是调用了这个对象无参数的构造方法进行的初始化 , 也就是如下这段代码 :

```java
class Car {
    public Car() {}
}
```

这个无参数的构造函数可以隐藏 , 由JVM自动添加 . 也就是说 , 构造函数能够确保类的初始化 .

#### 成员初始化

Java会尽量保证每个变量在使用前都会获得初始化 .

一种是编译器默认指定的字段初始化 , 基本数据类型的初始化 :

| 类型 | 初始值 |
| :--- | :--- |
| boolean | false |
| char | /u0000 |
| byte | \(byte\)0 |
| short | \(short\)0 |
| int | 0 |
| long | 0L |
| float | 0.0f |
| double | 0.0d |

一种是其他对象类型的初始化 , String也是一种对象 , 对象的初始值都是null , 其中也包括基本类型的包装类 .

还有一种是指定数值的初始化 , 例如 :

```
int a = 11;
```

也就是说 , 指定a的初始化值不是0 , 而是11 . 其他基本类型和对象类型也是一样的 .

#### 构造器初始化

可以利用构造器来对某些方法和某些动作进行初始化 , 确定初始值 , 例如 :

```java
public class Counter {
    int i;
    public Counter() {
        i = 11;
    }
}
```

利用构造函数 , 能够把 i 的值初始化为 11 .

#### 初始化顺序

* **静态属性** : static开头定义的属性
* **静态方法块** : static {} 包起来的代码块
* **普通属性** : 非static定义的属性
* **普通方法块** : {} 包起来的代码块
* **构造函数** : 类名相同的方法
* **方法** : 普通方法

```java
public class LifeCycle {
    // 静态属性
    private static String staticField = getStaticField();
    // 静态方法块
    static {
        System.out.println(staticField);
        System.out.println("静态方法块初始化");
    }
    // 普通属性
    private String field = getField();
    // 普通方法块
    {
        System.out.println(field);
    }
    // 构造函数
    public LifeCycle() {
        System.out.println("构造函数初始化");
    }

    public static String getStaticField() {
        String staticField = "Static Field Initial";
        return staticField;
    }

    public static String getField() {
        String field = "Field Initial";
        return field;
    }
    // 主函数
    public static void main(String[] argc) {
        new LifeCycle();
    }
}
```

上面代码的执行结果 , 就反映了初始化顺序 .

**静态属性初始化** -&gt; **静态方法块初始化** -&gt; **普通属性初始化** -&gt; **普通方法块初始化** -&gt; **构造函数初始化**

#### 数组初始化

数组是相同类型的、用一个标识符名称封装到一起的一个对象序列或基本类型数据序列 . 数组是通过方括号下标操作符`[]`来定义使用 .

**数组的定义**

```
int[] a1;
// 或者
int a1[];
```

两种格式的含义是一样的 .

* 直接给每个元素赋值 : int array\[4\] = {1,2,3,4};
* 给一部分赋值 , 后面的都为0 : int array\[4\] = {1,2};
* 由赋值参数个数决定数组的个数 : int array\[\] = {1,2};

**可变参数列表**

Java中一种数组冷门的用法就是可变参数 , 可变参数的定义如下 :

```java
public int add(int... numbers) {
    int sum = 0;
    for (int num : numbers) {
        sum += num;
    }
    return sum;
}
```

然后 , 可以使用下面这几种方式进行可变参数的调用

```java
add(); // 不传参数
add(1); // 传递一个参数
add(2,1); // 传递多个参数
add(new Integer[] {1,2,3}); // 传递数组
```

#### 对象的销毁

虽然Java语言是基于C++的 , 但是它和C/C++一个重要的特征就是不需要手动管理对象的销毁工作 . 在著名的一书 《深入理解 Java 虚拟机》中提到一个观点 :

> Java与C++之间有一堵由内存动态分配和垃圾收集技术所围成的高墙 , 墙外面的人想进去 , 墙里面的人想出来 .

在Java中 , 我们不再需要手动管理对象的销毁 , 它是由`Java 虚拟机`进行管理和销毁的 . 虽然我们不需要手动管理对象 , 但是需要知道`对象作用域`这个概念 .

**对象作用域**

大多数语言都有`作用域(scope)`这个概念 . 作用域决定了其内部定义的变量名的可见性和生命周期 . 在C , C++和Java中 , 作用域通常由{}的位置来决定  , 例如 :

```
{
    int a = 11;
    {
        int b = 12;
    }
}
```

a变量会在两个`{}`作用域内有效 , 而b变量的值只能在它自己的`{}`内有效 .

虽然存在作用域 , 但是不允许这样写 :

```
{
    int x = 11;
    {
        int x = 12;
    }
}
```

这种写法在C/C++中是可以的 , 但是在Java中不允许这样写 , 因为Java设计者认为这样写会导致程序混乱 .

#### **this和super**

this和super都是Java中的关键字 .

this表示的当前对象 , this可以调用方法、调用属性和指向对象本身 . this在Java中的使用一般有三种 :

**指向当前对象**

```java
public class Apple {
    int i = 0;

    Apple eatApple() {
        i++;
        return this;
    }

    public static void main(String[] args) {
        Apple apple = new Apple();
        apple.eatApple().eatApple();
    }
}
```

这里比较有趣的地方就是eatApple\(\)方法可以调用多次 , 在后面还可以继续调用 , 其实就是this原因 , 在`eatApple`方法中加了一个`return this`的返回值 , 也就是说哪个对象调用`eatApple`方法都能返回对象的自身 .

this还可以修饰属性 , 最常见的就是在构造方法中使用this :

```java
public class Apple {
    private int num;

    public Apple(int num) {
        this.num = num;
    }

    public static void main(String[] args) {
        new Apple(10);
    }
}
```

main方法中传递了一个int值为10的参数 , 它表示的就是苹果的数量 , 并把这个数量赋给了num全局变量 . 所以num的值现在就是10 .

this还可以和构造函数一起使用 , 充当一个全局关键字的效果

```java
public class Apple {
    private int num;
    private String color;

    public Apple(int num) {
        this(num, "红色");
    }

    public Apple(String color) {
        this(1, color);
    }

    public Apple(int num, String color) {
        this.num = num;
        this.color = color;
    }
}
```

上面使用的代码不是this , 而是this\(参数\) . 它相当于调用了其他构造方法 , 然后传递参数进去 . 这里注意一点 , this\(\)必须放在构造方法的第一行 , 否则编译不通过 .

如果把this理解为指向自身的一个引用 , 那么super就是指向父类的一个引用 . super关键字和this一样 , 可以使用super.对象来引用父类的成员 :

```java
public class Fruit {
    int num;
    String color;

    public void eat() {
        System.out.println("eat Fruit");
    }
}

public class Apple extends Fruit {
    @Override
    public void eat() {
        super.num = 10;
        System.out.println("eat" + num + "Apple");
    }
}
```

也可以使用super\(参数\)来调用父类的构造函数 , 不在举例 . 

这里比较一下this关键字和super关键字 : 

| 关键字 | this | super |
| :--- | :--- | :--- |
| 调用方式 | 调用本类中的属性 , 构造函数 , 方法 | 调用父类中属性 , 构造函数 , 方法 |
| 调用位置 | 构造函数第一行 , 其他可自行指定 | 构造函数第一行 , 其他可自行指定 |
| 调用次数 | 一个构造函数只能调用一次 | 一个构造函数只能调用一次 |



