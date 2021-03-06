# 基本数据类型的更多语法点

#### 变量要先赋值后使用

* 不给变量赋值代表什么
* 不赋值就使用会怎么样

需要初始化赋值后 , 再使用 .

#### 计算并赋值运算符

为了让代码更简洁 . a = a + 10 , 可以简化为a += 10

```java
+=
-=
/=
*=
%=
&=
^=
|=
<<=
>>=
>>>=
```

#### 数据类型自动转换

**自动类型转换**

* 不会出现问题的类型转换 , 编程语言可以做自动类型转换 , 比如低精度的数字向高精度的数字转换 . 
* 自动类型转换可以发生在算术运算 , 也可以发生在赋值 . 

> 计算结果自动转换为高精度的数

**数值精度顺序** : double &gt; float &gt; long &gt; int &gt; short &gt; byte

**char 可以转换为 int**

* char可以转换为int
* 虽然同样是两个byte , 但是因为char是无符号数 , 值域超出了short可以表示的范围 , 所以不可以自动转为short , 因为short还有负的 . 

#### 强制类型转换和数字溢出

**强制类型转换**

* 可能出现问题的类型转换 , 需要使用强制类型转换 , 比如高精度数值向低精度数值转换 . 
* 强制类型转换也是操作符
* 语法是用小括号括起来的目标类型放在被转换的值前面
* 强制转换会造成数据精度丢失

```java
public class ForceConvert {
    public static void main(String[] args) {
        int intVal = 99;
        long longVal = 19999;
        intVal = (int) longVal;

        System.out.println(intVal);

        float floatVal = 11.32f;
        double doubleVal = 33445566.7788;
        floatVal = (float) doubleVal;

        System.out.println(floatVal);

        int a = 65 + 10;
        char b = (char) a;

        System.out.println(b);
    }
}
```

**数值溢出**

* 数值计算一旦溢出 , 结果将失去其原有意义 . 比如 , 两个正数会加出负数 . 
* 要对能够处理的值有大概的估计 . 

```java
public class ForceConvertValueLoss {
    public static void main(String[] args) {
        int intVal = 99;
        long longVal = 5555555555555L;
        intVal = (int) longVal;

        System.out.println(intVal);

        float floatVal = 11.32f;
        double doubleVal = 123456789.0123456;

        floatVal = (float) doubleVal;
        System.out.println(floatVal);
        System.out.println(doubleVal);
    }
}
```

#### 从数值计算溢出理解程序员和编程语言

**编程语言的作用**

* 编程语言负责按照语法执行
* 编程语言负责和计算机交互

**程序员的任务**

* 程序员负责理解问题
* 程序员负责理解程序 , 并将问题转化为程序
* 编程语言不负责解决问题 , 程序员才负责解决问题



