# 初识Go

参考博客：

https://www.modb.pro/db/491215   配置

https://juejin.cn/post/6967941646138736653?searchId=20230814154001E938B48B4149D5F8C9E4  运行

配置相关网站：

https://goproxy.io/

遇到问题：

```
https://blog.csdn.net/zhan13253807836/article/details/122897168
```

go出现missing go.sum entry for module providing package 错误

解决办法：

```
go mod tidy
```

文档地址：

https://go-kratos.dev/docs/getting-started/start/

字节青训营有相关介绍

Kratos微服务 API 工程化指南

https://juejin.cn/post/7191095845096259641



在同一目录下运行多个.go文件

```
windows的cmd不支持*.go的表达方式，在ming64中可以支持，那么我如果想要windows脱离ming64支持，应该怎么实现
```

```
go run a.go b.go c.go
```

可参考学习 字节青训营 go

http://www.rply.cn/news/173011.html


参照学习 go聊天室

https://www.cnblogs.com/liwill/p/16086310.html 简单

https://github.com/liwilljinx/chatroom



https://juejin.cn/post/6870388583019872270?searchId=20230817174540A4E3A4B6FF9C13086987   较为复杂

