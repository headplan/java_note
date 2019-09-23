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



