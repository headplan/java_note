# 引用的缺省值null

#### 缺省值null

* null是引用类型的缺省值
* null代表空 , 不存在 . 可以读作空
* 引用类型的数组创建出来 , 初始值都是空

#### null带来的问题

* NullPointerException\(NPE\)问题
* 如果不确定 , 使用前要先判断引用是不是空

```java
package Class;

public class CheckBeforeUse {
    public static void main(String[] args) {
        // 数组在创建出来之后,会按照类型给数组中的每个元素赋缺省值.
        // 引用类型的缺省值是null
        Merchandise[] merchandises = new Merchandise[9];
        // 给索引为偶数的引用赋值
        for (int i = 0; i < merchandises.length; i++) {
            if (i % 2 == 0) {
                merchandises[i] = new Merchandise();
            }
        }

        // merchandises[7].name = "不存在的商品,不存在的名字";
        for (int i = 0; i < merchandises.length; i++) {
            if (merchandises[i] != null) {
                merchandises[i].name = "商品" + i;
            }
        }

        for (int i = 0; i < merchandises.length; i++) {
            if (merchandises[i] != null) {
                System.out.println(merchandises[i].name);
            }
        }
    }
}

```



