# 构建生命周期

Maven 构建生命周期定义了一个项目构建跟发布的过程 .

一个典型的Maven构建\(build\)生命周期是由以下几个阶段的序列组成的 :

![](/assets/mavengoujian.png)

| 阶段 | 处理 | 描述 |
| :--- | :--- | :--- |
| 验证 validate | 验证项目 | 验证项目是否正确且所有必须信息是可用的 |
| 编译 compile | 执行编译 | 源代码编译在此阶段完成 |
| 测试 Test | 测试 | 使用适当的单元测试框架\(例如JUnit\)运行测试 |
| 包装 package | 打包 | 创建JAR/WAR包如在 pom.xml 中定义提及的包 |
| 检查 verify | 检查 | 对集成测试的结果进行检查 , 以保证质量达标 |
| 安装 install | 安装 | 安装打包的项目到本地仓库 , 以供其他项目使用 |
| 部署 deploy | 部署 | 拷贝最终的工程包到远程仓库中 , 以共享给其他开发人员和工程 |

为了完成 default 生命周期 , 这些阶段\(包括其他未在上面罗列的生命周期阶段\)将被按顺序地执行 .

#### Maven 有以下三个标准的生命周期

* **clean : **项目清理的处理
* **default\(或 build\) : **项目部署的处理
* **site : **项目站点文档创建的处理

#### 构建阶段由插件目标构成

一个插件目标代表一个特定的任务\(比构建阶段更为精细\) , 这有助于项目的构建和管理 . 这些目标可能被绑定到多个阶段或者无绑定 . 不绑定到任何构建阶段的目标可以在构建生命周期之外通过直接调用执行 . 这些目标的执行顺序取决于调用目标和构建阶段的顺序 . 

例如 , 考虑下面的命令 : 

clean 和 pakage 是构建阶段 , dependency:copy-dependencies 是目标 . 

```
mvn clean dependency:copy-dependencies package
```

这里的 clean 阶段将会被首先执行 , 然后 dependency:copy-dependencies 目标会被执行 , 最终 package 阶段被执行 . 


