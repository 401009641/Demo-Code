# Code
本项目引荐学习 文章来源 https://mp.weixin.qq.com/s/UXw1nzopLLbzFy32n3Aknw
一、API的安全

作为一个Dotnet Core的老司机，写API时，能兼顾到API的安全，这是一种优雅。

 

通常，我们会用认证来保证API的安全，无敌的Authorize能解决我们很多的问题。

但是，总有一些场合，我们没办法用Authorize，而只能用匿名或不加验证的方式来访问。比方电商中查询SKU的列表并在前端展示，通常这个无关用户和权限，在完成API的时候，我们也不会加入认证Authorize。

这种情况下，如果直接写，不加入安全级别，这样的体系结构是有可能成为可供利用的安全漏洞的。

 

Dotnet Core框架已经提供了一些常见漏洞的解决方法，包括：

跨站点脚本
SQL注入
跨站点请求伪造（CSRF）
重定向
等等。

但是，我们还需要更进一步，还需要照顾到以下常见的攻击：

拒绝服务（DOS）
分布式拒绝服务（DDOS）
批量API调用
探测响应
数据抓取
这部分内容，需要我们自己实现。当然，这部分内容的实现，也可以从Web Server上进行设置。

本文讨论的，是代码的实现。
