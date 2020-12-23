# Java版本历史

标准版的Java平台是一个Java2的平台 , 为用户提供一个程序开发环境 . 这个程序开发环境提供了开发与运行Java软件的编译器等开发工具、软件库及Java虚拟机 . 它也是Java2平台、企业版本和Java网页服务的基础 .

**Java**2平台有3个版本 , 它们是适用于小型设备和智能卡的**Java**2平台Micro版\(**Java**2 Platform Micro Edition , **Java**ME\)、适用于桌面系统的Java 2平台标准版\(**Java**2 Platform Standard Edition，Java SE\)、适用于创建服务器应用程序和服务的Java2平台企业版\(**Java**2 Platform Enterprise Edition , Java EE\) .

笼统的讲 , 可以这样理解：

* J2SE是基础 ; 
* 压缩一点 , 再增加一些CLDC等方面的特性就是J2ME ; 
* 扩充一点 , 再增加一些EJB等企业应用方面的特性就是J2EE . 

J2SE包含于J2EE中 , J2ME包含了J2SE的核心类 , 但新添加了一些专有类 .

#### **企业版\(Java EE\)**

> Enterprise Edition\(企业版\) J2EE 包含J2SE 中的类 , 并且还包含用于开发企业级应用的类 . 比如 : EJB、servlet、JSP、XML、事务控制

Java EE是一种利用Java2平台来简化企业解决方案的开发、部署和管理相关的复杂问题的体系结构 . J2EE技术的基础就是核心Java平台或Java2平台的标准版 , Java EE不仅巩固了标准版中的许多优点 , 例如“编写一次、随处运行”的特性、方便存取数据库的JDBC API、CORBA技术以及能够在Internet应用中保护数据的安全模式等等 , 同时还提供了对 EJB\(Enterprise JavaBeans\)、Java Servlets API、JSP\(Java Server Pages\)以及XML技术的全面支持 . 其最终目的就是成为一个能够使企业开发者大幅缩短投放市场时间的体系结构 .

Java EE体系结构提供中间层集成框架用来满足无需太多费用而又需要高可用性、高可靠性以及可扩展性的应用的需求 . 通过提供统一的开发平台 , J2EE降低了开发多层应用的费用和复杂性 , 同时提供对现有应用程序集成强有力支持 , 完全支持EJB , 有良好的向导支持打包和部署应用 , 添加目录支持 , 增强了安全机制 , 提高了性能 .

#### **标准版\(Java SE\)**

> Standard Edition\(标准版\) J2SE 包含那些构成Java语言核心的类 . 比如 : 数据库连接、接口定义、输入/输出、网络编程

Java SE 是Java平台标准版的简称\(Java Platform, Standard Edition\)\(also known as Java 2 Platform\)\) , 用于开发和部署桌面、服务器以及嵌入设备和实时环境中的Java应用程序 . Java SE包括用于开发Java Web服务的类库 . 同时 , Java SE为Java EE和Java ME提供了基础 . Java SE\(Java Platform, Standard Edition , Java标准版\)就是基于JDK和JRE , 包含支持 Java Web 服务开发的类 , 并为 Java 企业级开发提供基础 .

**JavaSE起源**

> Java的安全模型可以追溯到该平台的早期时代 , 当时人们主要将它看作一种增强用户体验的浏览器扩展机制 . 执行的Java代码可以从各种源派生 , 而其中一些的来源是未知的或者不可靠的 . 相应地 , 该平台的安全性最初主要关注的是解决验证被执行的代码可信任的问题 , 而且整个游戏围绕着在浏览器中执行applet . 但是 , 这个模型只是简单地划分为trusted和untrusted部分 , 甚至连中等复杂的应用程序都无法运行 .
>
> 从 1.2 版开始 , Java作为一个编程平台逐渐得到了人们的认可 , 而不再只是一个浏览器扩展 , Sun开始提供更加灵活的安全功能 , 首先是可配置安全策略的概念 . Java文档 介绍了它的发展情况 .
>
> 当Java平台开始进入企业环境时 , 很快就会明显地感觉到 , 纯粹基于代码的功能无法管理大型应用程序的安全性 . Java平台的1.4 版引入了一种叫做Java Authentication and Authorization Service \(JAAS\)的新特性 , 用于将基于用户的权限项整合到安全策略中 . 堆栈上某个特殊代码框架的权限既基于代码的源\(其 CodeSource\) , 又基于验证时分配给用户的身份、组和角色 .

#### **Micro版\(Java ME\)**

> Micro Edition\(微缩版\) J2ME包含J2SE中一部分类 , 用于消费类电子产品的软件开发 . 比如 : 呼机、智能卡、手机、PDA、机顶盒

Java ME是Java微版的简称\(Java Platform,Micro Edition\) , 是一个技术和规范的集合 , 它为移动设备\(包括消费类产品、嵌入式设备、高级移动设备等\)提供了基于Java环境的开发与应用平台 . Java ME分为两类配置 , 一类是面向小型移动设备的CLDC\(Connected Limited Device Profile\) , 一类是面向功能更强大的移动设备如智能手机和机顶盒 , 称为CDC\(Connected Device Profile CDC\) .

### Java版本

从1995年发布1.0版本开始，到目前为止，最新的Java版本是Java 15 : 

| 时间 | 版本 |
| :--- | :--- |
| 1995 | 1.0 |
| 1998 | 1.2 |
| 2000 | 1.3 |
| 2002 | 1.4 |
| 2004 | 1.5 / 5.0 |
| 2005 | 1.6 / 6.0 |
| 2011 | 1.7 / 7.0 |
| 2014 | 1.8 / 8.0 |
| 2017/9 | 1.9 / 9.0 |
| 2018/3 | 10 |
| 2018/9 | 11 |
| 2019/3 | 12 |
| 2019/9 | 13 |
| 2020/3 | 14 |
| 2020/9 | 15 |





