# Clean 生命周期

当我们执行 mvn post-clean 命令时 , Maven 调用 clean 生命周期 , 它包含以下阶段 :

* pre-clean : 执行一些需要在clean之前完成的工作
* clean : 移除所有上一次构建生成的文件
* post-clean : 执行一些需要在clean之后立刻完成的工作

mvn clean 中的 clean 就是上面的 clean , 在一个生命周期中 , 运行某个阶段的时候 , 它之前的所有阶段都会被运行 , 也就是说 , 如果执行 mvn clean 将运行以下两个生命周期阶段 :

```
pre-clean, clean
```

如果我们运行 mvn post-clean , 则运行以下三个生命周期阶段 :

```
pre-clean, clean, post-clean
```

可以通过在上面的 clean 生命周期的任何阶段定义目标来修改这部分的操作行为 . 

在下面的例子中 , 将 maven-antrun-plugin:run 目标添加到 pre-clean、clean 和 post-clean 阶段中 . 这样就可以在 clean 生命周期的各个阶段显示文本信息 . 

```XML
<project xmlns="http://maven.apache.org/POM/4.0.0"
   xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
   xsi:schemaLocation="http://maven.apache.org/POM/4.0.0
   http://maven.apache.org/xsd/maven-4.0.0.xsd">
<modelVersion>4.0.0</modelVersion>
<groupId>com.companyname.projectgroup</groupId>
<artifactId>project</artifactId>
<version>1.0</version>
<build>
<plugins>
   <plugin>
   <groupId>org.apache.maven.plugins</groupId>
   <artifactId>maven-antrun-plugin</artifactId>
   <version>1.1</version>
   <executions>
      <execution>
         <id>id.pre-clean</id>
         <phase>pre-clean</phase>
         <goals>
            <goal>run</goal>
         </goals>
         <configuration>
            <tasks>
               <echo>pre-clean phase</echo>
            </tasks>
         </configuration>
      </execution>
      <execution>
         <id>id.clean</id>
         <phase>clean</phase>
         <goals>
          <goal>run</goal>
         </goals>
         <configuration>
            <tasks>
               <echo>clean phase</echo>
            </tasks>
         </configuration>
      </execution>
      <execution>
         <id>id.post-clean</id>
         <phase>post-clean</phase>
         <goals>
            <goal>run</goal>
         </goals>
         <configuration>
            <tasks>
               <echo>post-clean phase</echo>
            </tasks>
         </configuration>
      </execution>
   </executions>
   </plugin>
</plugins>
</build>
</project>
```

现在执行下面的Maven命令 : 

```
mvn post-clean
```

Maven 将会开始处理并显示 clean 生命周期的所有阶段 : 

```
[INFO] Scanning for projects...
[INFO] ------------------------------------------------------------------
[INFO] Building Unnamed - com.companyname.projectgroup:project:jar:1.0
[INFO]    task-segment: [post-clean]
[INFO] ------------------------------------------------------------------
[INFO] [antrun:run {execution: id.pre-clean}]
[INFO] Executing tasks
     [echo] pre-clean phase
[INFO] Executed tasks
[INFO] [clean:clean {execution: default-clean}]
[INFO] [antrun:run {execution: id.clean}]
[INFO] Executing tasks
     [echo] clean phase
[INFO] Executed tasks
[INFO] [antrun:run {execution: id.post-clean}]
[INFO] Executing tasks
     [echo] post-clean phase
[INFO] Executed tasks
[INFO] ------------------------------------------------------------------
[INFO] BUILD SUCCESSFUL
[INFO] ------------------------------------------------------------------
[INFO] Total time: < 1 second
[INFO] Finished at: Sat Jul 07 13:38:59 IST 2020
[INFO] Final Memory: 4M/44M
[INFO] ------------------------------------------------------------------
```



