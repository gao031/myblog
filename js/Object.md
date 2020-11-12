# Object

### 以{}包括起来的内容



显式地创建 Object 的实例有两种方式。第一种是使用 new 操作符和 Object 构造函数，另一种方式是使用对象字面量（object literal）表示法。

```javascript
let person = new Object(); 
person.name = "Nicholas"; 
person.age = 29; //第一种

let person = {  
  name: "Nicholas", 
  age: 29 
}; //第二种

```

#### 表达式上下文

指的是期待返回值的上下文 ''{''出现在赋值号右边

#### 语句上下文

比如 if 语句的条件后面，"{"则表示一个语句块的开始。 

 

PS: 

1. 在使用对象字面量表示法定义对象时，并不会实际调用 Object 构造函数。 
2. 在对象中数值属性会自动转换为字符串。

#### defineProperty()

描述符对象上的属性可以包含： configurable 、 enumerable 、 writable 和 value ，

```javascript
let person = {};  
Object.defineProperty(person, "name", { 
  writable: false, //此对象值只读 不可改
  value: "Nicholas" 
}); 
console.log(person.name); // "Nicholas" 
person.name = "Greg"; 
console.log(person.name); // "Nicholas" 
```

writable一旦为false,非严格模式下对这个属性调用 delete 没有效果，严格模式下会抛出错误。再次调用 Object.defineProperty() 并修改任何非 writable 属性会导致错误

#### assign() 

接收一个目标对象和一个或多个源对象作为参数，然后将每个源对象中可枚举（ Object.propertyIsEnumerable() 返回 true ）
和自有（ Object.hasOwnProperty() 返回 true ）属性复制到目标对象

Object.assign() 实际上对每个源对象执行的是浅复制。如果多个源对象都有相同的属性，则使用最后一个复制的值。

```javascript
let dest, src, result; 
 
/**  
 * 覆盖属性 
 */ 
dest = { id: 'dest' }; 
 
result = Object.assign(dest, { id: 'src1', a: 'foo' }, { id: 'src2', b: 'bar' }); 
 
// Object.assign 会覆盖重复的属性 取最后一个属性
console.log(result); // { id: src2, a: foo, b: bar } 
```

#### Object.is() 

ECMAScript  6 新增的判断相等方法

```javascript
console.log(Object.is(true, 1));  // false 
console.log(Object.is({}, {}));   // false 
console.log(Object.is("2", 2));   // false 
 
// 正确的 0、-0、+0 相等/不等判定 
console.log(Object.is(+0, -0));   // false 
console.log(Object.is(+0, 0));    // true 
console.log(Object.is(-0, 0));    // false 
 
// 正确的 NaN 相等判定 
console.log(Object.is(NaN, NaN)); // true cool!
```



