# 网页跳转与传参

```
点击回到顶部 ，内部为#什么都不会跳转，但是会回到顶部；
<a href="#">#是回到顶部</a>
```

```
<a href="https://bilibili.com">网址直接跳转</a> 
```

```
<a  :href="xxx">
```

传参数可用query字段传递特定参数

路由跳转例子：

```javascript
const router = useRouter();
const routeData=router.resolve({
    path: '/test',
    query: {
        a: 'test1',
        b: xxx.value
    }
})
window.open(routeData.href,'_blank')//新窗口打开
window.open(routeData.href,'_self')//当前窗口打开
```

```
const xxx =(route.query.xxxx? route.query.xxxx : '')
```

