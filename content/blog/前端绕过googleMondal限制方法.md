# 前端绕过弹窗限制方法

核心：浏览器限制js跳转链接，对a标签不限制，加a标签 绝对定位到整个按钮即可 nuxt可使用nuxtlink

举例：

```
<div :class="['xxx',yy,zz]" :style=""@click="aa"><NuxtLink class="guide-link" :to="routeData.href"></NuxtLink><div class="icon" /><div class="text">    <strong>{{bb||'cc'}}</strong>    </div> </div>
```

js写法失败例子

参考url: http://www.5ityx.com/cate100/76565.html

```
<html>
  <button onclick="test()"></button>
</html>
<script>
      function test()
      {
          //3
setTimeout(window.open('http://www.baidu.com'),500);
          //4
          let tempwindow=window.open('_blank'); //打开一个窗口，然后用

          tempwindow.location='http://www.baidu.com' //使这个窗口跳转到百度，这样就会呈现弹出百度窗口的效果了。
      }
</script>

```

未解决问题：

```
按钮选中按下持续一段时间松开，窗口仍然会被拦截，快速点击则能成功跳转到新网站。
```

