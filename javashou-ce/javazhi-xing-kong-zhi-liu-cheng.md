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

#### do...while循环

while与do...while循环的唯一区别是do...while语句至少执行一次 , 即使第一次的表达式为 false . 而在 while 循环中 , 如果第一次条件为 false , 那么其中的语句根本不会执行 . 在实际应用中 , while要比do...while应用的更广 . 它的一般形式如下 :

```java
int b = 10;
// do...while循环语句
do {
    System.out.println("b == " + b);
    b--;
} while (b == 1);
```

#### for循环语句

for循环是经常使用的循环方式 , 第一次迭代前进行初始化 . 形式如下 :

```
for (初始化; 布尔表达式; 步进) {}
```

每次迭代前会测试布尔表达式 . 如果获得的结果是false , 就会执行for语句后面的代码 ; 每次循环结束 , 会按照步进的值执行下一次循环 .

**逗号操作符**

这里不可忽略的一个就是逗号操作符 , Java里唯一用到逗号操作符的就是for循环控制语句 . 在表达式的初始化部分 , 可以使用一系列的逗号分隔的语句 ; 通过逗号操作符 , 可以在for语句内定义多个变量 , 但它们必须具有相同的类型 :

```
for (int i = 1; j = i + 10; i++, j = j * 2) {}
```

**for-each语句**

在Java JDK1.5中还引入了一种更加简洁的 , 方便对数组和集合进行遍历的方法 , 即for-each语句 :

```
int array[] = {7,8,9};
for (int arr : array) {
    System.out.println(arr);
}
```

#### 跳转语句

Java语言中 , 有三种跳转语句 : break , continue , return .

**break语句**

break 语句我们在 switch 中已经见到了 , 它是用于终止循环的操作 , 实际上break语句在for、while、do···while循环语句中 , 用于强行退出当前循环 , 例如 :

```java
for (int i = 0;i < 10;i++) {
    if(i == 5){
      break;
    }
}
```

**continue语句**

continue也可以放在循环语句中 , 它与break语句具有想法的效果 , 作用是用于复制性下一次循环 , 而不是退出当前循环 , 例如 : 

```java
for (int i = 0;i < 10;i++) {
  System.out.printl(" i = " + i );
  if(i == 5){
    System.out.printl("continue ... ");
    continue;
  }
}
```



