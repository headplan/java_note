# 字符集编码和字符串

#### 什么是字符集和编码

**什么是字符集\(Charset\)**

* 字符集就是字符的集合 . 一般会包含一种语言的字符 . 比如GBK , 是包含所有常用汉字字符的字符集 . ASCII是包含英文字符的字符集 . 
* 字符就是Java中的char , char是character的简写 . 

**什么是编码\(Encoding\)**

* char代表一个字符 , char的本质也是数字 . 将数字映射到字符 , 就叫编码 . 
* 将一个字符集映射到数字 , 就是给这个字符集编码 . 编码是有标准的 , 所有的计算机系统按照同一个编码标准执行 . 
* 有时候编码和字符集会混用 . 

#### 编码和字符集介绍

**常用的字符集简介**

* ASCII码 , ASCII表 : [https://baike.baidu.com/item/ASCII/309296](https://baike.baidu.com/item/ASCII/309296)
* Unicode 包含世界上所有常用字符 , 编码也有几种 , 包括UTF-8\(8-bit Unicode Transformation Format\) , UTF-16等 .
* Unicode , GBK等所有常用的字符集 , 都会兼容ASCII . 举个例子 , 字符A在这些所有常用的字符集里 , 都是对应数字65 .

**Java中的字符集**

Java中用的是UTF-16编码的Unicode . 

UTF-16用16个bit , 即两个byte , 这也是char占用两个byte的原因 . 当把char转成数字的时候 , 需要用int . 

#### ASCII码和转义符\(escape character\)

#### 字符串的"加法"



