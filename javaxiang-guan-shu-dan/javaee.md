# JavaEE

#### J2EE的概念

目前Java 2平台有3个版本 , 它们是适用于小型设备和智能卡的Java 2平台Micro版\(Java 2 Platform Micro Edition , J2ME\)、适用于桌面系统的Java 2平台标准版\(Java 2 Platform Standard Edition , J2SE\)、适用于创建服务器应用程序和服务的Java 2平台企业版\(Java 2 Platform Enterprise Edition，J2EE\) .

J2EE是一种利用Java 2平台来简化企业解决方案的开发、部署和管理相关的复杂问题的体系结构 . J2EE技术的基础就是核心Java平台或Java 2平台的标准版 , J2EE不仅巩固了标准版中的许多优点 , 例如”编写一次、随处运行”的特性、方便存取数据库的JDBC API、CORBA技术以及能够在Internet应用中保护数据的安全模式等等 , 同时还提供了对 EJB\(Enterprise JavaBeans\)、Java Servlets API、JSP\(Java Server Pages\)以及XML技术的全面支持 . 其最终目的就是成为一个能够使企业开发者大幅缩短投放市场时间的体系结构 .

J2EE体系结构提供中间层集成框架用来满足无需太多费用而又需要高可用性、高可靠性以及可扩展性的应用的需求 . 通过提供统一的开发平台 , J2EE降低了开发多层应用的费用和复杂性 , 同时提供对现有应用程序集成强有力支持 , 完全支持Enterprise JavaBeans , 有良好的向导支持打包和部署应用 , 添加目录支持 , 增强了安全机制 , 提高了性能 .

**PS : J2EE全称为Java2 Platform Enterprise Edition . "J2EE平台本质上是一个分布式的服务器应用程序设计环境一个Java环境 , 它提供了 , 宿主应用的一个运行基础框架环境和一套用来创建应用的Java扩展API . "**

#### Java与J2EE

随着Internet网络的迅速发展 , 基于互联网的企业应用要求软件平台具有开放性、分布性和平台无关性 . 于是就相继出现了RPC/COM/CORBA等技术 , 但这些技术在实际应用中存在着许多不足和局限 . 它们的特定协议难以通过防火墙 , 因而不适于Web上的应用开发 . 为了进一步开发基于Web的应用 , 出现了Sun公司的Sun ONE\(Open Net Environment 开发网络环境\)和Microsoft公司的.NET等Web服务技术体系 . 

Sun ONE体系结构以Java语言为核心 , 包括J2SE/J2EE/J2ME和一系列的标准、技术及协议 . 它包括Sun独有的iPlanet软件系列 , 其中有在市场上受欢迎的LDAP目录服务器软件 , 以及Forte for Java - 便于在任何环境下书写Java语言的软件工具 . 我们很容易就能从网上免费获得和使用包括Java集成开发环境、Java数据库和中间件\(Application Server\)服务器等产品 , 以及它们的源代码 . Sun ONE更接近或能满足互联网在智能化Web服务方面对分布性、开发性和平台无关性的要求 . 

随着Java技术的不断发展 , 它根据市场进一步细分为 : 针对企业网应用的J2EE\(Java 2 Enterprise Edition\)、针对普通PC应用的J2SE\(Java 2 Standard Edition\)和针对嵌入式设备及消费类电器的J2ME\(Java 2 Micro Edition\)三个版本 . 本文就Sun ONE的Java核心应用 - J2SE/J2EE/J2ME作一些介绍 . 



