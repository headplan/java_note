# StringBuilder类

StringBuilder是一个非常方便的用来拼接和处理字符串的类 , 和String不同的是 , 它是可变的 .

```java
package LearnClass;

public class LearnStringBuilder {
    public static void main(String[] args) {
        // TODO StringBuilder首先是可变的
        // TODO 而且对它进行操作的方法,都会返回this自引用.
        //      这样就可以一直点下去,对String进行构造.
        StringBuilder strBuilder = new StringBuilder("start");

        long longVal = 123456789;

        strBuilder.append(true).append("abc").append(longVal);

        System.out.println(strBuilder.toString());
        System.out.println(strBuilder.reverse().toString());
        System.out.println(strBuilder.reverse().toString());
        System.out.println(strBuilder.toString());

        System.out.println(strBuilder.delete(0, 4).toString());

        System.out.println(strBuilder.insert(3, "LLLLL").toString());

    }
}

```



