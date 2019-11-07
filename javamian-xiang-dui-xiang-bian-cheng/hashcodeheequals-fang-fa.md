# hashCode和equals方法

* hashCode可以翻译为哈希码 , 或者散列码 . 应该是一个表示对象的特征值的int整数 . 
  * 可以简单的认为对象的内存地址 , 缺省的hashCode的没有实际意义 , 应该自己实现并覆盖Object中的hashCode方法 . 
* equals方法应该用来判断两个对象从逻辑上是否相等 . 

hashCode和equals两个方法是最常覆盖的两个方法 , 基本上也是必须要覆盖的 .

```java
// TODO:覆盖的原则是,equals为true,hashCode就应该相等.这是一种约定俗成的规范
// TODO:即equals为true是hashCode相等的充分非必要条件,hashCode相等是equals为true的必要不充分条件

@Override
public boolean equals(Object o) {
    if (this == o) return true;
    if (!(o instanceof MerchandiseV2)) return false;
    MerchandiseV2 that = (MerchandiseV2) o;
    return getCount() == that.getCount() &&
            Double.compare(that.getSoldPrice(), getSoldPrice()) == 0 &&
            Double.compare(that.getPurchasePrice(), getPurchasePrice()) == 0 &&
            getName().equals(that.getName()) &&
            getId().equals(that.getId());
}

@Override
public int hashCode() {
    return Objects.hash(getName(), getId(), getCount(), getSoldPrice(), getPurchasePrice());
}
```

> 两个引用相等 , 说明指向的对象是同一个 .

#### String类的equals方法

String 类的 equals 方法和 == 判断

