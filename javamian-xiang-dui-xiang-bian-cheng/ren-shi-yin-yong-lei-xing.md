# 认识引用类型

#### 引用\(reference\)数据类型

Java中的数据类型分为基本数据类型和引用数据类型

```java
package Class;

public class ReferenceAndPrimaryDataType {
    public static void main(String[] args) {
        // >> TODO m1是一个Merchandise类型的引用,只能指向Merchandise类型的实例
        // >> TODO 引用数据类型变量包含两部分信息:类型和实例.也就是说,
        //    TODO 每个引用数据类型的变量(简称引用),都是指向某个类(class/自定义类型)
        // >> TODO 引用的类型信息在创建时就已经确定,可以通过给引用赋值,让其指向不同的实例.
        //         比如,m1就是Merchandise类型,只能指向Merchandise的实例.
        Merchandise m1;
        m1 = new Merchandise();
        Merchandise m2 = new Merchandise();
        Merchandise m3 = new Merchandise();
        Merchandise m4 = new Merchandise();
        Merchandise m5 = new Merchandise();

        // >> TODO 给一个引用赋值,则两者的类型必须一样.m5可以给m1赋值,因为他们类型是一样的.
        m1 = m5;

        System.out.println("m1=" + m1);
        System.out.println("m2=" + m2);
        System.out.println("m3=" + m3);
        System.out.println("m4=" + m4);
        System.out.println("m5=" + m5);

        Merchandise m6 = m1;
        System.out.println("m6=" + m6);
        m6 = m5;
        System.out.println("m6=" + m6);
    }
}
```

#### 引用数据类型和基本数据类型

**引用数据类型和基本数据类型的相同点**

* 都可以用来创建变量 , 可以赋值和使用其值
* 本身都是一个地址

**引用数据类型和基本数据类型的不同点**

* 基本类型变量的值 , 就是地址对应的值 . 引用数据类型的值还是一个地址 , 需要通过二级跳找到实例 .
* 引用数据类型是Java的一种内部类型 , 是对所有自定义类型和数组引用的统称 , 并非特指某种类型 .  

**Java的实例**

```java
Merchandise m1 = new Merchandise();
```

* 使用new操作符可以创建某个类的一个实例 . 在Java程序运行的时候 , **所有这些创建出来的实例**都被Java放在内存里一个叫做堆\(heap\)的地方 . 
* 创建一个实例 , 就是根据类的定义 , 选出需要的放在内存堆里 . 
* 引用里存放的 , 相当于内存地的地址 . 

**引用类型**

引用类型占用的内存大小和JDK相关 , 如果安装的是32位的JDK , 就是32个bit , 4个byte . 安装的是64位的JDK , 就是64个bit , 8个byte . 



