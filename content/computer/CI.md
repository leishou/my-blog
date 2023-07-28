# CI

### tcp

#### ack tcp:

三次握手：

```
SYN=1 握手报文
SYN=1 seq=x
客户端处于SYN-SENT
SYN=1 seq=y ACK=1 ack=x+1
服务器处于SYN-RCVD
ACK=1 确认应答
ACK=1 seq=x+1 ack=y+1
```

参考博客链接：https://blog.csdn.net/Leeeoplod/article/details/128079890

#### 报文字节

```
SYN 1000 
FIN 5001 
5001 -1001=4000

```

#### 重传：

```
tcp规定超过三个冗余ACK就立即重传
```

#### 划分子网：

```
https://blog.csdn.net/weixin_45757125/article/details/120395992
```

![img](https://img-blog.csdnimg.cn/7868a037e103476aab86b2a59a5c2307.jpg?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBAd2VpeGluXzQ1NzU3MTI1,size_20,color_FFFFFF,t_70,g_se,x_16)

```
链接：https://www.nowcoder.com/questionTerminal/ef77c11f51424788a0ba86360d29d538?orderByHotValue=1&difficulty=00111&page=1&onlyReference=false
来源：牛客网

01.200.16.0/20划分5个子网
101.200.0001 0000 .0
101.200.0001 1000 .0
101.200.0001 1100 .0
101.200.0001 1110 .0
101.200.0001 1111 .0   最小子网的可分配IP地址数 2的8次方-2 =254  选B
```

### 虚电路

```
虚电路服务需要有建立连接过程，每个分组使用短的虚电路号，属于同一条虚电路的分组按照同一路由进行转发，
分组到达终点的顺序与发送顺序相同，可以保证有序传输，不需要为每条虚电路预分配带宽。
```

#### 冲突域广播域

![img](https://img2020.cnblogs.com/blog/2530388/202112/2530388-20211207161838147-2094481576.png)



### OSI

![img](https://img-blog.csdnimg.cn/cb53a33c2a5741568a6ff79f64873a52.png?x-oss-process=image/watermark,type_ZHJvaWRzYW5zZmFsbGJhY2s,shadow_50,text_Q1NETiBA6YWS5YmR5LuZYWJj,size_20,color_FFFFFF,t_70,g_se,x_16)

| 7应用层     | 直接提供服务                 |
| ----------- | ---------------------------- |
| 6表示层     | 格式转换加密解密 数据编码    |
| 5会话层     | 会话管理 寻址 出错控制       |
| 4传输层     | 端到端差错控制和流量控制     |
| 3网络层     | 数据帧 不同子网间            |
| 2数据链路层 | 差错控制 流量控制            |
| 1物理层     | 提供物理连接，比特流透明传输 |
|             |                              |

```
应用层：产生网络流量的程序

       表示层：传输之前是否进行加密或者压缩处理

       会话层：查看会话，查木马  netstat-n

       传输层：可靠传输、流量控制、不可靠传输

       网络层：负责选择最佳路径、规划ip地址

       数据链路层：帧的开始和结束、透明传输、差错校验

       物理层：接口标准、电器标准、如何更快传输数据
 
————————————————
版权声明：本文为CSDN博主「酒剑仙abc」的原创文章，遵循CC 4.0 BY-SA版权协议，转载请附上原文出处链接及本声明。
原文链接：https://blog.csdn.net/fengxin_/article/details/121602938
```

### 滑动窗口

发送窗口+接收窗口<=2^n

### 计算

#### 最大信道利用率：

```
停等协议向主机乙发送数据帧，数据帧长与确认帧长均为1000B，数据传输速率是10kbps，单项传播延时是200ms
发送数据帧和确认帧的时间均为 t = 1000*8b/10kbps = 800ms。
发送周期 T = 800ms + 200ms + 800ms + 200ms = 2000ms。
信道利用率 = t/T = 800/2000 = 0.4 = 40%。
```

