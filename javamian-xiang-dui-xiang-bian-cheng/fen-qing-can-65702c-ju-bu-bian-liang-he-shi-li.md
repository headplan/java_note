# 分清参数,局部变量和对象实例

* 局部变量就是之前所说的变量 , 是在方法体里创建的变量
* 参数和局部变量都是演算纸 , 方法执行完就清除了
* 对象是实体/实例 , 不是变量 . 
  对象创建出来后 , 被堆在一起 , 放在类似公告板的地方 . 
  方法里创建的对象是不会随着方法结束被清楚的 . 
  所以对象的地盘不受限制 , 只要有引用指向一个对象 , 这个对象的数据就可以通过这个引用来访问 . 

```java
// >> TODO 方法的代码可以影响方法之外的数据。我们可以通过指向同一个对象的引用，操作这个对象里的属性
MerchandiseV2 paramRef = littleSuperMarket.merchandises[2];

m.gift = giftBowl;
System.out.println("gift变换大法执行前");
m.describe();
paramRef.describe();
m.changeToTheSameGift(paramRef);
System.out.println("gift变换大法执行后");
paramRef.describe();
```

```java
// ------ 返回值 -------

// >> TODO 给返回值赋值，并不会影响用来充当返回值的变量

MerchandiseV2 giftOfM;

// >> TODO 可以通过返回值，操作同一个对象

System.out.println("获取m的赠品，并修改这个赠品对象的采购价格");
System.out.println("修改前");
m.describe();
giftOfM = m.getGiftAndHowCanOutsideChangeIt();
giftOfM.purchasePrice = giftOfM.purchasePrice * 10;
System.out.println("修改后");
m.describe();
```



