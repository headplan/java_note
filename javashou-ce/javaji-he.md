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

jdk 1.8之前`Iterator`只有iterator一个方法 , 就是

```java
Iterator<T> iterator();
```

实现次接口的方法能够创建一个轻量级的迭代器 , 用于安全的遍历元素 , 移除元素 , 添加元素 . 这里面涉及到一个`fail-fast`机制 .

> fail-fast 机制是java集合\(Collection\)中的一种错误机制 . 当多个线程对同一个集合的内容进行操作时 , 就可能会产生fail-fast事件 . 例如 : 当某一个线程A通过iterator去遍历某集合的过程中 , 若该集合的内容被其他线程所改变了 ; 那么线程A访问集合时 , 就会抛出ConcurrentModificationException异常 , 产生fail-fast事件 .

总之一点就是能创建迭代器进行元素的添加和删除的话 , 就尽量使用迭代器进行添加和删除 .

也可以使用迭代器的方式进行遍历 :

```java
for (Iterator it = coll.iterator(); it.hasNext();) {
    System.out.println(it.next());
}
```

#### 顶层接口

**Collection**是一个顶层接口 , 它主要用来定义集合的约定 . 

**List**接口也是一个顶层接口 , 它继承了Collection接口 , 同时也是ArrayList , LinkedList等集合元素的父类 . 

**Set** 接口位于与 List 接口同级的层次上 , 它同时也继承了 Collection 接口 . Set 接口提供了额外的规定 . 它对add、equals、hashCode 方法提供了额外的标准 . 

**Queue** 是和 List、Set 接口并列的 Collection 的三大接口之一 . Queue 的设计用来在处理之前保持元素的访问次序 . 除了 Collection 基础的操作之外 , 队列提供了额外的插入 , 读取 , 检查操作 . 

**SortedSet** 接口直接继承于 Set 接口 , 使用 Comparable 对元素进行自然排序或者使用 Comparator 在创建时对元素提供定制的排序规则 . set 的迭代器将按升序元素顺序遍历集合 . 

**Map** 是一个支持 key-value 存储的对象 , Map 不能包含重复的 key , 每个键最多映射一个值 . 这个接口代替了Dictionary 类 , Dictionary 是一个抽象类而不是接口 . 

#### ArrayList



