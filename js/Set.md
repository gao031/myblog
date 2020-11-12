# Set

new 关键字和 Set 构造函数可以创建一个空集合

可以给 Set 构造函数传入一个可迭代对象

```javascript
// 使用数组初始化集合  
const s1 = new Set(["val1", "val2", "val3"]); 
 
alert(s1.size); // 3 
 
// 使用自定义迭代器初始化集合//这段搁置 
const s2 = new Set({ 
  [Symbol.iterator]: function*() { 
    yield "val1"; 
    yield "val2"; 
    yield "val3"; 
  } 
}); 
alert(s2.size); // 3 
```

初始化之后，可以使用 add() 增加值，使用 has() 查询，通过 size 取得元素数量，以及使用 delete()和 clear() 删除元素

```javascript
const s = new Set(); 
 
const functionVal = function() {}; 
const symbolVal = Symbol(); 
const objectVal = new Object(); 
 
s.add(functionVal); 
s.add(symbolVal); 
s.add(objectVal); 
 
alert(s.has(functionVal));   // true 
alert(s.has(symbolVal));     // true 
alert(s.has(objectVal));     // true 
```









