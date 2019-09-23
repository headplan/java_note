# String类

String对象最重要的特点是 , 不可变\(immutable\) , 重要的事情说三遍 . String用来存储字符的数据是private的 , 而且不提供任何修改内容的方法 , 所以String对象一旦生成 , 其内容就是完全不可能被修改的 . 

#### 常用的String类的方法

```java
package LearnClass;

public class LearnString {
    public static void main(String[] args) {
        String content = "01234567ABCDefgh";

        // String的length()是个方法不是属性
        System.out.println(content.length());

        // 其实是生成了一个新的String对象
        System.out.println(content.toUpperCase());
        System.out.println(content.toLowerCase());

        // content指向对象的内容并没有变化
        System.out.println(content);
        System.out.println(content.charAt(1));
        // System.out.println(content.charAt(99));
        System.out.println(content.substring(5));
        System.out.println(content.substring(1,5));
        // System.out.println(content.substring(1,99));
    }
}
```



