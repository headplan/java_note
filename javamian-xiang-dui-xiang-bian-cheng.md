# Java面向对象编程

#### 用变量表示商品

商品有标识 , 名字 , 数量 , 价格这几个属性

多个商品怎么办 ? 重复 , 又是重复 !

#### 用类来表示商品

重新认识类\(class\)真正的用途

* 用来描述同一类事物的
* 可以在内部定义任意数量的 , 不同类型的变量 , 作为这一类事物的属性 . 这种属性叫做成员变量
* 有类名 , 类名必须和文件名一样
* 就好像文件路径+文件名不能重复一样 , 一个Java程序中相同名字的类只能有一个

**定义类的语法**

```java
package Class;
// >> TODO 一个类以public class开头,public class代表这个类是公共类,类名必须和文件名相同.
// >> TODO public class后面紧跟类名,然后是一对大括号的类体
public class Merchandise {
    // >> TODO 类体中可以定义描述这个类的属性的变量.我们称之为成员变量(member variable)
    // >> TODO 每个成员变量的定义以;结束
    String name;
    String id;
    int count;
    double price;
}

// >> TODO 上面这整个类,其实就是创建了一个模板.描述了一种我们需要的数据类型.
```



