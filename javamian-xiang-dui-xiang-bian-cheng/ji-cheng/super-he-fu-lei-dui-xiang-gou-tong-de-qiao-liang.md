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



