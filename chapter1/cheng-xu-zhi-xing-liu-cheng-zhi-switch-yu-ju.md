# 程序执行流程之switch语句

#### 将阿拉伯数字转换为中文数字

* 使用if可以完成 , 但是略显不够整洁
* 能够根据两个值相比较 , 进入某个代码块最适合这个情况

#### 使用switch语句简化程序

**switch语句的语法**

```java
switch (用于比较的int值) {
    case 目标值1,对应一个if else(xxx):
        匹配后可以执行的语句
    case 目标值2,不可以与别的case子句重复:
        匹配后可以执行的语句
    default(对应最后的else,可选):
        default 语句
}
```

**switch里的case子句中也可以有任意合法的语句 , 比如if-else , for循环等**

#### switch语法中的break

* switch语句如果没有遇到break , 会一直执行下去
* 如果我们的例子没有break会怎么样
* 没有break的情况也有用武之地

#### switch语句语法点总结

* switch语句中用于比较的值 , 必须是int类型
* switch语句适用于有固定多个目标值匹配 , 然后执行不同的逻辑的情况
* 必须使用break语句显示的结束一个case子句 , 否则switch语句会从第一个match的case语句开始执行直到遇到break语句或者switch语句结束
* default子句是可选的 , 如果所有的case语句都没有匹配上 , 才会执行default中的代码
* 不能是switch语句中声明名字相同的变量 , 因为switch中没有{}代码块的包裹

```java
package Procedure;

public class IfElseSwitch {
    public static void main(String[] args) {
        int n = 2;

        String ret = n + "对应的汉字是";

        switch (n) {
            case 1:
                ret = ret + "壹";
                break;
            case 2:
                ret = ret + "贰";
                break;
            case 3:
                ret = ret + "叁";
                break;
            case 4:
                ret = ret + "肆";
                break;
            case 5:
                ret = ret + "伍";
                break;
            case 6:
                ret = ret + "陆";
                break;
            case 7:
                ret = ret + "柒";
                break;
            case 8:
                ret = ret + "捌";
                break;
            case 9:
                ret = ret + "玖";
                break;
            default:
                System.out.println("错误的值" + n + ".值需要大于等于1,小于等于9.");
        }
        System.out.println(ret);
    }
}

```



