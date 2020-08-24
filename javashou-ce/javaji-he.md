# 集合

集合在日常开发中非常常见 , 下面就来详细介绍一下Collection集合框架的家族体系和成员 , 设计与实现 .

![](/assets/jihequantu.png)

### Iterable 接口

实现此接口允许对象成为for-each循环的目标 , 也就是增强for循环 , 它是Java中的一种语法糖 .

```java
List<Object> list = new ArrayList();
for (Object obj:list) {}
```

除了实现此接口的对象外 , 数组也可以用for-each循环遍历 :

```java
Object[] list = new Object[10];
for (Object obj:list) {}
```

**其他遍历方式**



