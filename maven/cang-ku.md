# 仓库

在 Maven 的术语中 , 仓库是一个位置\(place\) .

Maven 仓库是项目中依赖的第三方库 , 这个库所在的位置叫做仓库 .

在Maven中 , 任何一个依赖、插件或者项目构建的输出 , 都可以称之为构件 .

Maven仓库能帮助我们管理构件\(主要是JAR\) , 它就是放置所有JAR文件\(WAR , ZIP , POM等等\)的地方 .

Maven仓库有三种类型 :

* 本地\(local\)
* 中央\(central\)
* 远程\(remote\)

#### 本地仓库

Maven的本地仓库 , 在安装 Maven 后并不会创建 , 它是在第一次执行 maven 命令的时候才被创建 .

运行 Maven 的时候 , Maven 所需要的任何构件都是直接从本地仓库获取的 . 如果本地仓库没有 , 它会首先尝试从远程仓库下载构件至本地仓库 , 然后再使用本地仓库的构件 .

默认情况下 , 不管Linux还是 Windows , 每个用户在自己的用户目录下都有一个路径名为 .m2/respository/ 的仓库目录 .

Maven 本地仓库默认被创建在 %USER\_HOME% 目录下 . 要修改默认位置 . 在 %M2\_HOME%\conf 目录中的 Maven 的 settings.xml 文件中定义另一个路径 .

```XML
<settings xmlns="http://maven.apache.org/SETTINGS/1.0.0"
   xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
   xsi:schemaLocation="http://maven.apache.org/SETTINGS/1.0.0 
   http://maven.apache.org/xsd/settings-1.0.0.xsd">
      <localRepository>C:/MyLocalRepository</localRepository>
</settings>
```

当你运行 Maven 命令 , Maven 将下载依赖的文件到你指定的路径中 . 

#### 中央仓库

Maven 中央仓库是由 Maven 社区提供的仓库 , 其中包含了大量常用的库 . 

中央仓库包含了绝大多数流行的开源Java构件 , 以及源码、作者信息、SCM、信息、许可证信息等 . 一般来说 , 简单的Java项目依赖的构件都可以在这里下载到 . 

中央仓库的关键概念 : 

* 这个仓库由 Maven 社区管理
* 不需要配置
* 需要通过网络才能访问

要浏览中央仓库的内容 , maven 社区提供了一个 URL : [http://search.maven.org/\#browse](http://search.maven.org/#browse) . 使用这个仓库 , 开发人员可以搜索所有可以获取的代码库 . 



