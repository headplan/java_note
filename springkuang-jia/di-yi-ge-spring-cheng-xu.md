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

Hello Spring

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



