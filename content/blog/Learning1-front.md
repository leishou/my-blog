# Learning1-front

再学习学习项目源码:

1.使用正则表达式对文章详情页进行格式处理

2.新的弹窗可以用js单独获取节点来 remove destroy

```
function createTest(Component,props){
const vm = new Vue({
render:(h)=>h(Component,{props}),
})$mount();
doucument.body.appendChild(vm,$el);

const test =vm.$children[0];

test.remove =function(){
	document.body.removeChild(vm.$el);
	vm.$destroy();
};
	return test;
}
```

```
这个函数接受两个参数：Component是要测试的组件，props是传递给组件的属性。

函数内部创建了一个Vue实例vm，并使用render函数渲染传入的组件，并将其挂载到一个新创建的DOM元素上。然后将这个新创建的DOM元素追加到document.body中。

接下来，通过vm.$children[0]获取到渲染的组件实例，并将其赋值给test变量。然后给test对象添加了一个remove方法，用于移除挂载的DOM元素和销毁Vue实例。

最后，将test对象返回，可以通过调用test.remove()方法来移除组件。
```

3.uuid  ab测试

4.有需要资源移动至CDN

5.防抖 节流

防抖（Debounce）和节流（Throttle）是常用的前端性能优化技术，它们的应用场景如下：

防抖（Debounce）的应用场景：

1. 监听窗口大小变化，只在用户停止调整窗口大小后执行相关操作。
2. 输入框输入事件，只在用户输入停止一段时间后才触发相关操作，例如输入搜索关键字后，等待用户停止输入后再发送请求。
3. 按钮点击事件，只在用户重复点击按钮时防止触发多次操作。

节流（Throttle）的应用场景：

1. 频繁触发的事件，比如鼠标滚动事件，只在一定时间间隔内触发一次，避免频繁触发事件带来的性能问题。
2. 页面滚动事件，只在一定时间间隔内触发一次，避免滚动事件阻塞主线程。
3. 监听页面滚动位置，只在用户停止滚动一段时间后才执行相关操作。

下面是防抖和节流的示例代码：

防抖（Debounce）示例代码：

```
function debounce(func, delay) {  
  let timer;  
    
  return function(...args) {  
    clearTimeout(timer);  
    timer = setTimeout(() => {  
      func.apply(this, args);  
    }, delay);  
  };  
}  
  
// 使用防抖函数包装回调函数  
const debouncedFn = debounce(function() {  
  // 执行相关操作  
}, 300);  
  
// 监听输入框输入事件  
document.getElementById('input').addEventListener('input', debouncedFn);  
```

节流（Throttle）示例代码：

```
function throttle(func, delay) {  
  let timer;  
    
  return function(...args) {  
    if (!timer) {  
      timer = setTimeout(() => {  
        func.apply(this, args);  
        timer = null;  
      }, delay);  
    }  
  };  
}  
  
// 使用节流函数包装回调函数  
const throttledFn = throttle(function() {  
  // 执行相关操作  
}, 300);  
  
// 监听鼠标滚动事件  
window.addEventListener('scroll', throttledFn);  
```

在上述示例代码中，`debounce`函数和`throttle`函数分别用于创建防抖和节流的函数。通过使用这些函数包装回调函数，可以实现在一定时间间隔内执行一次操作，避免频繁触发事件带来的性能问题。

6.判断爬虫访问

仅能做到对ua 判断 关键字检测

7.配置化json导航 对特殊需要处理的字段 用 isSth来判断添加

8.在特定界面通过引入js接入聊天机器人

9.vue2 vue3 钩子函数生命周期

https://blog.csdn.net/DZQ1223/article/details/131433573

https://blog.csdn.net/m0_57002951/article/details/126704957

nuxt3相关博客：

https://juejin.cn/post/7266768708139401277

```
1.懒加载(知道但未使用？是否有副作用)
gpt分析如下：
在Nuxt.js 3中，使用懒加载（Lazy Loading）的确存在一些副作用。以下是一些常见的副作用：

首次加载延迟：懒加载需要在需要时才加载组件，因此首次加载时可能会有一定的延迟。这是因为只有在使用到该组件时，浏览器才会下载和解析该组件的代码。这可能会导致用户在首次加载页面时看到一个空白的区域或加载指示器。

额外的HTTP请求：懒加载组件需要通过HTTP请求加载对应的代码文件。这可能会导致额外的网络请求，增加页面的加载时间和网络传输的数据量。虽然Nuxt.js 3使用了自动分割代码（Code Splitting）的技术，但仍然会产生额外的文件请求。

动态模块加载问题：懒加载可能会导致一些动态模块（如动态导入的模块）在组件加载后才被加载。这可能会导致一些依赖于这些动态模块的逻辑不能立即执行，从而引起意料之外的问题。

SEO问题：懒加载对于搜索引擎的爬虫可能会产生不利影响。由于爬虫可能无法执行JavaScript代码，因此在首次访问页面时，爬虫可能无法获取到懒加载的组件内容，从而无法正确解析和索引页面。(致命)

需要注意的是，以上副作用在大多数情况下可能是可以接受的，并且Nuxt.js 3已经对懒加载进行了优化。懒加载可以显著减少初始加载时间和资源占用，并提供更好的用户体验。但在某些特定情况下，可能需要权衡是否使用懒加载，或者采取其他解决方案以解决副作用。
2.assets 和public目录区别
Nuxt 3 中的 ~/assets 文件夹适用于需要处理的资产。

例如，图像、样式表、图标和字体。

从该文件夹导入资产时，捆绑程序会处理文件，生成带有哈希值的新文件名，并用新文件名替换导入文件。。
如果资产丢失，就会出现构建错误，这有助于维护应用程序的完整性。而 ~/public 文件夹中的资产不会出现这种情况，因为它们不会被处理。
```

lottie 绘图

```
Lottie简介
官方介绍：Lottie是一个库，可以解析使用AE制作的动画（需要用bodymovie导出为json格式）,支持web、ios、android、flutter和react native。 在web端，lottie-web库可以解析导出的动画json文件，并将其以svg或者canvas的方式将动画绘制在我们的页面上.
————————————————
版权声明：本文为CSDN博主「球球不吃虾」的原创文章，遵循CC 4.0 BY-SA版权协议，转载请附上原文出处链接及本声明。
原文链接：https://blog.csdn.net/qq_32594913/article/details/128606420
```

sourcesrc 引入video

sitemap之于SEO 

```
https://blog.csdn.net/weixin_44869002/article/details/131246260
```

前端 slogan 字体循环移动效果：

animation 动画 关键帧

svg可以实现动画

轮播图效果：

```
原生实现 点击切换 translate3d()
&#item1 &#item2 &#item3
befoteDestroy scroll removeEventListener
mounted  addEventListener
```

瀑布图流水线效果：

```
-webkit-animation: myimg-44431bec 15s linear infinite;
```

量化数字在可视化区域计算

一个有趣的设计 滑动到特定位置隐藏导航栏 显示特定下载广告