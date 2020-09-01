# Maven编译错误 . 不再支持源选项 5 , 请使用 7 或更高版本

在使用apache-maven-3.6.3编译时编译报错 : 

```
[ERROR] COMPILATION ERROR :
[INFO] -------------------------------------------------------------
[ERROR] 不再支持源选项 5。请使用 7 或更高版本。
[ERROR] 不再支持目标选项 5。请使用 7 或更高版本。
[INFO] 2 errors
[INFO] -------------------------------------------------------------
[INFO] ------------------------------------------------------------------------
[INFO] BUILD FAILURE
[INFO] ------------------------------------------------------------------------
[INFO] Total time:  1.685 s
[INFO] Finished at: 2020-08-31T23:56:50+08:00
[INFO] ------------------------------------------------------------------------
[ERROR] Failed to execute goal org.apache.maven.plugins:maven-compiler-plugin:3.1:compile (default-compile) on project Hello: Compilation failure: Compilation failure:
[ERROR] 不再支持源选项 5。请使用 7 或更高版本。
[ERROR] 不再支持目标选项 5。请使用 7 或更高版本。
```

#### 原因分析

本地使用的是openjdk version "11.0.7" , 并没有修改setting.xml或pom.xml , 没有使用指定参数 , 那就是maven自动使用了默认参数 . 查看Debug . 

```java
mvn -debug compile
```



