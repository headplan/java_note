# Java泛型

在JDK1.5中 , 提出了一种新的概念 , 那就是泛型 , 那什么是泛型呢 ?

泛型其实就是一种参数化的集合，它限制了你添加进集合的类型 . 泛型的本质就是一种参数化类型 . 多态也可以看作是泛型的机制 . 一个类继承了父类 , 那么就能通过它的父类找到对应的子类 , 但是不能通过其他类来找到具体要找的这个类 . 泛型的设计之处就是希望对象或方法具有最广泛的表达能力 . 

下面来看一个例子说明没有泛型的用法 : 

```
List arrayList = new ArrayList();
arrayList.add("Headplan");
arrayList.add(100);

for (int i = 0; i < arrayList.size(); i++) {
    String item = (String) arrayList.get(i);
    System.out.println("test === ", item);
}
```



