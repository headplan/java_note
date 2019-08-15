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

* ! 非运算符
* & 且运算符
* && 且且运算符 \(优化后的&\)
* \| 或运算符
* \|\| 或或运算符\(优化后的\|\)

```java
public class BooleanOprt {
    public static void main(String[] args) {
        boolean a = true;
        boolean b = false;

        System.out.println(a && b);
        System.out.println(a & b);
        System.out.println(a || b);
        System.out.println(a | b);

        System.out.println(a || (10 / 0 > 1));
        System.out.println(a | (10 / 0 > 1));
    }
}
```

#### 小括号运算符

小括号运算符内可以包含任何运算符 , 决定运算符的顺序 .

```java
public class ParentOprt {
    public static void main(String[] args) {
        int a = 10;
        int b = 88;
        boolean c = ((a + b) * a - 9 * (a + b)) == (a + b);

        System.out.println(c);
    }
}
```

#### 运算符优先级

* \(\)
* !
* \*,/,%
* +,-
* &gt;,&gt;=,&lt;,&lt;=
* ==
* !=
* &,&&,\|,\|\|
* =

**理解运算符 , 灵活记忆优先级**

为什么等号的优先级最低 ? 赋值 , 右边👉先执行之后才到等号 . 

为什么布尔运算符的优先级低于比较运算符 ? \(a&gt;b \|\| c&lt;d\)

为什么比较运算符的优先级比算术运算符低 ? 计算后比较 . 

#### 理解运算符优先级



