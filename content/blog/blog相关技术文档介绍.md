# blog相关技术文档介绍

### protobuf：

https://blog.csdn.net/Gefangenes/article/details/131319610

简介
Protobuf是Protocol Buffers的简称，它是Google公司开发的一种数据描述语言，是一种轻便高效的结构化数据存储格式，可以用于结构化数据串行化，或者说序列化 。它很适合做数据存储或 RPC 数据交换格式。可用于通讯协议、数据存储等领域的语言无关、平台无关、可扩展的序列化结构数据格式。目前提供了 C++、Java、Python 三种语言的 API。

### webassembly:

WebAssembly 是基于栈式虚拟机的二进制指令集，可以作为编程语言的编译目标，能够部署在 web 客户端和服务端的应用中。

听起来有点晦涩，下面说说我个人的一些理解。

WebAssembly（Wasm）是Web中的指令集，或者说其目的是让指令集能够在Web中运行。这其中又包含两个层面：

**Assembly的来源**

Wasm作为媒介（编译目标），它可以：

- 抹平语言差异
- 抹平终端差异


https://www.jianshu.com/p/f7d98c422e0c

性能比较实例： 8.94s 13s

https://www.jianshu.com/p/e4d002780cf8

web 小程序 node /多端解决方案 rust+WebAssembly

![image-20230822112133224](C:\Users\15818\AppData\Roaming\Typora\typora-user-images\image-20230822112133224.png)

### Rust：

参考博客：https://blog.csdn.net/inthat/article/details/121491401

中文官网：https://www.rust-lang.org/zh-CN/

### MAT：

分析内存泄漏

思路：打开文档，关闭后打开小文档，dump hprof文件 用MAT工具分析大对象的引用链

mat下载链接 https://eclipse.dev/mat/downloads.php

## 网安：

钓鱼应用可能发快捷方式改成形如正常文件名的格式

0day：未发现和公开

1day：已发现未修复

nday:  已公开和修复

### Svelte:

1.减少开发时代码编写量

2.无虚拟Dom

3.反应能力

vue react ：数据发生变化 通过diff算法判断要更新哪些节点 找到要更新节点 更新真实DOM 

在Svelte在代码编译时将状态改变操作转换为对应的Dom节点操作

代码体积确实小很多

响应式原理： 位掩码 静态界面没有复杂交互场景 值得尝试