# 多维数组

创建一个二维数组 , 二维数组是一位数组的自然延伸

* double\[\]\[\] scores = new double\[3\]\[6\]

```java
package Array;

public class MultiDimensionArray {
    public static void main(String[] args) {
        // 创建一个double类型的二维数组
        double[][] multiDimensionArr = new double[3][5];

        // 循环查看每个数组元素的值,在给数组元素赋值前,数组元素的值其实都是每种类型的初始值
        for (int i = 0; i < multiDimensionArr.length; i++) {
            for (int j = 0; j < multiDimensionArr[i].length; j++) {
                System.out.println("multiDimensionArr[" + i + "][" + j + "]=" + multiDimensionArr[i][j]);
            }
        }

        multiDimensionArr[2] = new double[100];
        for (int i = 0; i < multiDimensionArr.length; i++) {
            System.out.println("multiDimensionArr[" + i + "]=" + multiDimensionArr[i].length);
        }
    }
}
```

```java
package Array;

import java.util.Scanner;

public class OneYearOneArray {
    public static void main(String[] args) {
        // 声明六个变量,分别代表六门科目的成绩
        int YuWenIndex = 0;
        int ShuXueIndex = 1;
        int WaiYuIndex = 2;
        int WuLiIndex = 3;
        int HuaXueIndex = 4;
        int ShengWuIndex = 5;

        // 每门课的名字
        String[] names = new String[6];
        names[YuWenIndex] = "语文";
        names[ShuXueIndex] = "数学";
        names[WaiYuIndex] = "外语";
        names[WuLiIndex] = "物理";
        names[HuaXueIndex] = "化学";
        names[ShengWuIndex] = "生物";

        // 每门课的成绩
        double[] year1 = new double[6];

        // 用随机数给成绩赋值
        for (int i = 0; i < 6; i++) {
            year1[i] = 80 + Math.random() * 20;
        }

        // 每门课的成绩
        double[] year2 = new double[6];

        // 用随机数给成绩赋值
        for (int i = 0; i < 6; i++) {
            year2[i] = 80 + Math.random() * 20;
        }

        // 每门课的成绩
        double[] year3 = new double[6];

        // 用随机数给成绩赋值
        for (int i = 0; i < 6; i++) {
            year3[i] = 80 + Math.random() * 20;
        }

        double[] yearToUse;

        Scanner scanner = new Scanner(System.in);
        System.out.println("请输出要查询第几年的成绩:");
        int year = scanner.nextInt();

        switch (year) {
            case 1:
                yearToUse = year1;
                break;
            case 2:
                yearToUse = year2;
                break;
            case 3:
                yearToUse = year3;
                break;
            default:
                System.out.println("输入的年份不对,返回最新一年的成绩");
                yearToUse = year3;
                break;
        }

        System.out.println("请输入要查看的成绩编号:");
        int scoreIndex = scanner.nextInt();
        System.out.println("第" + year + "年的" + names[scoreIndex] + "的成绩是:" + yearToUse[scoreIndex]);
    }
}
```

```java
package Array;

import java.util.Scanner;

public class OneArrayForAll {
    public static void main(String[] args) {
        // 声明六个变量,分别代表六门科目的成绩
        int YuWenIndex = 0;
        int ShuXueIndex = 1;
        int WaiYuIndex = 2;
        int WuLiIndex = 3;
        int HuaXueIndex = 4;
        int ShengWuIndex = 5;

        // 每门课的名字
        String[] names = new String[6];
        names[YuWenIndex] = "语文";
        names[ShuXueIndex] = "数学";
        names[WaiYuIndex] = "外语";
        names[WuLiIndex] = "物理";
        names[HuaXueIndex] = "化学";
        names[ShengWuIndex] = "生物";

        Scanner in = new Scanner(System.in);
        System.out.println("请问要保存几年的成绩?");

        int yearToStore = in.nextInt();
        double[][] scores = new double[yearToStore][names.length];

        for (int i = 0; i < yearToStore; i++) {
            for (int j = 0; j < names.length; j++) {
                scores[i][j] = 80 + Math.random() * 20;
            }
        }

        System.out.println("请问你要查看第几年的成绩?");
        int year = in.nextInt() - 1;
        System.out.println("请输入要查看的课程编号");
        int scoreIndex = in.nextInt() - 1;
        System.out.println("第" + (year + 1) + "年的" + names[scoreIndex] + "的成绩是:" + scores[year][scoreIndex]);
    }
}
```



