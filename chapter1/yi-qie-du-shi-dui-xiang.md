# 一切都是对象

尽管Java是基于CPP的 , 但是相比之下 , Java是一种更纯粹的面向对象程序设计语言 .

#### 用引用操纵对象

每种编程语言都有自己的操纵内存中元素的方式 . 有时候 , 必须注意将要处理的数据是什么类型 . 是直接操纵元素 , 还是用某种基于特殊语法的间接表示 .

Java里都会简化 . 一切都被视为对象 , 因此可以采用单一固定的语法 . 尽管如此 , 但操纵的标识符实际上是对象的一个引用 . 可以将这一情形想象成用遥控器来操纵电视 .

即使没有电视 , 遥控器也可以独立存在 . 也就是说有引用 , 并不一定需要有一个对象与它关联 . 因此 , 如果想操纵一个词或句子 , 则可以创建一个String引用 .

```
String s;
```

但这里所创建的只是引用 , 并不是对象 . 如果此时向s发送一个消息 , 就会返回一个运行时错误 . 这是因为此时s实际上没有与任何事物相关联 . 因此 , 一种安全的做法是 : 创建一个引用的同时便进行初始化 .

```
String s = "asdf";
```

这里是Java的特性 , 字符串可以用带引号的文本初始化 . 通常 , 必须对对象采用一种更通用的初始化方法 .

#### 必须由你创建所有对象

一旦创建了一个引用 , 就希望它能与一个新的对象相关联 . 通常用new操作符来实现这一目的 . new关键字的意思是 : 给我一个新对象 . 所以前面的例子可以写成 :

```
String s = new String("asdf");
```

它不仅表示 , 给我一个新的字符串 , 通过初始化字符串 , 给出了怎样产生这个String的信息 . 除了String类型 , Java提供了大量过剩的现成类型 , 还可以自行创建类型 .

**存储到什么地方**

对象放置安排的五个不同地方 :

* **寄存器** - 这是最快的存储区 , 位于处理器内部 . 寄存器数量有限 , 所以按需分配 . 不能直接控制 , 程序中也感觉不到 , 但C/CPP可以想编译器建议寄存器的分配方式 . 
* **堆栈** - 通用RAM , 仅次于寄存器 . Java系统必须知道堆栈内所有项的确切声明周期 , 以便上下移动堆栈指针 , 分配内存 , 当然也限制了一部分灵活性 , 所以某些Java数据存储于堆栈中 , 特别是对象引用 , 但是Java对象并不存储于其中 . 
* **堆** - 一种通用的内存池\(也位于RAM区\) , 用于存放所有的Java对象 . 堆的好处是 , 编译器不需要知道存储的数据在堆里存活多长时间 . 因此 , 在堆里分配存储有很大的灵活性 . 需要一个对象 , 只需要new一下 , 执行代码时 , 会自动在堆里进行存储分配 . 当然 , 代价是进行存储分配时需要更多的时间 . 
* **常量存储** - 常量值通常直接存放在程序代码内部 , 这样做是安全的 , 因为它们永远不会被改变 . 有时 , 在嵌入式系统中 , 常量本身会和其他部分隔离开 , 所以在这种情况下 , 可以选择将其存放在ROM\(只读存储器\)中 . 
* **非RAM存储** - 如果数据完全存活于程序之外 , 那么它可以不受程序的任何控制 , 在程序没有运行时也可以存在 . 其中两个基本的例子是流对象和持久化对象 . 在流对象中 , 对象转化成字节流 , 通常被发送给另一台机器 . 在持久化对象中 , 对象被存放于磁盘上 , 因此 , 即使程序终止 , 它仍可以保持自己的状态 . 
  这种存储方式的技巧在于 : 把对象转化成可以存放在其他媒介上的事务 , 在需要时 , 可以恢复成常规的 , 基于RAM的对象 . Java提供了轻量级持久化的支持 ,  比如JDBC和Hibernate这样的机制提供了更加复杂的在数据库中存储和读取对象信息的支持 .  

#### 永远不需要销毁对象

#### 创建新的数据类型 : 类

#### 方法 , 参数和返回值

#### 构建一个Java程序

#### 第一个Java程序

#### 注释和嵌入式文档

#### 编码风格


