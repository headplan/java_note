# Java中的基本数据类型

#### 认识二进制

**十进制**

* 每一位可以是0~9这10个值 , 到10进位 . 一百用十进制表示就是100 , 十就是10 . 

**二进制**

* 每一位可以是0和1这两个值 , 到2进位 . 一百用二进制表示就是1100100 , 十就是1010 . 

**十六进制**

* 每一位可以是0~F这16个值 , 到16进位 . 一百用十六进制表示就是64 , 十就是A . 

**bit和byte**

* 一个二进制的位叫做一个bit , 网络带宽中的单位 , 就是bit . 
* 八个二进制的位 , 组成一个byte . 硬盘等存储的单位 , 都是byte . 
* byte是计算机中基本的衡量存储的单位 , 计算机在对外使用时不会用bit作为划分存储的单位 . 

就像去办理一个100M的宽带 , 实际下载速度就是12,13M . 除以8了 .

#### 数字的基本数据类型

**整数类型**

* byte占用1个byte , 值域是-128~127
* short占用2个byte , 值域是-32768~32767
* int占用4个byte , 值域是-2147483648~2147483647 . Java中整数缺省是int类型的 . 
* long占用8个byte , 值域是-9223372036854774808~9223372036854774807

**浮点类型**

* float有精度 , 值域复杂±340282346638528859811704183484516925440
* double精度是float的一倍 , 占用8个byte . Java中整数缺省是double类型 . 

**符号位**

理解值域 , byte的符号位去掉的话 , 就可以到256 , 因为有±符号位 , 所以byte的值域是-128~127

#### 布尔和字符数据类型

* boolean占用4个byte , 值域是true,false
* char占用2个byte , 值域是所有字符\(最多65535个\)

#### 使用各种基本数据类型

```java
public class PrimaryTypes {
    public static void main(String[] args) {
        byte byteVal = 99;
        System.out.println(byteVal);

        short shortVal = -30000;
        System.out.println(shortVal);

        int intVal = 300000;
        System.out.println(intVal);

        long longVal = 999999999999999L;
        System.out.println(longVal);

        float floatVal = 134.11111111F;
        System.out.println(floatVal);

        double doubleVal = 100.11111111;
        System.out.println(doubleVal);

        boolean condition = true;
        boolean fcondition = false;
        System.out.println(condition);
        System.out.println(fcondition);

        char ch = 'A';
        System.out.println(ch);
    }
}
```

* 例程
* L后缀
* 感受浮点数精度
* 整数缺省是int类型 , 浮点数缺省是double类型
* 编译错误的定位和修正



