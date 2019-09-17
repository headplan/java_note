# 参数 : 让Merchandise计算多件商品的总价

```java
// >> TODO 参数是定义在方法名后面的括号里的
// >> TODO 参数定义的规范和变量一样,都是类型名字加标识符,这里的标识符我们叫做参数名.
// >> TODO 方法体中的代码可以使用参数
// >> TODO 参数的值在调用方法的时候需要给出,有的资料叫做实参(实际参数)
//    TODO 对应的,方法定义这里的参数叫做形参(形式参数)
// 如果返回值为负数,代表购买失败,库存不足
public double buy(int countToBuy) {
    if (count < countToBuy) {
        System.out.println("商品库存不足");
        return -1;
    }
    System.out.println("商品单价为" + purchasePrice);

    int fullPriceCount = countToBuy / 2 + countToBuy % 2;
    int halfPriceCount = countToBuy - fullPriceCount;
    double totalCost = purchasePrice * fullPriceCount + halfPriceCount * purchasePrice / 2;

    count -= countToBuy;

    return totalCost;
}

// >> TODO 一个方法可以有多个参数,多个参数之间用逗号隔开
public double buyAndPrintLeft(int countToBuy, boolean printLeft) {
    if (count < countToBuy) {
        System.out.println("商品库存不够");
        if (printLeft) {
            System.out.println("商品剩余库存为" + count);
        }
        return -1;
    }

    System.out.println("商品单价为" + purchasePrice);

    int fullPriceCount = countToBuy / 2 + countToBuy % 2;
    int halfPriceCount = countToBuy - fullPriceCount;
    double totalCost = purchasePrice * fullPriceCount + halfPriceCount * purchasePrice / 2;

    count -= countToBuy;

    if (printLeft) {
        System.out.println("商品剩余库存为:" + count);
    }

    return totalCost;
}

// >> TODO 参数可以是任何类型,包括自定义类型,甚至是自己的类型都没问题
public boolean totalValueBiggerThan(MerchandiseV2 merchandiseV2) {
    return count * purchasePrice > merchandiseV2.purchasePrice * merchandiseV2.count;
}

// >> TODO 参数可以是任何类型,包括自定义类型
public boolean isTheBiggestTotalValueOne(LittleSuperMarket littleSuperMarket) {
    double totalValue = count * purchasePrice;
    for (int i = 0; i < littleSuperMarket.merchandises.length; i++) {
        MerchandiseV2 m = littleSuperMarket.merchandises[i];
        double newTotalValue = m.count * m.purchasePrice;
        if (totalValue < newTotalValue) {
            // 执行到return的时候,方法直接结束,不管是不是在循环中,是在底基层循环中
            return false;
        }
    }
    return true;
}
```



