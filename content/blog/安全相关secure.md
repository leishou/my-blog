# 安全相关secure

获取ssh私钥
https://zhuanlan.zhihu.com/p/37390404

套域名cloudflare 
免费防ddos测试
默认
dns13.hichina.com / dns14.hichina.com
修改为特定

参照博客
https://www.pengqi.club/2713.html 
缓存配置 打开SSL/TLS建议程序 

https://blog.csdn.net/feiying0canglang/article/details/127698008
防火墙规则 较为全面

https://zhuanlan.zhihu.com/p/636629112
nginx配置SSL/TLS证书，并强制https方式访问

### 加密解密

客户端前端 服务端

请求响应体 校验文段 和校验结果

AES256+CBC(指定长度16的IV)

流程： 

```
AES加密 对结果base64编码 请求
得到响应结果 base64解码 AES 解密
```

