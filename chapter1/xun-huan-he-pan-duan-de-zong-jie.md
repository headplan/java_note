# 循环和判断的总结

#### Java中的单行注释

* 以//为开始 , 到这一行结束都是注释内容
* 注释可以是任何内容
* 可以在一行的开始注释 , 也可以在程序内容后面添加注释
* 注释不会对程序有任何影响
* 多行指数/\*注释\*/

#### 生成指定范围内的随机数

**新功能**

Math.random\(\)生成随机数 , 随机数在0到1之间 , 类型是double

**生成一个在指定范围内的随机正整数程序关键点**

* 得到随机数 , Java支持得到0到1的double类型的随机数
* 确定基本的数学方法
* 运用取模运算符
* 使用强制类型转换
* 确保生成的数字在指定的范围内 . 边界思维 , 假设随机数是0或者1 , 结果是多少 ? 假设取模后是0或者mod-1 , 结果会是多少 ?

```java
package Procedure;

public class RandomNumber {
    public static void main(String[] args) {
        double randNum = 0;

        // 要生成一个大于0.5的随机数,只有随机数大于0.5,循环才退出
        while (randNum < 0.5) {
            // 使用Java中的Math.random(),生成一个随机数
            randNum = Math.random();
            System.out.println(randNum);
        }

        System.out.println("大于0.5的随机数是" + randNum);

        int rangeStart = 99;
        int rangeEnd = 180;

        int mod = rangeEnd - rangeStart;
        if (rangeStart < 0 || rangeEnd < 0) {
            System.out.println("开始和结束必须是正数或者0");
        }

        if (mod <= 1) {
            System.out.println("非法的数字范围:(" + rangeStart + "," + rangeEnd + ")");
        }

        for (int i = 0; i < 20; i++) {
            int bigRandom = (int) (Math.random() * rangeEnd * 100);
            // 随机的比较大的数取模,加上起始的数就是99-180之间的随机数
            int numberToGuess = (bigRandom % mod) + rangeStart;

            if (numberToGuess <= rangeStart) {
                numberToGuess = rangeStart + 1;
            } else if (numberToGuess > rangeEnd) {
                numberToGuess = rangeEnd - 1;
            }

            System.out.println("mod=" + mod + ", numberToGuess=" + numberToGuess + ", bigRandom=" + bigRandom);
        }
    }
}
```

#### 从标准输出读取字符串和整数

**新功能**

* Scanner in = new Scanner\(System.in\) 连接标准输入 , 在我们例子里也就是命令行 . in也是变量 , 只是不是基本类型 . 
* in.nextLine\(\)可以从命令行读取一行字符串
* in.nextInt\(\)可以从命令行读取一个正整数
* 点操作符也是Java中的操作符 , 和System.out.println\(\)以及Math.random\(\)中的点是一样的操作符 . 意思就是对点前面的变量进行点后面的操作 . 这里的操作指的是方法 , 也就是前面写过的那么多main方法的那个方法 . 这些操作都是使用一个个的方法 . 使用方法也叫调用方法 , 英文是invoke a method . 
* import java.util.Scanner; 是告诉程序 , Scaner这个类型在哪里 . 
* 创建Scanner类型的变量 , 就是我们提过的工具 , 可以帮我们从标准输出读取数据 . 
* nextLine\(\)和nextInt\(\)两个方法可以从命令行读取一行字符串或者一行字符串代表的整数

```java
package Procedure;

import java.util.Scanner;

public class ReadStringAndIntFromConsole {
    public static void main(String[] args) {
        Scanner in = new Scanner(System.in);

        System.out.println("请问你的名字是?");

        String str = in.nextLine();

        System.out.println(str + ",你好.");
        System.out.println("请问你几岁了?");

        int age = in.nextInt();

        System.out.println("好的," + str + age + "岁了.");
    }
}
```

#### 猜数字的游戏

**善假于物也**

Random方法和readInt方法是两个工具，可以完成一个明确具体的功能

**游戏功能**

* 猜数字 : 生成一个指定范围内的随机正整数 , 从命令行读取一个整数 , 如果和随机数相同 , 就算猜中 . 
* 固定随机数的范围
* 支持每次猜数字游戏的猜测次数 , 在指定次数内没猜对 , 则猜数字失败 , 否则就是成功 . 
* 可以支持退出游戏
* 输出剩余的猜测次数
* 每次猜测后 , 如果未猜中 , 则提示本次猜测的数字比目标数字大还是小
* 游戏结束后 , 输出猜数字游戏的统计
* 没有猜中 , 要输出这次的目标数字
* 可以设置随机数的范围 , 可以设置最大猜测次数

```java
package Procedure;

import java.util.Scanner;

public class GuessNumber {
    public static void main(String[] args) {
        // 创建Scanner从控制台读取输入
        Scanner in = new Scanner(System.in);

        // 游戏设置
        int rangeStart = 1;
        int rangeEnd = 8;
        int guessTotal = 5; // 允许猜的次数

        // 游戏统计
        int totalGameCount = 0; // 游戏次数
        int totalCorrectCount = 0; // 正确次数

        // 是否结束游戏
        boolean stopGame = false;

        while (!stopGame) {
            // 生成指定范围内的随机数
            int mod = rangeEnd - rangeStart;
            if (rangeStart < 0 || rangeEnd < 0) {
                System.out.println("开始和结束必须是正数或者0");
            }
            if (mod <= 1) {
                System.out.println("非法的数字范围:(" + rangeStart + "," + rangeEnd + ")");
            }
            int bigRandom = (int) (Math.random() * rangeEnd * 100);
            int numberToGuess = bigRandom % mod + rangeStart;
            if (numberToGuess <= rangeStart) {
                numberToGuess = rangeStart + 1;
            } else if (numberToGuess > rangeEnd) {
                numberToGuess = rangeEnd - 1;
            }

            // 剩余的猜测次数
            int leftToGuess = guessTotal;
            // 是否记进行游戏并记录次数
            boolean currentGameCounted = false;
            boolean currentGuess = false;

            System.out.println("游戏规则:请输入猜测的数字,范围在(" + rangeStart + "," + rangeEnd + ").输入-1代表结束游戏.");
            while (leftToGuess > 0) {
                System.out.println("剩余猜测次数" + leftToGuess + ".请输入本次猜测的数字:");
                int guess = in.nextInt();
                if (guess < 0) {
                    stopGame = true;
                    System.out.println("用户选择结束游戏.");
                    break;
                }
                if (!currentGameCounted) {
                    totalGameCount++;
                    currentGameCounted = true;
                }
                leftToGuess--;

                if (guess > numberToGuess) {
                    System.out.println("输入的数字比目标数字大");
                } else if (guess < numberToGuess) {
                    System.out.println("输入的数字比目标数字小");
                } else {
                    totalCorrectCount++;
                    currentGuess = true;
                    System.out.println("输入的数字正确!");
                    break;
                }
            }
            if (!currentGuess) {
                System.out.println("本次的目标数字是:" + numberToGuess);
            }
            System.out.println("本轮游戏结束!目前共进行了" + totalGameCount + "次游戏, 其中猜中的次数为" + totalCorrectCount);
        }
    }
}
```



