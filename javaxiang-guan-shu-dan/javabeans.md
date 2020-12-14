# Java Bean

[https://stackoverflow.com/questions/1612334/difference-between-dto-vo-pojo-javabeans](https://stackoverflow.com/questions/1612334/difference-between-dto-vo-pojo-javabeans)

* 在java1996年发布 , 当年12月即发布了java bean1.00-A , 有什么用呢 ? 通过统一的规范可以设置对象的值\(get,set方法\) , 这是最初的java bean ; 
* 在实际企业开发中 , 需要实现事务 , 安全 , 分布式 , javabean就不好用了 . sun公司就开始往上面堆功能 , 这里java bean就复杂为EJB ; 
* EJB功能强大 , 但是太重了 . 此时出现DI\(依赖注入\) , AOP\(面向切面\)技术 , 通过简单的java bean也能完成EJB的事情 , 这里的java bean简化为POJO ; 
* Spring诞生了 . 

#### JavaBean

* JavaBean是公共Java类 , 但是为了编辑工具识别 , 需要满足至少三个条件 :
* 有一个public默认构造器\(例如无参构造器\)属性使用public的get , set方法访问 , 也就是说设置成private , 同时get , set方法与属性名的大小也需要对应 . 例如属性name , get方法就要写成 , `public String getName(){}` .
* 需要序列化 . 这个是框架 , 工具跨平台反映状态必须的 .

`<Think in Java>`里面讲到JavaBean最初是为Java GUI的可视化编程实现的 . 拖动IDE构建工具创建一个GUI组件\(如多选框\) , 其实是工具给你创建java类 , 并提供将类的属性暴露出来给你修改调整 , 将事件监听器暴露出来 .

#### EJB

在企业开发中 , 需要可伸缩的性能和事务、安全机制 , 这样能保证企业系统平滑发展 , 而不是发展到一种规模重新更换一套软件系统 . 然后有提高了协议要求 , 就出现了Enterprise Bean . EJB在javabean基础上又提了一些要求 , 当然更复杂了 .

#### POJO

有个叫Josh MacKenzie人觉得 , EJB太复杂了 , 完全没必要每次都用 , 所以发明了个POJO , POJO是普通的javabean , 什么是普通就是和EJB对应的 . 总之 , 区别就是 , 先判断是否满足javabean的条件 , 然后如果再实现一些要求 , 满足EJB条件就是EJB , 否则就是POJO .

#### 其他

* **PO\(persistence object\)** - 用于持久化时\(例如保存到数据库或者缓存\) ; 
* **VO\(value object\)** - 用于前端展示使用\(例如放置到JSP中解析或者给前端传递数据\) ; 
* **DTO\(data transfer object\)** : 用于接口互相调用返回,数据传输\(例如很多接口调用返回值或消息队列内容\) ; 

Java语言欠缺属性、事件、多重继承功能 . 所以 , 如果要在Java程序中实现一些面向对象编程的常见需求 , 只能手写大量胶水代码 . Java Bean正是编写这套胶水代码的惯用模式或约定 . 这些约定包括getXxx、setXxx、isXxx、addXxxListener、XxxEvent等 . 遵守上述约定的类可以用于若干工具或库 .

假如要用Java实现一个单向链表类 :

```java
// 编译成 java-int-list_1.0.jar
public final class JavaIntList {
  static class Node {
    public Node next;
    public int value;
  }
  public Node head;
  public int size;
}
```

上述实现为了能够快速获取链表的大小 , 把链表大小缓存在size变量中 .

```java
JavaIntList myList = new JavaIntList();
System.out.println(myList.size);
```

JavaIntList的作者很满意 , 于是开源了java-int-list库的1.0版 . 文件名是java-int-list\_1.0.jar . 发布后 , 吸引了许多用户来使用java-int-list\_1.0.jar . 有一天 , 作者决定要节省内存 , 不要缓存size变量了 , 把代码改成这样 :

```java
// 编译成 java-int-list_2.0.jar
public final class JavaIntList {
  static final class Node {
    public Node next;
    public int value;
  }
  public Node head;
  public int getSize() {
    Node n = head;
    int i = 0;
    while (n != null) {
      n = n.next;
      i++;
    }
    return i;
  }
}
```

然后发布了2.0版 : java-int-list\_2.0.jar . 发布后 , 原有java-int-list\_1.0.jar的用户纷纷升级版本到2.0 . 这些用户一升级 , 就发现自己的程序全部坏掉了 , 说是找不到什么size变量 . 于是这些用户就把作者暴打一顿 , 再也不敢用java-int-list库了 .

所以Java标准库中 , 绝对不会出现public int size这样的代码 , 而一定会一开始就写成 :

```java
private int size;
public int getSize() { return size; }
```

让用户一开始就使用getSize , 以便有朝一日修改getSize实现时 , 不破坏向后兼容性 . 这种`public int getSize() { return size; }`的惯用手法 , 就是Java Bean . 

现在 , C\#、Scala等比Java新的面向对象语言自身就提供了语言特性来实现这些常用需求 , 所以根本不需要Java Bean这样繁琐的约定 . 

