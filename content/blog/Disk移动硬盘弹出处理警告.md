# Disk移动硬盘弹出处理警告

一般的解决方法
此电脑单机右键选管理：
1.计算机管理-> 系统工具 ->事件查看器 -> 自定义视图 -> 管理事件
2.在日期与事件进行排序找到最新的事件
3.合理的关掉这个程序 (直接结束进程 / 保存相关文档后关闭 Word 等程序)
另外也可以在资源监视器的磁盘 -> 磁盘活动的进程
但进程 ID 为 4 的应用程序 System就要用以下方法解决：
使用以管理员身份运行 Powershell

```bash
diskpart
list disk 找到移动硬盘的编号 X，一般是最后一个
select disk X
offline disk //disk X脱机
online disk //offline并拔出以后，下次在插入移动硬盘时，还会处于offline状态。因此需要online
```

链接来源：http://lihuaxi.xjx100.cn/news/1385006.html?action=onClick

参考其他：

1.查找ID https://blog.csdn.net/qq_21453783/article/details/126083516