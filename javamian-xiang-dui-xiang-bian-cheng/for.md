# for循环的另一种写法

```java
LittleSuperMarket superMarket = new LittleSuperMarket("大卖场", "世纪大道1号", 500, 600, 100);

MerchandiseV2[] all = superMarket.getMerchandises();

// TODO:只循环遍历,不赋值,不跳跃访问,不需要知道当前元素是第几个
double maxPurchasePrice = -1;
for (MerchandiseV2 m : all) {
    if (m.getPurchasePrice() > maxPurchasePrice) {
        maxPurchasePrice = m.getPurchasePrice();
    }
}
```



