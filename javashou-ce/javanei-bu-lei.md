# Java内部类

内部类的定义非常简单 : **可以将一个类的定义放在另一个类的内部 , 这就是内部类** . 

内部类是一种非常有用的特性 , 定义在类内部的类 , 持有外部类的引用 , 但却对其他外部类不可见 . 

#### 创建内部类

定义内部类非常简单 , 就是直接将一个类定义在外围类的里面 , 如下代码所示 : 

```java
public class OuterClass {
    private String name;
    private int age;
    
    class InnerClass {
        public InnerClass() {
            name = "headplan";
            age = 25;
        }
    }
}
```



