# Java中的包和访问修饰符

#### 类太多可以用package管理

* 为了避免类在一起混乱 , 可以把类放在文件夹里 . 这时就需要用package语句告诉Java这个类在哪个package里 . package语句要和源文件的目录完全对应 , 大小写要一致
* package读作包 . 一般来说 , 类都会在包里 , 而不会直接放在根目录
* 不同的包里可以有相同名字的类
* 一个类只能有一个package语句 , 如果有package语句 , 则必须是类的第一行有效代码

#### 类使用太繁琐可以用import

* 当使用另一个包里的类时 , 需要带上包名
* 每次使用都带包名很繁琐 , 可以在使用的类的上面使用import语句 , 一次性解决问题 , 就可以直接使用类了 . 就好像之前用过的Scanner类
* import语句可以有多个
* 如果需要import一个包中的很多类 , 可以使用\*通配符

#### 属性访问修饰符:public

* 被public修饰的属性 , 可以被任意包中的类访问
* 没有**访问修饰符**的属性 , 称作缺省的访问修饰符 , 可以被本包内的其他类和自己的对象访问
* 访问修饰符是一种限制或者允许属性访问的修饰符

#### 类的全限定名

* 包名 + 类名 = 类的全限定名 . 也可以简称为**类的全名** . 
* 同一个Java程序中全限定名字不可重复 . 

```java
package Phone;

import Phone.Parts.Mainboard;
import Phone.Parts.Screen;

public class Phone {
    public Screen screen;
    public Mainboard mainboard;
    public double price;
    public boolean hasFigurePrintUnlocker;

    Phone prePhone;
}
```



