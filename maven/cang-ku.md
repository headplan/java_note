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

