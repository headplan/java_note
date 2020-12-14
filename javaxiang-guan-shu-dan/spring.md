# Spring

Spring框架是一个开放源代码的J2EE应用程序框架 , 由[Rod Johnson](https://baike.baidu.com/item/Rod Johnson/1423612)发起 , 是针对bean的生命周期进行管理的轻量级容器\(lightweight container\) . Spring解决了开发者在J2EE开发中遇到的许多常见的问题 , 提供了功能强大IOC、AOP及Web MVC等功能 . Spring可以单独应用于构筑应用程序 , 也可以和Struts、Webwork、Tapestry等众多Web框架组合使用 , 并且可以与Swing等桌面应用程序AP组合 . 因此 , Spring不仅仅能应用于J2EE应用程序之中 , 也可以应用于桌面应用程序以及小应用程序之中 . Spring框架主要由七部分组成 , 分别是Spring Core、 Spring AOP、 Spring ORM、 Spring DAO、Spring Context、 Spring Web和Spring Web MVC .

Spring是分层的Java SE/EE full-stack轻量级开源框架 , 以 IoC\(Inverse of Control , 控制反转\)和AOP\(Aspect Oriented Programming , 面向切面编程\)为内核 , 使用基本的JavaBean完成以前只可能由EJB完成的工作 , 取代了EJB臃肿和低效的开发模式 .

在实际开发中 , 通常服务器端采用三层体系架构 , 分别为表现层\(web\)、业务逻辑层\(service\)、持久层\(dao\) . 

Spring对每一层都提供了技术支持 , 在表现层提供了与Struts2框架的整合 , 在业务逻辑层可以管理事务和记录日志等 , 在持久层可以整合Hibernate和JdbcTemplate等技术 . 

Spring 具有简单、可测试和松耦合等特点 , 不仅可以用于服务器端的开发 , 也可以应用于任何 Java 应用的开发中 . Spring 框架的主要优点具体如下 . 

#### 方便解耦 , 简化开发

Spring 就是一个大工厂 , 可以将所有对象的创建和依赖关系的维护交给 Spring 管理 . 

#### 方便集成各种优秀框架

Spring 不排斥各种优秀的开源框架 , 其内部提供了对各种优秀框架\(如 Struts2、Hibernate、MyBatis 等\)的直接支持 . 

#### 降低 Java EE API 的使用难度

Spring 对 Java EE 开发中非常难用的一些 API\(JDBC、JavaMail、远程调用等\)都提供了封装 , 使这些 API 应用的难度大大降低 . 

#### 方便程序的测试

Spring 支持 JUnit4 , 可以通过注解方便地测试 Spring 程序 . 

#### AOP 编程的支持

Spring 提供面向切面编程 , 可以方便地实现对程序进行权限拦截和运行监控等功能 . 

#### 声明式事务的支持

只需要通过配置就可以完成对事务的管理 , 而无须手动编程 . 

