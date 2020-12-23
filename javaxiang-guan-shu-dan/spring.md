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

### 框架特征

#### 轻量

从大小与开销两方面而言Spring都是轻量的 . 完整的Spring框架可以在一个大小只有1MB多的JAR文件里发布 . 并且Spring所需的处理开销也是微不足道的 . 此外 , Spring是非侵入式的 : 典型地 , Spring应用中的对象不依赖于Spring的特定类 . 

#### 控制反转

Spring通过一种称作控制反转\(IoC\)的技术促进了低耦合 . 当应用了IoC , 一个对象依赖的其它对象会通过被动的方式传递进来 , 而不是这个对象自己创建或者查找依赖对象 . 你可以认为IoC与JNDI相反 - 不是对象从容器中查找依赖 , 而是容器在对象初始化时不等对象请求就主动将依赖传递给它 . 它的底层设计模式采用了工厂模式 , 所有的Bean都需要注册到Bean工厂中 , 将其初始化和生命周期的监控交由工厂实现管理 . 程序员只需要按照规定的格式进行Bean开发 , 然后利用XML文件进行bean的定义和参数配置 , 其他的动态生成和监控就不需要调用者完成 , 而是统一交给了平台进行管理 . 

控制反转是软件设计大师 Martin Fowler在 2004 年发表的”Inversion of Control Containers and the Dependency Injection pattern”提出的 . 这篇文章系统阐述了控制反转的思想 , 提出了控制反转有依赖查找和依赖注入实现方式 . 控制反转意味着在系统开发过程中 , 设计的类将交由容器去控制 , 而不是在类的内部去控制 , 类与类之间的关系将交由容器处理 , 一个类在需要调用另一个类时 , 只要调用另一个类在容器中注册的名字就可以得到这个类的实例 , 与传统的编程方式有了很大的不同 , "不用你找 , 我来提供给你" , 这就是控制反转的含义 . 

#### **面向切面**

Spring提供了面向切面编程的丰富支持 , 允许通过分离应用的业务逻辑与系统级服务事务进行内聚性的开发 . 应用对象只实现它们应该做的 - 完成业务逻辑 - 仅此而已 . 它们并不负责其它的系统级关注点 , 例如日志或事务支持 . 

#### **容器**

Spring包含并管理应用对象的配置和生命周期 , 在这个意义上它是一种容器 , 你可以配置你的每个bean如何被创建 - 基于一个可配置原型\(prototype\) , 你的bean可以创建一个单独的实例或者每次需要时都生成一个新的实例——以及它们是如何相互关联的 . 然而 , Spring不应该被混同于传统的重量级的EJB容器 , 它们经常是庞大与笨重的 , 难以使用 . 

#### **框架**

Spring可以将简单的组件配置 , 组合成为复杂的应用 . 在Spring中 , 应用对象被声明式地组合 , 典型地是在一个XML文件里 . Spring也提供了很多基础功能\(事务管理、持久化框架集成等等\) , 将应用逻辑的开发留给了你 . 

#### **MVC**

Spring的作用是整合 , 但不仅仅限于整合 , Spring框架可以被看做是一个企业解决方案级别的框架 . 客户端发送请求 , 服务器控制器\(由DispatcherServlet实现的\)完成请求的转发 , 控制器调用一个用于映射的类HandlerMapping , 该类用于将请求映射到对应的处理器来处理请求 . HandlerMapping将请求映射到对应的处理器Controller\(相当于Action\)在Spring 当中如果写一些处理器组件 , 一般实现Controller接口 , 在Controller中就可以调用一些Service或DAO来进行数据操作ModelAndView用于存放从DAO中取出的数据 , 还可以存放响应视图的一些数据 . 如果想将处理结果返回给用户 , 那么在Spring框架中还提供一个视图组件ViewResolver , 该组件根据Controller返回的标示 , 找到对应的视图 , 将响应response返回给用户 . 

所有Spring的这些特征使你能够编写更干净、更可管理、并且更易于测试的代码 . 它们也为Spring中的各种模块提供了基础支持 . 

