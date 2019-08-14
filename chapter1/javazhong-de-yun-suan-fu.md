# Java中的运算符

#### 什么是运算符

* 运算符对一个或者多个值进行运算 , 并得出一个运算结果 . 
* 运算符的运算结果类型有的是固定的 , 有时候会根据被计算的值变化 . 比如两个int相加 , 结果的类型就是int . 两个byte相加 , 返回值的类型就是byte . 
* 混淆点 : 除赋值运算符外 , 运算符本身不会更改变量的值 . 

```java
public class OprtNotChangeVariableValue {
    public static void main(String[] args) {
        int a = 100;

        System.out.println(a + 1);
        System.out.println(a);

        a = a + 6;
        System.out.println(a);
    }
}
```

#### 取模运算符

* 用来计算余数
* 负数也可以被取模
* 负数也可以取模
* 小数也可以取模

```java
public class ModCalc {
    public static void main(String[] args) {
        int num = 10;

        System.out.println(num % 2);
        System.out.println(num % -3);
        System.out.println(num % 4);
        System.out.println(num % 5);
        System.out.println(num % -6);

        int fnum = -10;

        System.out.println(fnum % 2);
        System.out.println(fnum % -3);
        System.out.println(fnum % 4);
        System.out.println(fnum % 5);
        System.out.println(fnum % -6);
    }
}
```

#### 整数的除法运算

int除以int还是int , 不会变成浮点数 .

```java
public class IntegerDiv {
    public static void main(String[] args) {
        int a = 10;
        int b = 3;

        System.out.println(a / b);

        int c = 10;
        double d = 3.0;

        System.out.println(c / d);
    }
}
```

#### 比较运算符和布尔运算符

**比较运算符**

* &gt;
* &gt;=
* &lt;
* &lt;=
* !=
* ==

**布尔运算符**

* !
* &
* &&
* \|
* \|\|

#### 小括号运算符

#### 运算符优先级

#### 理解运算符优先级



