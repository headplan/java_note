# Java泛型

在JDK1.5中 , 提出了一种新的概念 , 那就是泛型 , 那什么是泛型呢 ?

泛型其实就是一种参数化的集合，它限制了你添加进集合的类型 . 泛型的本质就是一种参数化类型 . 多态也可以看作是泛型的机制 . 一个类继承了父类 , 那么就能通过它的父类找到对应的子类 , 但是不能通过其他类来找到具体要找的这个类 . 泛型的设计之处就是希望对象或方法具有最广泛的表达能力 .

下面来看一个例子说明没有泛型的用法 :

```java
List arrayList = new ArrayList();
arrayList.add("Headplan");
arrayList.add(100);

for (int i = 0; i < arrayList.size(); i++) {
    String item = (String) arrayList.get(i);
    System.out.println("test === ", item);
}
```

这段程序不能正常运行 , 原因是Integer类型不能直接强制转换为String类型 :

```
java.lang.ClassCastException: java.lang.Integer cannot be cast to java.lang.String
```

如果我们用泛型进行改写后 , 示例代码如下

```java
List<String> arrayList = new ArrayList<String>();
arrayList.add(100);
```

这段代码在编译期间就会报错 , 编译器会在编译阶段就能够帮我们发现类似这样的问题 .

### 泛型的使用

#### 用泛型表示类

泛型可以加到类上面 , 来表示这个类的类型

```java
// 此处T可以随便写为任意标识,常见的如T、E、K、V等形式的参数常用于表示泛型
public class GenericDemo<T> {
    // value这个成员变量的类型为T,T的类型由外部执行
    private T value;

    public GenericDemo(T value) {
        this.value = value;
    }

    // 泛型方法getKey的返回值类型为T,T的类型由外部指定
    public T getValue() {
        return value;
    }

    public void setValue(T value) {
        this.value = value
    }
}
```

#### 用泛型表示接口

泛型接口与泛型类的定义及使用基本相同 .

```java
// 定义一个泛型接口
public interface Generator<T> {
    public T next();
}
```

一般泛型接口常用于`生成器(generator)`中 , 生成器相当于对象工厂 , 是一种专门用来创建对象的类 . 

#### 泛型方法

可以使用泛型来表示方法

```java
public class GenericMethods {
    public <T> void f(T x) {
        System.out.println(x.getClass().getName());
    }
}
```



