# Math和Scanner

#### Math

* 查看Math类的源代码
* 学习Math中的常用方法
* Math类的文档
  > [https://docs.oracle.com/en/java/javase/12/docs/api/java.base/java/lang/Math.html](https://docs.oracle.com/en/java/javase/12/docs/api/java.base/java/lang/Math.html)

```java
package LearnMath;

import java.util.Random;

public class LearnMath {
    public double abc;

    public static void main(String[] args) {
        // TODO 我们之前调用的都是Math里的静态方法,Math的构造函数就是private的
        //      这意味着不能创建Math类的实例
        System.out.println(Math.random());
        // TODO 归根结底,Math的random是用的Random类来实现的,在java.util包里
        Random random = new Random();
        for (int i = 0; i < 100; i++) {
            // TODO nextInt的返回值是又正负的,所以使用别人的类之前,需要看看文档,避免出现问题
            System.out.println(random.nextInt());
        }

        System.out.println(Math.abs(-9));

        System.out.println(Math.round(-9.5));
        System.out.println(Math.round(-9.8));
        System.out.println(Math.round(9.5));
        System.out.println(Math.round(9.8));
    }
}
```

#### Scanner

* Scanner的作用
* 查看Scanner的源代码和since , 理解public带来的现实中的约束
* 查看Scanner的源代码

```java
package LearnClass;

import java.math.BigInteger;
import java.util.Scanner;

public class LearnScanner {
    public static void main(String[] args) {
        // TODO Scanner是一个方便的可以帮我们从标准输入读取并转换数据的类
        // TODO 注释里@since1.5表示它是从Java5才开始有的
        Scanner scanner = new Scanner(System.in);

        // TODO 但并不是说从Java5开始,这个类就没有了变化
        // TODO 在源代码里搜索一下@since,会发现很多方法是在后续的Java版本中添加进去的
        // TODO 但是private方法就不会有这个文档标识,因为private方法本来就不给用

        System.out.println("请输入一个大的正数");
        BigInteger bigInteger = scanner.nextBigInteger();
        System.out.println("请输入想给这个数加多少");
        BigInteger toBeAdd = scanner.nextBigInteger();
        System.out.println("结果为:" + bigInteger.add(toBeAdd));
    }
}
```

> 注释里@since1.5表示它是从Java5才开始有的 , Java后续的版本也都改为1.6叫Java6 , 1.7叫Java7这种大版本号 .



