# Java访问控制权限

访问控制权限其实最核心就是一点 : 只对需要的类可见 .

Java中成员的访问权限共有四种 , 分别是public , protected , default , private .

|  | private | default | protected | public |
| :--- | :--- | :--- | :--- | :--- |
| 同一类 | ✅ | ✅ | ✅ | ✅ |
| 同一包中的类 |  | ✅ | ✅ | ✅ |
| 子类 |  |  | ✅ | ✅ |
| 其他包中的类 |  |  |  | ✅ |

#### 继承

继承是所有OOP语言和Java语言都不可或缺的一部分 . 只要我们创建了一个类 , 就隐式的继承自Object父类 , 只不过没有指定 . 如果你显示指定了父类 , 那么你继承于父类 , 而你的父类继承于Object类 .

![](/assets/extends.png)

继承的关键字是extends , 如上图所示 , 如果extends显示指定了继承 , 那么可以说Father是父类 , 而Son是子类 , 用代码表示如下 :

```java
class Father{}

class Son extends Father{}
```

继承双方拥有某种共性的特征

```java
class Father {
    public void feature() {
        System.out.println("父亲的特征");
    }
}

class Son extends Father {

}
```



