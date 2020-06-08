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

下面的依赖是没有版本号的

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



