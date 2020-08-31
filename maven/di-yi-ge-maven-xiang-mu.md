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
    <groupId>org.test.maven</groupId>
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



