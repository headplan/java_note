# 第一个Spring程序

* 通过Spring Initializr生成骨架
* 编写第一段代码
* 运行程序
* 分析项目结构

#### 生成骨架

[https://start.spring.io/](https://start.spring.io/)

![](/assets/start_spring.png)

导入项目 , 看一下基本的目录结构 :

这是一个典型的Maven的单模块工程

![](/assets/mulujiegou.png)

HelloSpringApplication.java是入口程序 , 带有注解 :

```java
@SpringBootApplication
```

resources文件夹下还生成了一个空的配置文件 :

```
application.properties
```

test文件夹下是对应的测试类 .

#### 运行项目

在IDE下 , Run运行项目 , 因为默认的8080的端口被占用 , 所以修改`application.properties`配置文件 :

```
server.port=8001
```

##### 运行Hello Spring

```java
@SpringBootApplication
@RestController
public class HelloSpringApplication {

    public static void main(String[] args) {
        SpringApplication.run(HelloSpringApplication.class, args);
    }

    @RequestMapping("/hello")
    public String Hello() {
        return "Hello Spring";
    }

}
```

在Terminal中简单的访问一下URL :

```
curl http://localhost:8001/hello                                                                     
Hello Spring
```

刚才我们在Dependencies中还选择了**Spring Boot Actuator** , 它还提供了一些额外的功能 , 比方说健康检查 :

```
curl http://localhost:8001/actuator/health
{"status":"UP"}
```

#### Maven的pom文件

这里Spring boot把spring-boot-starter-parent作为整个maven工程的parent引入进来 , 这里其实引入了大量的依赖 , 并保证其不冲突 .

```asciidoc
<parent>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-parent</artifactId>
    <version>2.3.0.RELEASE</version>
    <relativePath/> <!-- lookup parent from repository -->
</parent>
```

下面的依赖是没有版本号的 , 继承在parent的version中 , 只要告诉maven用了什么就可以 .

```asciidoc
<dependencies>
    <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-actuator</artifactId>
    </dependency>
    <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-web</artifactId>
    </dependency>

    <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-test</artifactId>
        <scope>test</scope>
        <exclusions>
            <exclusion>
                <groupId>org.junit.vintage</groupId>
                <artifactId>junit-vintage-engine</artifactId>
            </exclusion>
        </exclusions>
    </dependency>
</dependencies>
```

**spring-boot-maven-plugin**

是用来在执行打包的过程当中 , 为我们生成一个可执行的jar包 :

```
<build>
    <plugins>
        <plugin>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-maven-plugin</artifactId>
        </plugin>
    </plugins>
</build>
```

 执行

```
mvn clean package -Dmaven.test.skip
```

清空之前的包 , 然后打包并跳过测试 .

#### 执行jar包

```
java -jar hello-spring-0.0.1-SNAPSHOT.jar
```

执行jar包 , 然后可以像之前一样请求了 .

#### 如果工程有自己特定的parent , 不能使用spring-boot-starter-parent该怎么办 ?

简单的修改一下pom文件 , 不指定parent , 指定dependencyManagement , 在其中将Spring boot的依赖完整的import进来 , 通过这种方式 , 同样可以实现parent实现的依赖管理的功能 .这里还是会保留spring-boot-maven-plugin , 但是需要指定 , 其是在repackage时候介入进来 .

```asciidoc
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
    <modelVersion>4.0.0</modelVersion>

    <groupId>spring.test</groupId>
    <artifactId>helloworld</artifactId>
    <version>0.0.1-SNAPSHOT</version>
    <name>HelloWorld</name>
    <description>Demo project for Spring Boot</description>

    <properties>
        <java.version>1.8</java.version>
    </properties>

    <dependencyManagement>
        <dependencies>
            <dependency>
                <groupId>org.springframework.boot</groupId>
                <artifactId>spring-boot-dependencies</artifactId>
                <version>2.1.1.RELEASE</version>
                <type>pom</type>
                <scope>import</scope>
            </dependency>
        </dependencies>
    </dependencyManagement>

    <dependencies>
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-web</artifactId>
        </dependency>

        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-test</artifactId>
            <scope>test</scope>
        </dependency>
    </dependencies>

    <build>
        <plugins>
            <plugin>
                <groupId>org.springframework.boot</groupId>
                <artifactId>spring-boot-maven-plugin</artifactId>
                <version>2.1.1.RELEASE</version>
                <executions>
                    <execution>
                        <goals>
                            <goal>repackage</goal>
                        </goals>
                    </execution>
                </executions>
            </plugin>
        </plugins>
    </build>

</project>
```



