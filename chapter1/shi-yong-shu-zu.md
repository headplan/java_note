# 使用数组

#### 什么是数组和数组的语法

**数组的特点是**

* 数组是相同类型的变量的集合 , 所有元素的类型都一样
* 可以指定数组包含的元素个数 , 最多为int的最大值个
* 元素有固定的顺序
* 每个元素都有一个固定的编号 , 称之为索引\(index\) , 从0开始递增 , 类型为int
* 可以像操作变量一样读写数组中的任何一个元素
* 如果说之前的变量是一张有名字的纸 , 可以通过这个名字读写这个变量 ; 数组则是一个有名字的本子 . 本子有一个名字 , 每页纸有一个页码 . 可以通过本子的名字和页码读写对应的数组元素

**创建和使用一个数组的语法**

* 数组元素类型\[\] 变量名 = new数组元素类型\[数组长度\]
* 变量名\[索引\] 可以使用这个变量 , 可以读取也可以给它赋值

#### **用数组处理6门课程的成绩**

**创建数组来表示 6 门课的成绩**

* 创建一个大小为6的double类型的数组
* 创建一个大小为6的String数组 , 代表每门课的名字
* 为每门课创建一个int变量 , 值为这门课的成绩对应的数组的索引 , 以便操作每门课的成绩和名字

**求出最高的成绩**

* 创建一个大小为6的double类型的数组
* 创建一个大小为6的String数组 , 保存每门课的成绩
* 为每门课创建一个int变量 , 值为这门课的成绩对应的数组的索引 , 以便操作每门课的成绩
* 实现计算最高成绩的逻辑

```java
package Array;

public class ScoreArrayMaxScore {
    public static void main(String[] args) {
        int YuWen = 0;
        int ShuXue = 1;
        int WaiYu = 2;
        int WuLi = 3;
        int HuaXue = 4;
        int ShengWu = 5;

        int totScoreCount = 6;
        double[] scores = new double[totScoreCount];

        String[] ScoreNames = new String[totScoreCount];
        ScoreNames[YuWen] = "语文";
        ScoreNames[ShuXue] = "数学";
        ScoreNames[WaiYu] = "外语";
        ScoreNames[WuLi] = "物理";
        ScoreNames[HuaXue] = "化学";
        ScoreNames[ShengWu] = "生物";

        for (int i = 0; i < totScoreCount; i++) {
            scores[i] = 80 + Math.random() * 20;
            System.out.println(ScoreNames[i] + "的成绩是:" + scores[i]);
        }

        double maxScore = 0;
        int maxScoreIndex = -1;

        for (int i = 0; i < totScoreCount; i++) {
            if (scores[i] > maxScore) {
                maxScore = scores[i];
                maxScoreIndex = i;
            }
        }

        System.out.println("最好成绩科目是" + ScoreNames[maxScoreIndex] + ":" + maxScore);
    }
}

```



