# toString方法

可以使用IDE自动生成 , 调用toString方法的地方很多 , 他也是Object中的方法 , 常见的println就调用了toString方法 . 

```java
@Override
public String toString() {
    return "MerchandiseV2{" +
            "name='" + name + '\'' +
            ", id='" + id + '\'' +
            ", count=" + count +
            ", soldPrice=" + soldPrice +
            ", purchasePrice=" + purchasePrice +
            '}';
}
```

在Debug中也会用到toString方法 , 方便IDE展示内容 . 

