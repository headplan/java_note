# J2EE和Spring

链接：https://www.zhihu.com/question/268742981/answer/341770209

JavaEE是一组建立在JavaSE之上的**标准** , 解决企业级开发中的一系列问题 . 请特别留意 , 它仅仅是个标准 , 是对一系列接口的约定 , 众多厂商围绕这个标准做实现 . 如JBoss , WebSphere等 . 第一个版本的JavaEE 1.2在1999年被发布 , 到2017年的JavaEE 8 , 已经经历了将近20年 . 

那么JavaEE都有哪些标准 , 解决了什么问题呢 ? 我这里简单列举一下主要的标准 : 

* Servlet - 定义了如何处理Web请求 , 这个相信大家最熟悉
* Java Server Faces - 定义了如何使编写Web界面
* JAX-RS - 定义了如何编写RESTFul的接口
* EJB - 定义了如何编写"企业Bean"
* JPA - 定义了如何编写ORM和数据存取
* JTA - 定义了如何编写事务相关的代码
* JMS - 定义了如何编写消息队列程序
* CDI - 定义了如何编写依赖注入
* JAX - 定义了如何编写XML程序
* JAX-WS - 定义了如何编写基于XML的网络服务 , 即SOAP
* ……

看到这些 , 你可能机会发现 , 你平时其实经常使用其中一些标准接口 , 即便你认为你在用Spring . 

什么是Spring呢 ? Spring最早可以追溯到2002～2004年 . 在那几年作者Rod Johnson出版了两本书 : "Expert One-on-One J2EE Design and Development"和"Expert One-on-One J2EE Development without EJB" , 和最初几个版本的Springframework . 

早期的Spring定位于解决J2EE在实际使用上的一系列问题 , 因为JavaEE的API实在是太难用了 . Rod估计是趟了不少大坑 , 于是总结了一套最佳实践 , 并总结到了一套框架里 . 其中最重要的 , 就是所谓IoC\(控制反转\) . 

经过多年发展 , Spring发布了很多组件 : 

* spring-core : Spring的Bean的管理 , 控制反转和程序上下文
* spring-mvc : web开发中的model-view-controller
* spring-data : 数据层访问和封装
* spring-boot : spring全家桶自助配置和部署管理工具
* spring-batch : 一个简单的批处理框架
* spring-cloud : 支持与许多云服务接口的整合
* spring-security : 认证和权限管理
* ……

spring中其实大量使用或者实现了JavaEE标准 . 比如spring-mvc是在servlet基础之上的封装 . spring本身并不提供容器 , 而是支持使用任何支持servlet标准的容器\(如tomcat , jetty等\) . spring-data也实现了JPA , 通过标准接口对进行CRUD等 . 

归根到底Spring只是想**更好的解决实际问题 . **JavaEE的实现做得好的就用 , 做得不好的用比较恰当的方式独立实现或者封装 . 俗称"接地气" . 

见过不少人喜欢用"JavaEE vs Spring"来提问引战 . 但是 , 由上面的介绍可以看到JavaEE和Spring并不对立 . 作为开发工程师 , 其实还是哪个能解决问题 , 生态好 , 支持好 , 成本低就用哪个 . 而且混着用也没有什么大的问题 . 

随着时间的发展 , JavaEE已经越来越落后 , 这是由于它的体制造成的 . JavaEE的制定是由几大巨头定期开会协商通过 , 发布 . 然后个大容器实现厂商跟进 . 但这样太慢了 . 互联网的发展速度已经远不是这样一个僵化的体制能够适应的 . 反观Spring相对就快速的多 . Spring自己就是一家公司 , 觉得整个社区什么东西最前沿 , 最急缺就立刻响应去做了 . 比如 , Restful刚流行 , 你是愿意等一年半载出JAX-RS标准 , 然后再出Jersey , 才能用 ; 还是选择直接用Spring MVC直接就把事办了 ? 结果不言而喻 . 对解决问题的态度是二者目前境遇不同的主要原因 . 

最早期JavaEE是领导者 , 所有的技术厂商要想在这个圈子里混 , 必须跟着标准走 . 而Spring逐渐占据领导地位之后 , JavaEE的一些标准反而要跟着Spring走 . CDI就是一个很好的例子 . Spring IoC是整个框架的核心 . 它解决了在Java中只能import类 , 却import不了组件的问题 . 这个问题在js , python之类的环境中都是小菜一碟 . 但是Java中 , 如果没有IoC , 程序员就要花大量的时间写new和set , 组装整个服务的引用关系\(你不觉得这很不人道吗 ? \) . Spring流行之后 , JavaEE在2009年才发布CDI标准 . 其样子就是活脱脱的把Spring的Annotation换了个名字而已 . 

如果说未来的发展 , 我认为JavaEE早已经没有了未来 . JavaEE里那些做得很好的 , 或者和其他框架能够很容易相融的标准继续存在 ; 那些被骂成翔的 , 比如JSF ; 或者一开始就没有市场的 , 比如CDI , 会成为Wiki上的一段段文字记录 . 但Spring也不一定好过 . 在Java体系内他也要面临play , vert.x的冲击 ; 在体系外 , 它会受到其他语言环境的巨大压力 , 如nodejs , python和go . 说Spring灵活是相对于JavaEE而言 . 

无论标准、框架、服务，都是为了解决问题而存在 , 而不是如"多么的OO" , "多么的标准" , "多么的概念清晰" . 哪个工具解决的好 , 解决的快 , 就用哪个 . 最近2-3年 , docker+微服务的发展进一步的强化了这个现实 . 大量的新技术会随着业务领域形成自己的生态 . 

