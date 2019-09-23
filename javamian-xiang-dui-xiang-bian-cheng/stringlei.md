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

        String str = "Orange_Apple_Banana";

        char[] chars = str.toCharArray();
        for (int i = 0; i < chars.length; i++) {
            System.out.println(chars[i]);
        }

        String[] s = str.split("_");
        for (int i = 0; i < s.length; i++) {
            System.out.println(s[i]);
        }

        int indexOf = str.indexOf('_');
        System.out.println(indexOf);
        System.out.println(str.substring(indexOf+1, str.length()));

        int lastIndexOf = str.lastIndexOf('_');
        System.out.println(lastIndexOf);
        System.out.println(str.substring(0, lastIndexOf));

        System.out.println(str.contains("apple"));
        System.out.println(str.contains("Apple"));
        System.out.println(str.contains("Orange"));
        System.out.println(str.contains("Banana"));

        String str2 = "Orange_Apple_Banana";
        String str3 = "orange_Apple_banana";

        System.out.println(str.equals(str2));
        System.out.println(str.equals(str3));
        System.out.println(str.equalsIgnoreCase(str3));

        String strtrim = " abc ";
        System.out.println(strtrim.trim());
    }
}
```



