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



