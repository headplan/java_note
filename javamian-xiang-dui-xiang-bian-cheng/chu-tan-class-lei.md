# 初探Class类

Class类是代表类的类 . 每个Class类的实例 , 都代表了一个类 .

```
package supermarket;

import java.lang.reflect.Field;
import java.lang.reflect.Method;

public class ClassOfClassAppMain {
    // 变长参数String...
    public static void main(String... args) throws NoSuchFieldException, NoSuchMethodException {
        LittleSuperMarket superMarket = new LittleSuperMarket("大卖场", "回龙观", 500, 600, 100);
        MerchandiseV2 m100 = superMarket.getMerchandiseOf(100);

        // TODO:Object类里的getClass方法可以得到Class类的实例.
        // TODO:通过一个类的Class实例,可以获取一个类所有的信息,包括成员变量,方法等.
        Class clazz = m100.getClass();
        Class claxx = ShellColorChangePhone.class;

        System.out.println(clazz);
        System.out.println(clazz.getName()); // 获取类的全类名
        System.out.println(clazz.getSimpleName()); // 获取去掉了包名,获取类名

        Field nameField = clazz.getField("name"); // 获取成员变量的定义,这里需要添加异常
        System.out.println(nameField.getName());
        System.out.println(nameField.getType());

        Method equalsMethod = clazz.getMethod("equals", Object.class); // 获取成员方法的定义,这里需要添加异常
        System.out.println(equalsMethod.getReturnType());
        System.out.println(equalsMethod.getParameters());
        Method buyMethod = clazz.getMethod("buy", int.class);
        System.out.println(buyMethod.getTypeParameters());
    }
}
```



