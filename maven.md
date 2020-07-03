# Maven

Maven 翻译为"专家"、"内行" , 是 Apache 下的一个纯 Java 开发的开源项目 . 基于项目对象模型\(缩写 : POM\)概念 , Maven利用一个中央信息片断能管理一个项目的构建、报告和文档等步骤 . 

Maven 是一个项目管理工具 , 可以对 Java 项目进行构建、依赖管理 . 它包含了一个项目对象模型\(Project Object Model\) , 反映在配置中 , 就是一个 pom.xml 文件 . 是一组标准集合 , 一个项目的生命周期、一个依赖管理系统 , 另外还包括定义在项目生命周期阶段的插件\(plugin\)以及目标\(goal\) . 

当我们使用 Maven 的使用 , 通过一个自定义的项目对象模型 , pom.xml 来详细描述我们自己的项目 . 

Maven 中的有两大核心 : 

* 依赖管理 : 对 jar 的统一管理\(Maven 提供了一个 Maven 的中央仓库 , https://mvnrepository.com/ , 当我们在项目中添加完依赖之后 , Maven 会自动去中央仓库下载相关的依赖 , 并且解决依赖的依赖问题\)
* 项目构建 : 对项目进行编译、测试、打包、部署、上传到私服等

## Maven 功能

Maven 能够帮助开发者完成以下工作：

* 构建
* 文档生成
* 报告
* 依赖
* SCMs
* 发布
* 分发
* 邮件列表

## 约定配置

Maven 提倡使用一个共同的标准目录结构 , Maven 使用约定优于配置的原则 :

| 目录 | 说明 |
| :--- | :--- |
| ${basedir} | 存放pom.xml和所有的子目录 |
| ${basedir}/src/main/java | 项目的java源代码 |
| ${basedir}/src/main/resources | 项目的资源，比如说property文件，springmvc.xml |
| ${basedir}/src/test/java | 项目的测试类，比如说Junit代码 |
| ${basedir}/src/test/resources | 测试用的资源 |
| ${basedir}/src/main/webapp/WEB-INF | web应用文件目录，web项目的信息，比如存放web.xml、本地图片、jsp视图页面 |
| ${basedir}/target | 打包输出目录 |
| ${basedir}/target/classes | 编译输出目录 |
| ${basedir}/target/test-classes | 测试编译输出目录 |
| Test.java | Maven只会自动运行符合该命名规则的测试类 |
| ~/.m2/repository | Maven默认的本地仓库目录位置 |



