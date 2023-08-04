# 界面UI设计相关

# 0804

1.mixin的使用：提取组件共有逻辑，在所需要的组件引入

```
<xx @parentClick="(options)=>currentPageMethod(options)"/>
```

2.li svg 文本排列

```
<ul>
<li>
<svg></svg>
xxx
</li>
</ul>
```

```
vertical-align:middle;
```

3.居中相关

```
text-align:center;
justify-content:center;
margin: 0 auto;//2个参数 top bottom
```

4.margin border padding

```
margin 外边距 常用
border 边框样式
padding 内边距
var 1 上下左右
var2 上下 左右
var3 上 左右 下
var 4 上 右 下 左
```

5.fixed absolute

```
fixed:固定定位

absolute:绝对定位

 

区别很简单：

1、没有滚动条的情况下没有差异

2、在有滚动条的情况下，fixed定位不会随滚动条移动而移动，而absolute则会随滚动条移动

常用场合：

1.fixed固定定位，只针对浏览器窗口定位，上下左右，不会随着窗口大小改变，固定不变，例如固定位置的小广告，常用于网站边缘的公司联系方式和快速回到顶部

2.absolute绝对定位，脱离文档流，没有父元素，上下左右设置是针对于浏览器窗口，不占据位置，会随着窗口大小与页面一起改变

3.relative：元素仍处于文档流中，定位是相对于原本自身的位置，若没有设置宽度，则宽度为父元素的宽度，该元素的大小会影响父元素的大小。
```

z-index：xxx;//越大越高

6.隐藏不需要的内容

套盒子 overflow:hidden;

7.figma使用

1.可切换到dev模式看到更多参数

2.字体有大小也能看到行高，行高为实际占据高度

3.可以直接复制svg代码或img

4.切图可联系设计人员



query添加对应参数：

```
 return this.$route.query.hasOwnProperty('download')
```

```
 return this.$route.query.noguide==='true';
```

```
download 字段存在

noguide  条件 = true 
```

现象：正在等待可用的套接字 

```
老系统很长时间没有用，再启动后，使用Chrome浏览器访问，发现点开第一个页面时，可以访问，再点开其他页面，页面不跳转，且浏览器显示“正在等待可用的套接字”。同时浏览器无报错，后台无报错，浏览器出现连接超时，重启系统，正在等待的页面即可加载出来，并且没有规律。

网上找的原因：

浏览器对同一个域名的sockets连接数作了限制，访问的网站上使用了html5 的socket通讯特性, 浏览器对这个连接数限制为6个, 当你刷新网页过快时, 以前的socket请求未能正常返回, 占了6个中的N个, 满了6个时, 就会出现阻塞,并无限排队的情况，就出现了这个问题。
————————————————
版权声明：本文为CSDN博主「六千江山」的原创文章，遵循CC 4.0 BY-SA版权协议，转载请附上原文出处链接及本声明。
原文链接：https://blog.csdn.net/hfaflanf/article/details/102911096
```

现象：nuxt项目刷新点击两次才会重新加载

```
div 套svg 可以直接使用background-image
li 套svg 换用img
```

