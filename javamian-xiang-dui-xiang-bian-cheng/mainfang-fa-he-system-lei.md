# main方法和System类

#### main方法

* main方法也只是一个静态的 , 有String\[\]做参数的 , 没有返回值的方法而已 . 特殊性在于Java可以把main方法作为程序入口 . 
* 给main方法传递参数 . 
* 自己试着调用main方法 . 

```java
package LearnClass;

public class LearnMain {
    public static void main(String[] args) {
        System.out.println(args.length);
        for (int i = 0; i < args.length; i++) {
            System.out.println(args[i]);
        }
    }
}
```

```java
package LearnClass;

public class InvokeMain {
    public static void main(String[] args) {
        System.out.println("进入了InvokeMain的main方法");
        LearnMain.main(args);
        System.out.println("InvokeMain的main方法执行结束");
    }
}
```

#### System类



