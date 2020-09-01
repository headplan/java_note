# 第一个Maven项目

### 创建约定的目录结构

```
Hello/
    src/
        main/
            java/
            resources/
        test/
            java/
            resources/
    pom.xml
```

main目录用于存放主程序 .

test目录用于存放测试程序 .

java目录用于存放源代码文件 .

resources目录用于存放配置文件和资源文件 .

#### 创建Maven的核心配置文件pom.xml

```XML
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 https://maven.apache.org/xsd/maven-4.0.0.xsd">
    <modelVersion>4.0.0</modelVersion>
    <groupId>org.lartisan.maven</groupId>
    <artifactId>Hello</artifactId>
    <version>0.0.1-SNAPSHOT</version>
    <name>Hello</name>
    <dependencies>
        <dependency>
            <groupId>junit</groupId>
            <artifactId>junit</artifactId>
            <version>4.9</version>
            <scope>test</scope>
        </dependency>
    </dependencies>
</project>
```

#### 编写主代码

在`./src/main/java/org/lartisan/maven`目录下新建文件Hello.java

```java
package org.lartisan.maven;

public class Hello {
    public String sayHello(String name) {
        return "Hello " + name + "!";
    }
}
```

#### 编写测试代码

在`./src/test/java/org/lartisan/maven`目录下新建测试文件HelloTest.java

```java
package org.lartisan.maven;

import org.junit.Test;

import jdk.nashorn.internal.AssertsEnabled;

import static junit.framework.Assert.*;

public class HelloTest {
    @Test
    public void testSayHello() {
        Hello hello = new Hello();

        String result = hello.sayHello("小明");

        assertEquals("Hello 小明!", result); // 断言
    }
}
```

#### 运行几个基本的Maven命令

运行Maven命令时 , 一定要进入pom.xml文件所在的目录 . 

```
mvn compile 编译
mvn clean
mvn clean compile
```





