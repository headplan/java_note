# Site 生命周期

Maven Site 插件一般用来创建新的报告文档、部署站点等 . 

* pre-site : 执行一些需要在生成站点文档之前完成的工作
* site : 生成项目的站点文档
* post-site : 执行一些需要在生成站点文档之后完成的工作，并且为部署做准备
* site-deploy：将生成的站点文档部署到特定的服务器上

这里经常用到的是site阶段和site-deploy阶段 , 用以生成和发布Maven站点 , 这可是Maven相当强大的功能 , Manager比较喜欢 , 文档及统计数据自动生成很好看 . 

