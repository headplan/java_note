# hashCode和equals方法

* hashCode可以翻译为哈希码 , 或者散列码 . 应该是一个表示对象的特征值的int整数 . 
  * 可以简单的认为对象的内存地址 , 缺省的hashCode的没有实际意义 , 应该自己实现并覆盖Object中的hashCode方法 . 
* equals方法应该用来判断两个对象从逻辑上是否相等 . 

hashCode和equals两个方法是最常覆盖的两个方法 , 基本上也是必须要覆盖的 .

```java
// TODO:覆盖的原则是,equals为true,hashCode就应该相等.这是一种约定俗成的规范
// TODO:即equals为true是hashCode相等的充分非必要条件,hashCode相等是equals为true的必要不充分条件

@Override
public boolean equals(Object o) {
    if (this == o) return true;
    if (!(o instanceof MerchandiseV2)) return false;
    MerchandiseV2 that = (MerchandiseV2) o;
    return getCount() == that.getCount() &&
            Double.compare(that.getSoldPrice(), getSoldPrice()) == 0 &&
            Double.compare(that.getPurchasePrice(), getPurchasePrice()) == 0 &&
            getName().equals(that.getName()) &&
            getId().equals(that.getId());
}

@Override
public int hashCode() {
    return Objects.hash(getName(), getId(), getCount(), getSoldPrice(), getPurchasePrice());
}
```

> 两个引用相等 , 说明指向的对象是同一个 .

#### String类的equals方法

String 类的 equals 方法和 == 判断 .

```java
package supermarket;

import java.util.Scanner;

public class StringEqualsAppMain {
    public static void main(String[] args) {
        String s1 = "aaabbb";
        String s2 = "aaa" + "bbb";

        // TODO:说好的每次创建一个新的String对象
        System.out.println("s1和s2用==判断结果:" + (s1 == s2));
        System.out.println("s1和s2用equals判断结果:" + (s1.equals(s2)));
        // TODO:打乱Java对String的优化,再试试看
        Scanner scanner = new Scanner(System.in);
        System.out.println("请输入s1");
        s1 = scanner.nextLine();
        System.out.println("请输入s2");
        s2 = scanner.nextLine();
        System.out.println("s1和s2用==判断结果：" + (s1 == s2));
        System.out.println("s1和s2用 equals 判断结果：" + (s1.equals(s2)));
    }
}
```

Java对字符串有一些优化 , 如果创建的字符串不是那么多 , 这些字符串会放在同一个地方 , 如果有相同的字符串 , 就直接返回这个字符串对象 . 上例中 , 如果输入时输入两个特别长的字符串去比较 , ==就会判断为false . 因为"太长了"创建了不同的对象 . 

String还是用equals去比较 , 最好不用==去比较 .

Java虚拟机对字符串的优化 , 具体的行为可能是因不同的jdk版本而不同 . 其实不是jdk优化了== , 而是jdk尽力优化了String对象的创建 , 减少重复创建相同的对象 . Integer这些也是一样的 .

