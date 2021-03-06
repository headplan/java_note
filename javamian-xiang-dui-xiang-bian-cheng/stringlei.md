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

#### 人工智障机器人

```java
package LearnClass;

import java.util.Scanner;

public class LearnAI {
    public static void main(String[] args) {
        LearnAIClass AIClass = new LearnAIClass();
        Scanner in = new Scanner(System.in);
        while (true) {
            String input = in.next();
            if ("exit".equals(input)) {
                System.out.println("再见!");
                break;
            }
            String answer = AIClass.answer(input);
            System.out.println(answer);
        }
    }
}
```

```java
package LearnClass;

public class LearnAIClass {
    public String answer(String question) {
        String ret = null;

        ret = handleCanStart(question);

        if (ret != null) {
            return ret;
        }

        ret = handleAskTail(question);

        if (ret != null) {
            return ret;
        }

        return handleUnknown(question);
    }

    private String handleCanStart(String question) {
        String[] canStart = new String[]{"会", "能", "有", "敢", "在"};
        for (int i = 0; i < canStart.length; i++) {
            if (question.startsWith(canStart[i])) {
                return canStart[i] + "!";
            }
        }
        return null;
    }

    private String handleAskTail(String question) {
        String[] askTail = new String[]{"吗?", "吗？", "吗"};
        for (int i = 0; i < askTail.length; i++) {
            if (question.endsWith(askTail[i])) {
                return question.replace(askTail[i], "!");
            }
        }
        return null;
    }

    private String handleUnknown(String question) {
        return question + "!";
    }
}
```



