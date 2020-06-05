# 环境配置

Maven 是一个基于 Java 的工具 , 所以要做的第一件事情就是安装 JDK .

#### JDK

* Maven 3.3 要求 JDK 1.7 或以上
* Maven 3.2 要求 JDK 1.6 或以上
* Maven 3.0/3.1 要求 JDK 1.5 或以上

#### 设置Maven环境变量

```
# wget http://mirrors.hust.edu.cn/apache/maven/maven-3/3.3.9/binaries/apache-maven-3.3.9-bin.tar.gz
# tar -xvf  apache-maven-3.3.9-bin.tar.gz
# sudo mv -f apache-maven-3.3.9 /usr/local/
```

编辑**/etc/profile**文件

```bash
export MAVEN_HOME=/usr/local/apache-maven-3.3.9
export PATH=${PATH}:${MAVEN_HOME}/bin
```

保存文件 , 并运行如下命令使环境变量生效

```
# source /etc/profile
```



