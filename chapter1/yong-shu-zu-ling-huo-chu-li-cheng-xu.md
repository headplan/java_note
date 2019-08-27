# 用数组灵活处理程序

```java
package Array;

import javax.xml.namespace.QName;
import java.util.Scanner;

public class ScoreMaster {
    public static void main(String[] args) {
        int YuWen = 0;
        int ShuXue = 1;
        int WaiYu = 2;
        int WuLi = 3;
        int HuaXue = 4;
        int ShengWu = 5;

        int totScoreCount = 6;

        String[] ScoreNames = new String[totScoreCount];
        ScoreNames[YuWen] = "语文";
        ScoreNames[ShuXue] = "数学";
        ScoreNames[WaiYu] = "外语";
        ScoreNames[WuLi] = "物理";
        ScoreNames[HuaXue] = "化学";
        ScoreNames[ShengWu] = "生物";

        Scanner scanner = new Scanner(System.in);
        System.out.println("请输入共有多少年的成绩:");

        int yearCount = scanner.nextInt();

        double[][] scores = new double[yearCount][totScoreCount];

        for (int i = 0; i < yearCount; i++) {
            for (int j = 0; j < totScoreCount; j++) {
                scores[i][j] = 80 + Math.random() * 20;
                System.out.println("第" + (i + 1) + "年" + ScoreNames[j] + "成绩为:" + scores[i][j]);
            }
        }

        boolean cont = true;
        while (cont) {
            System.out.println("请输入要进行的操作编号");
            System.out.println("1:求某年最好成绩\n" +
                    "2:求某年的平均成绩\n" +
                    "3:求所有年份最好成绩\n" +
                    "4:求某门课程理历年最好成绩");

            int oprtId = scanner.nextInt();

            int year = 0;
            switch (oprtId) {
                case 1:
                    System.out.println("请输入要求哪一年的最好成绩");
                    year = scanner.nextInt() - 1;
                    if (year < 0 || year >= yearCount) {
                        System.out.println("非法的年份");
                        break;
                    }
                    int bestOfYearScoreId = 0;
                    for (int i = 1; i < scores[year].length; i++) {
                        if (scores[year][bestOfYearScoreId] < scores[year][i]) {
                            bestOfYearScoreId = i;
                        }
                    }
                    System.out.println("第" + (year + 1) + "年的最好成绩为" + ScoreNames[bestOfYearScoreId] + ":" + scores[year][bestOfYearScoreId]);
                    break;
                case 2:
                    System.out.println("请输入要求哪一年的平均成绩");
                    year = scanner.nextInt() - 1;
                    if (year < 0 || year >= yearCount) {
                        System.out.println("非法的年份");
                        break;
                    }
                    double totalScore = 0;
                    for (int i = 0; i < scores[year].length; i++) {
                        totalScore += scores[year][i];
                    }
                    System.out.println("第" + (year + 1) + "年的平均成绩为" + (totalScore / ScoreNames.length));
                    break;
                case 3:
                    int bestOfYearsScoreId = 0;
                    year = 0; // 初始化一下,前面有这个变量
                    for (int i = 0; i < scores.length; i++) {
                        for (int j = 0; j < scores[i].length; j++) {
                            if (scores[year][bestOfYearsScoreId] < scores[i][j]) {
                                year = i;
                                bestOfYearsScoreId = j;
                            }
                        }
                    }
                    System.out.println("成绩最好的为第" + (year + 1) + "年的" + ScoreNames[bestOfYearsScoreId] + ",成绩为:" + scores[year][bestOfYearsScoreId]);
                    break;
                case 4:
                    System.out.println("请输入要查询哪门课的历年最好成绩:");
                    int scoreId = scanner.nextInt();
                    year = 0;
                    for (int i = 0; i < scores.length; i++) {
                        if (scores[year][scoreId] < scores[i][scoreId]) {
                            year = i;
                        }
                    }
                    System.out.println(ScoreNames[scoreId] + "历年最好成绩为第" + (year + 1) + "年,成绩为:" + scores[year][scoreId]);
                    break;
                default:
                    System.out.println("程序结束.");
                    cont = false;
            }
        }
    }
}

```



