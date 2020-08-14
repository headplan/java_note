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

#### switch多分支语句

比if...else语句更优雅的方式是使用switch多分支语句

```java
switch (week) {
  case 1:
    System.out.println("Monday");
    break;
  case 2:
    System.out.println("Tuesday");
    break;
  case 3:
    System.out.println("Wednesday");
    break;
  case 4:
    System.out.println("Thursday");
    break;
  case 5:
    System.out.println("Friday");
    break;
  case 6:
    System.out.println("Saturday");
    break;
  case 7:
    System.out.println("Sunday");
    break;
  default:
    System.out.println("No Else");
    break;
}
```

### 循环语句

循环语句就是在满足一定的条件下反复执行某一表达式的操作 , 直到满足循环语句的要求 . 使用的循环语句主要有 :

```java
for , do...while() , while
```

#### while循环语句

while循环语句的循环方式为利用一个条件来控制是否要继续反复执行这个语句 .  while 循环语句的格式如下 : 

```java
while (布尔值) {
    表达式
}
```

它的含义是 , 当\(布尔值\)为true的时候 , 执行下面的表达式 , 布尔值为false的时候 , 结束循环 , 布尔值其实也是一个表达式 , 比如 : 

```java
int a = 10;
while (a > 5) {
    a--;
}
```



