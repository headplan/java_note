# 环境配置

Maven 是一个基于 Java 的工具 , 所以要做的第一件事情就是安装 JDK .

下载地址 : [http://maven.apache.org/download.cgi](http://maven.apache.org/download.cgi)

#### JDK

* Maven 3.3 要求 JDK 1.7 或以上
* Maven 3.2 要求 JDK 1.6 或以上
* Maven 3.0/3.1 要求 JDK 1.5 或以上

#### 设置Maven环境变量

```
# wget http://mirrors.hust.edu.cn/apache/maven/maven-3/3.6.3/binaries/apache-maven-3.6.3-bin.tar.gz
# tar -xvf  apache-maven-3.6.3-bin.tar.gz
# sudo mv -f apache-maven-3.6.3 /usr/local/
```

编辑**/etc/profile**文件

```bash
export MAVEN_HOME=/usr/local/apache-maven-3.6.3
export PATH=${PATH}:${MAVEN_HOME}/bin
```

保存文件 , 并运行如下命令使环境变量生效

```
# source /etc/profile
```

```
mvn -v
```

#### 配置本地仓库

Maven默认的本地仓库目录

```XML
~/.m2/repository/
```

Maven的核心程序并不包含具体功能 , 仅负责宏观调度 . 具体功能由插件来完成 . Maven核心程序会到本地仓库中查找插件 . 如果本地仓库中没有就会从远程中央仓库下载 . 此时如果不能上网则无法执行Maven的具体功能 . 可以将Maven的本地仓库指向一个在联网情况下下载好的目录 . 

Maven的核心配置文件位置 : 

```
~/maven/conf/settings.xml
```



