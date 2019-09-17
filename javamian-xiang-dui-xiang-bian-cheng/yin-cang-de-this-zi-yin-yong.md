# 隐藏的this自引用

#### 参数和局部变量重名

会报错

```java
public void setCount(int count) {
    int count;
}
```

#### 使用this访问局部变量的完整形态

当参数和局部变量重名了 , 就可以使用this自引用来访问成员变量 .

每一个方法都有一个隐藏的this自引用\(自指针\) .

```java
public void setCount(int count) {
    // >> TODO 方法里隐藏这一个this自引用,指向调用这个方法的对象
    // >> TODO 使用一个对象调用方法,也叫做在这个对象上调用方法.因为方法可以访问这个对象的值
    // >> TODO 访问一个成员变量的完整形态是"this.成员变量的名字"
    this.count = count;
}
```

如果不存在重名的错误 , Java会在编译时加上 . 

