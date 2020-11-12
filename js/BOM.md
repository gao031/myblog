# BOM

## 定时器

但允许使用定时器指定在某个时间之后或每隔一段时间就执行相应的代码。

### setInterval



用于指定每隔一段时间执行某些代码。 

###  setTimeout()

用于指定在一定时间后执行某些代码

```javascript
// 设置超时任务 
let timeoutId = setTimeout(() => alert("Hello world!"), 1000); 
// 取消超时任务 
clearTimeout(timeoutId); 
```

