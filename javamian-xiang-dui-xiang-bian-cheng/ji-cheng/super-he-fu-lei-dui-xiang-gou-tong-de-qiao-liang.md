# super : 和父类对象沟通的桥梁

子类对象里可以认为有一个特殊的父类的对象 , 这个父类对象和子类对象之间通过super关键字来沟通 .

```java
public void describe() {
    System.out.println("此手机商品属性如下");
    super.describe();
    System.out.println("手机厂商为" + brand + "；系统为" + os + "；硬件配置如下：\n" +
        "屏幕：" + screenSize + "寸\n" +
        "cpu主频" + cpuHZ + " GHz\n" +
        "内存" + memoryG + "Gb\n" +
        "存储空间" + storageG + "Gb");
}
```

super看上去非常像是父类的引用 , 使用super可以调用父类的方法和属性\(当然必须满足访问控制符的控制\) , 但它并不是父类的引用 . 

虽然 , 使用super可以调用父类的public属性 , 但是super不是一个自引用 . 明显的例子就是 , 一个方法里可以返回this , 但是不可以返回super , 可以返回super.方法或者super.属性 . 



