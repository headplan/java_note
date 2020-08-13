# Java执行控制流程

在Java中 , 流程控制会涉及到包括**if-else、while、do-while、for、return、break**以及选择语句`switch`.

### 条件语句

条件语句可根据不同的条件执行不同的语句 . 包括if条件语句与switch与多分支语句 .

#### if条件语句

if 语句可以单独判断表达式的结果 , 表示表达的执行结果 , 例如 :

```java
int a = 10;
if (a > 10) {
    return true;
}

return false;
```

#### if...else条件语句

if语句还可以与else连用 , 通常表现为**如果满足某种条件 , 就进行某种处理 , 否则就进行另一种处理** . 

```java
int a = 10;
int b = 11;

if (a >= b) {
    System.out.println("a >= b");
} else {
    System.out.println("a < b");
}
```

if后的\(\)内的表达式必须是boolean型的 . 如果为true , 则执行if后的复合语句 ; 如果为false , 则执行else后的复合语句 . 

#### if...else if 多分支语句

上面中的 if...else 是单分支和两个分支的判断 , 如果有多个判断条件 , 就需要使用**if...else if**

```java
int x = 40;
if (x > 60) {
  System.out.println("x的值大于60");
} else if (x > 30) {
  System.out.println("x的值大于30但小于60");
} else if (x > 0) {
  System.out.println("x的值大于0但小于30");
} else {
  System.out.println("x的值小于等于0");
}
```



