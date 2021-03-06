# J2EE的13个规范

#### JDBC\(Java Database Connectivity\)

用于执行SQL语句的Java API , 可以为多种关系数据库提供统一访问 , 它由一组用Java语言编写的类和接口组成 .

跟微软的ODBC很像 , 应该说是ODBC和ADO的结合 , 创建连接和发送SQL只用JDBC一个就行了 , 而ODBC只是创建一个连接 , 还需要用ADO来进行数据操作 . ODBC把简单功能跟高级功能放到了一起 , 相对来说比较难学 , 而JDBC尽量保证简单功能的简便性 , 同时又可以在需要的时候使用高级功能 .

JDBC是Java应用程序与各种不同数据库之间进行对话的方法的机制 . 简单地说 , 它做了三件事 : 与数据库建立连接 - 发送操作数据库的语句 - 处理结果 .

#### JNDI\(Java Name and Directory Interface\)

JNDI是一组在Java应用中访问命名和目录服务的API . \(命名服务将名称和对象联系起来 , 我们即可用名称访问对象 . JNDI允许把名称同Java对象或资源关联起来 , 建立逻辑关联 , 而不必知道对象或资源的物理ID . \)

JNDI是为了对高级网络应用开发中使用的目录基础结构进行访问 . 这个目录其实是一个特殊的数据库 , 提供了对存储数据的快速访问 , 不象传统的目录服务访问方式那样必须提供不同的API接口去访问不同的目录服务\(如 : LDAP , NIS , ADS等\) , 它统一了不同类型目录访问的接口 . JDNI与JDBC都构建在抽象层上 .

它提供了标准的独立于命名系统的API , 这些API构建在命名系统之上 . 这一层有助于将应用与实际数据源分离 , 因此不管是访问的LDAP , RMI还是DNS . 也就是说 , JNDI独立于目录服务的具体实现 , 只要有目录的服务提供接口或驱动 , 就可以使用目录 .

#### EJB\(Enterprise JavaBean\)

在J2EE中 , 这个运行在一个独立的服务器上 , 并封装了业务逻辑的组件就是EJB组件 . 其实就是把原来放到客户端实现的代码放到服务器端 , 并依靠RMI进行通信 .

Javabean的任务是 : 一次性编写 , 任何地方执行 , 任何地方重用 . Javabean分为会话Bean\(无会话状态的Bean , 有会话状态的Bean\)、实体Bean、消息驱动Bean .

关于实体Bean , 很像三层里面的DAL+Entity . 只不过在这里 , Bean可以由容器实现 , 也可以由Bean自己实现 . 由容器实现 , 在使用过程中 , 感觉很像为某个空间设置数据源 , 只需要通过自己选择一下 , 语句就可以出来 . 而有Bean自己控制的Bean , 感觉就很像三层里面的DAL+Entiry了 .

会话Bean , 可以作为三层架构中的业务逻辑层出现 . 而消息驱动Bean , 更多的是用在了JMS\(Java massage Service\)中 .

#### RMI\(Remote Method Invoke\)

正如其名字所表示的那样 , RMI协议调用远程对象上方法 . 它使用了序列化方式在客户端和服务器端传递数据 . RMI是一种被EJB使用的更底层的协议 .

RMI是非常重要的底层技术 , 是分布式的基础所在 , 刚刚提到的EJB就是建立在RMI的基础之上的 . 相比Web Service这样重量级的组件来说 , RMI比较简单 , 更适合一些小型应用的使用 .

#### Java IDL/CORBA

Java接口定义语言/公用对象请求代理程序体系结构在JavaIDL的支持下 , 开发人员可以将Java和CORBA集成在一起 .

他们可以创建Java对象并使之可在CORBA ORB中展开 , 或者他们还可以创建Java类并作为和其它ORB一起展开的CORBA对象的客户 . 后一种方法提供了另外一种途径 , 通过它Java可以被用于将新的应用和旧的系统相集成 .

CORBA是面向对象标准的第一步 , 有了这个标准 , 软件的实现与工作环境对用户和开发者不再重要 , 可以把精力更多地放在本地系统的实现与优化上 .

#### JSP\(Java Server Pages\)

JSP页面=HTML+Java , 其根本是一个简化的Servlet设计 . 服务器在页面被客户端请求后 , 对这些Java代码进行处理 , 然后将执行结果连同原HTML代码生成的新HTML页面返回给客户端浏览器 .

#### Java Servlet

Servlet是一种服务器端的Java应用程序 , 具有独立于平台和协议的特性 , 可以生成动态的Web页面 . 它担当客户请求\(Web浏览器或其他HTTP客户程序\)与服务器响应\(HTTP服务器上的数据库或应用程序\)的中间层 .

Servlet是位于Web服务器内部的服务器端的Java应用程序 , 与传统的从命令行启动的Java应用程序不同 , Servlet由Web服务器进行加载 , 该Web服务器必须包含支持Servlet的Java虚拟机 .

Servlets提供的功能大部分JSP相同 , 它采用的是一个有点不同的方法 . JSP中大部分是HTML代码 , 其中只有少量的Java代码 , 而servlets则相反 , 它完全使用Java编写 , 并且可以产生HTML代码 . JSP并没有增加任何本质上不能用Servlet实现的功能 . 但是 , 在JSP中编写静态HTML更加方便 , 不必再用println语句来输出每一行HTML代码 . 更重要的是 , 借助内容和外观的分离 , 页面制作中不同性质的任务可以方便地分开 . Servlet跟微软的一般处理程序很像 .

#### XML\(Extensible Markup Language\)

XML是一种可以用来定义其它标记语言的语言 . 它被用来在不同的商务过程中共享数据 . XML的发展和Java是相互独立的 , 但是它和Java具有的相同目标正是平台独立性 . 通过将Java和XML的组合 , 可以得到一个完美的具有平台独立性的解决方案 .

#### JMS\(Java Message Service\)

JMS即Java消息服务\(Java Message Service\)应用程序接口是一个Java平台中关于面向消息中间件\(MOM\)的API , 用于在两个应用程序之间或分布式系统中发送消息 , 进行异步通信 . Java消息服务是一个与具体平台无关的API , 绝大多数MOM提供商都对JMS提供支持 .

点对点互发 , 消息广播 . 还可以这样设置 : 如果对方没有在线 , 那么消息会存在服务器 , 待对方上线后 , 发送给对方 . 其实这个自己新增个表 , 其实也可以实现 , 但是你不好实现的是优化 , 如果面对大数据量 , 你无法保证是否会像你使用JMS那样高效 .

#### JTA\(Java Transaction Architecture\)

Java事务API . 允许应用程序执行分布式事务处理 —— 在两个或多个网络计算机资源上访问并且更新数据 . JDBC驱动程序的JTA支持极大地增强了数据访问能力 . 事务最简单最直接的目的就是保证数据的有效性 , 数据的一致性 .

JTA事务比JDBC事务更强大 . 一个JTA事务可以有多个参与者 , 而一个JDBC事务则被限定在一个单一的数据库连接 . 

#### JTS\(Java Transaction Service\)

JTS是CORBA OTS事务监控的基本的实现 . JTS规定了事务管理器的实现方式 . 该事务管理器是在高层支持Java Transaction API \(JTA\)规范 , 并且在较底层实现OMG OTSspecification的Java映像 . JTS事务管理器为应用服务器、资源管理器、独立的应用以及通信资源管理器提供了事务服务 . 

#### JavaMail

JavaMail是用于存取邮件服务器的API , 它提供了一套邮件服务器的抽象类 . 不仅支持SMTP服务器 , 也支持IMAP服务器 . 

#### JAF\(JavaBeans Activation Framework\)

JAF是一个专用的数据处理框架 , 它用于封装数据 , 并为应用程序提供访问和操作数据的接口 . 也就是说 , JAF让Java程序知道怎么对一个数据源进行查看 , 编辑 , 打印等 . JavaMail利用JAF来处理MIME编码的邮件附件 . MIME的字节流可以被转换成Java对象 , 或者转换自Java对象 . 大多数应用都可以不需要直接使用JAF . 

![](/assets/13guifan.png)



