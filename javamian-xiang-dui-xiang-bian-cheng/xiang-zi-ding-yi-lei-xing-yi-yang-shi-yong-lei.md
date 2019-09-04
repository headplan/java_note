# 像自定义类型一样使用类

#### 类就是一种自定义类型

* 在类定义中可以使用类 , 创建类的引用
* 在类定义中 , 甚至可以使用类自己的类创建引用
* 引用类型的缺省值是null . 一个类定义中如果有引用 , 创建出来的实例 , 其缺省值是null . 

```java
package Phone;

public class PhoneMaker {
    public static void main(String[] args) {
        // 创建一个Phone的实例
        Phone phone = new Phone();

        // 可以设置断点查看实例内部状态

        phone.hasFigurePrintUnlocker = true;
        phone.price = 2999.9;
        // 创建一个Screen的实例,给phone实例的screen引用赋值
        phone.screen = new Screen();
        // 通过引用phone找到Phone的对象,通过screen找到Screen对象,并给其中的属性赋值
        phone.screen.producer = "京东方";
        phone.screen.size = 6.6;

        Mainboard mainboard = new Mainboard();

        mainboard.model = "FA888";
        mainboard.year = 2019;
        mainboard.cpu = new CPU();
        mainboard.cpu.speed = 3.5;
        mainboard.memory = new Memory();
        mainboard.memory.producer = "三星";
        mainboard.memory.capacity = 4;
        mainboard.storage = new Storage();
        mainboard.storage.producer = "Intel";
        mainboard.storage.capacity = 256;
        
        phone.mainboard = mainboard;
        // 上一个版本的手机
        phone.prePhone = new Phone();
    }
}
```



