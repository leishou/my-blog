# 单体微服务K8S笔记

```
https://blog.csdn.net/m0_48341969/article/details/126063832
```

思路参考以上博客

//测试
```
https://gitee.com/yangbuyi/yi
```

项目组织参考以上git

### 单体：



### 微服务：

rpc:远程过程调用

拆分，分别部署，不同端口。

https://www.mdaima.com/it/14263.html

###### MySql的多站式数据库：如何实现多个站点共用一个MySQL数据库

```
理解的核心：分配数据表 设置权限 数据备份
```

总流量限制

```
https://blog.csdn.net/qq_36154886/article/details/130251876
```

nginx介绍，流量及并发连接数限制，访问控制及ddos预防

```
https://www.dandelioncloud.cn/article/details/1460922170401701889
```

Nginx--流量限制（最有用的功能之一）

https://blog.csdn.net/liji133122/article/details/126667277

```
限制下载速度
```



#### 配置过程：

调整匹配数据库 

调整nacos配置 2.1.1

https://blog.csdn.net/u011149152/article/details/130396466

https://blog.csdn.net/weixin_43185154/article/details/123854515

参考配置过程中maven用到之前未曾用过的关键字

dependencymanagement

plugins引入相关插件

多模块开发写法比较麻烦但是相对分离互不影响

单体只需要统合 多服务便于拆分

#### 其他相关博客介绍：

https://blog.csdn.net/weixin_46703995/article/details/131820311?spm=1001.2014.3001.5502



K8S

```
https://blog.51cto.com/ITEvan/6459831
```

![企业微服务项目如何进入K8S的全过程_docker](https://s2.51cto.com/images/blog/202306/12095953_64867c19e986734836.jpg?x-oss-process=image/watermark,size_16,text_QDUxQ1RP5Y2a5a6i,color_FFFFFF,t_30,g_se,x_10,y_10,shadow_20,type_ZmFuZ3poZW5naGVpdGk=/format,webp/resize,m_fixed,w_1184)