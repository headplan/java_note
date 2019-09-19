# 静态变量和静态方法

* 尽量不要使用Magic Number
* VIP的折扣作为一个成员变量 , 有些浪费 , 可以写成静态变量
* 静态变量也叫类变量

```java
// >> TODO 静态变量使用 static 修饰符
// >> TODO 静态变量如果不赋值，Java也会给它赋以其类型的初始值
// >> TODO 静态变量一般使用全大写字母加下划线分割。这是一个习惯用法
// >> TODO 所有的代码都可以使用静态变量，只要根据防范控制符的规范，这个静态变量对其可见即可
//    TODO 比如 public 的静态变量，所有的代码都可以使用它
public static double DISCOUNT_FOR_VIP = 0.95;

//    TODO 但是如果没有public修饰符，只能当前包的代码能使用它
static int STATIC_VARIABLE_CURR_PACKAGE_ONLY = 100;
```



