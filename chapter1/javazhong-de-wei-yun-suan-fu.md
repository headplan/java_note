# Java中的位运算符

#### 字面值的八进制和十六进制

**以0开头的整数为八进制**

* 05就是十进制的5
* 011就是十进制的9

**以0x开头的整数为十六进制**

* 0xF就是十进制的15
* 0x11就是十进制的17

#### 按位运算符

* 按位并\(AND\) & : 两个位都是1 , 结果才是1 . 1 & 1 结果1 , 1 & 0 结果 0
* 按位或\(OR\) \| : 两个位有一个是1 , 结果就是1 . 1 \| 0 结果 1 . 
* 按位异或\(XOR\) ^ : 两个位不一样就是1 , 两个位一样就是0 . 
* 按位取反 ~ : 只要1个操作数 , 把每一位都取反 . 

```java
public class BitCalc {
    public static void main(String[] args) {
        int a = 0xF8; // 二进制:1111 1000
        int b = 0xF4; // 二进制:1111 0100
        int c = 0xFF; // 二进制:1111 1111
        System.out.println(a & b);
        System.out.println(a | b);
        System.out.println(a ^ b);

        System.out.println(~c);
    }
}
```

#### 位移运算符

* &gt;&gt; : 符号位不动\(数字的符号位\) , 其余位右移 , 符号位后边补0 , 又称带符号右移\(原来是正数就是正数 , 原来是负数就是负数\)
* &gt;&gt;&gt; : 符号位一起右移 , 左边补0 , 又称无符号右移 . 
* &lt;&lt; : 左移 , 右边补0 . 左移没有带符号位一说 , 因为符号位在最左侧

```java
public class BitShift {
    public static void main(String[] args) {
        int a = 0x400;
        System.out.println(a);
        System.out.println(a >> 1);
        System.out.println(a >> 2);

        System.out.println(a << 1);
        System.out.println(a << 2);

        int b = -0x400;
        System.out.println(b >> 1);
        System.out.println(b >> 2);

        System.out.println(b << 1);
        System.out.println(b << 2);

        System.out.println(b >>> 1);
        System.out.println(b >>> 2);
    }
}
```

#### 位运算符不会改变原变量的值

* 按位运算符不会改变原本的变量的值
* 位移运算符不会改变原本的变量的值

#### 位运算符用处

* 按位运算符 : 掩码\(MASK\)
* 位移运算符 : 高效除以2\(右移除2 , 左移乘2\)

```java
public class BitOprtUsage {
    public static void main(String[] args) {
        int base = 1;
        int is_student_mask = base; // 0001
        int is_programmer_mask = base << 1; // 0010
        int is_driver_mask = base << 2; // 0100
        int is_painter_mask = base << 3; // 1000

        int data = 5; // 0101
        // 0101 & 0001
        boolean isStudent = (data & is_student_mask) != 0;
        System.out.println(isStudent);
        // 0101 & 0010
        boolean isProgrammer = (data & is_programmer_mask) != 0;
        System.out.println(isProgrammer);
        // 0101 & 0100
        boolean isDriver = (data & is_driver_mask) != 0;
        System.out.println(isDriver);
        // 0101 & 1000
        boolean isPainter = (data & is_painter_mask) != 0;
        System.out.println(isPainter);
    }
}
```



