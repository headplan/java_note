# Java基本语法

### 数据类型

在Java中 , 数据类型只有四类八种 :

整数型 , 浮点型 , 字符型 , 布尔型

#### 整数型

byte - 也就是字节 , 1 byte = 8 bits , byte的默认值是0 ;

short - 占用两个字节 , 也就是16位 , 1 short = 16 bits , 默认值也是0 ;

int 占用四个字节 , 也就是32位 , 1 int = 32 bits , 默认值是0 ;

long 占用八个字节 , 也就是64位 , 1 long = 64 bits , 默认值是0L ;

整数型的占用字节大小空间为 long &gt; int &gt; short &gt; byte .

#### 浮点型

浮点型有两种数据类型

float - 单精度浮点型 , 占用4位 , 1 float = 32 bits , 默认值是0.0f ;

double 是双精度浮点型 , 占用8位 , 1 double = 64 bits , 默认值是0.0d ;

#### 字符型

字符型是char , char类型是一个单一的16位Unicode字符 , 最小值是\u0000 \(也就是0\) , 最大值是\uffff\(即65535\) , char数据类型可以存储任何字符 , 例如 char a = 'A' .

#### 布尔型

布尔型指的就是boolean , boolean只有两种值 , true或者是false , 只表示1位 , 默认值是false .

上面所说的位都指的是内存中的占用 .

![](/assets/shujuleixing.png)

### 基础语法

* 大小写敏感 : Java是对大小写敏感的语言 , 例如Hello与hello是不同的 , 这其实就是Java的字符串表示方式 . 
* 类名 : 对于所有的类来说 , 首字母应该大写 , 例如`MyFirstClass`
* 包名 : 包名应该尽量保证小写 , 例如my.first.package
* 方法名 : 方法名首字母需要小写 , 后面每个单词字母都需要大写 , 例如`myFirstMethod()`

### 运算符

运算符不只Java中有 , 其他语言也有运算符 , 运算符是一些特殊的符号 , 主要用于数学函数 , 一些类型的赋值语句和逻辑比较方面 . 



