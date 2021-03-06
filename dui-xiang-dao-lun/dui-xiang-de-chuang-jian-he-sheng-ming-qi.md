# 对象的创建和生命期

在使用对象时 , 最关键的问题之一是它们的生成和销毁方式 . 每个对象为了生存都需要资源 , 尤其是内存 . 当我们不再需要一个对象时 , 它必须被清理掉 , 使其占有的资源可以被释放和重用 .

为了追求最大的执行速度 , 对象的存储空间和生命周期可以在编写程序时确定 , 这可以通过将对象置于堆栈或静态存储区域内来实现 . 这种方式将存储空间分配和释放置于优先考虑的位置 , 某些情况下这样控制非常有价值 . 但是 , 也牺牲了灵活性 , 因为必须在编写程序时知道对象确切的数量 , 生命周期和类型 .

还有一种方式 , 在被称为堆的内存池中动态的创建对象 . 在这种方式中 , 知道运行时才知道需要多少对象 , 它们的生命周期如何 , 以及它们的具体类型是什么 . 这些问题的答案只能在程序运行时相关代码被执行到的那一刻才能确定 . 如果需要一个新对象 , 可以在需要的时刻直接在堆中创建 . 因为存储空间是在运行时被动态管理的 , 所以需要大量的时间在堆中分配存储空间 , 这可能远远大于在堆栈中创建存储空间的时间 . 不像堆栈一条汇编指令 , 在栈顶指针向下移动和将栈顶指针向上移动 .

Java完全采用了动态内存分配方式 , 每当想要创建新对象时 , 就要使用new关键字来构建此对象的动态实例 . 

**对象的生命周期**

对于允许在堆栈上创建对象的语言 , 编译器可以确定对象存货的时间 , 并可以自动销毁它 . 然而在堆上创建对象 , 编译器就会对它的声明周期一无所知 . 

Java提供了被称为垃圾回收期的机制 , 自动发现对象何时不再被使用 , 并继而销毁它 . 垃圾回收器非常有用 , 它提供了更高层的保障 , 可以避免暗藏的内存泄露问题 . 

Java的垃圾回收器被设计用来处理内存释放问题 , 尽管不包括清理对象的其他方面 . 但垃圾回收器知道对象何时不再被使用 , 并自动释放对象占用的内存 . 这一点同所有对象都是继承自单根基类Object以及智能以一种方式创建对象\(在堆上创建\)这两个特点结合起来 , 使得用Java编程的过程较之用CPP编程要简单的多 , 所要做的决策和要克服的障碍也要少得多 . 



