# 参数和返回值是怎么传递的

* 参数和方法里的局部变量可以认为是一样的东西 . 只是在方法调用之前 , 会用实参给参数的形参赋值 . 
* 发生在代码块里的 , 就让它留在代码块里 . 方法执行完毕 , 参数和方法的局部变量的数据就会被删除回收 . 就好像演算纸 , 作用是计算一个值 , 算好之后 , 演算纸就可以扔了 . 
* 调用一个有返回值的方法时 , 就好像访问一个成员变量

```java
// ----- 参数 -----
// >> TODO 参数的传递,其实就是赋值.左边是形参,右边是括号里的实参.
//    TODO 类似buy(int countToBuy = (c + 2) * 5)
// >> TODO 参数本身可以是一个表达式,只要表达式的值类型可以和参数类型匹配就可以
double totalCost = m.buy((c + 2) * 5);
System.out.println("商品总价为:" + totalCost);

// >> TODO 对于引用类型,参数同样是一个表达式
boolean biggerThan = m.totalValueBiggerThan(littleSuperMarket.merchandises[index + 1]);
System.out.println(biggerThan);

// >> TODO 方法里的代码并不能改变实参的值
//    TODO 方法里使用的参数相当于一个局部变量.使用方法前,会用实参给局部变量赋值

// ----- 返回值 -----
// >> TODO 可以把有返回值的方法,当成一个成员变量,当成一个类型为返回值类型的成员变量
//    TODO 关注于返回值并忽略方法执行的部分,使用返回值,就好像在使用一个成员变量
double soldPrice = m.getIntSoldPrice();
System.out.println(soldPrice);
m.describe();

// >> TODO 给返回值赋值,并不会影响用来充当返回值的变量
```



