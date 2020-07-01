### bind  call  apply分别是什么，用于什么地方

- `bind()`创建一个新函数，新函数的this被指定为bind的第一个参数，其余参数作为新函数的参数
- `apply()`和`call()`都是用来通过给定this值得形式来调用函数
- `apply`和`call`区别就是call接受参数列表，而apply接受参数数组



### 闭包是什么

- 闭包是一个有权访问其它函数作用域里面得变量的函数
- 作用：延伸了变量的作用范围，就可以在其它作用域里面访问函数内的局部变量





### ajax

- readystate



### 跨域



### 立即执行函数



### 跨窗口通信



### 防抖（debounce）

- 防抖就是当持续触发某事件时，在一定的事件间隔内没有再次触发事件，事件处理函数才会执行一次

- ```ts
  //防抖函数
  //如果没有执行多少时间后就会执行一次
  export const debounce = (fn: Function, wait: number) => {
    let timeout: any = null;
    return () => {
      if (timeout !== null) {
      clearTimeout(timeout);
      }
      timeout = setTimeout(fn, wait);
    };
  };
  ```
  
- 



### 节流（throttle）

- 指的是当持续触发某事件时，有规律的每隔一个事件间隔执行一次事件处理函数

```ts
//节流函数
//每隔一段时间就执行一次
export const throttle = (fn: Function, delay: number) => {
  let prev = Date.now();
  return () => {
    let now = Date.now();
    if (now - prev > delay) {
      fn();
      prev = now;
    }
  };
};
```





### 浅拷贝数组

- 



### for of 和for in有什么区别





### 垃圾回收





### js数据类型有哪些

最新的 ECMAScript 标准定义了 8 种数据类型:

- 7 种基本类型
  - [Boolean](https://developer.mozilla.org/zh-CN/docs/Glossary/Boolean)
  - [Null](https://developer.mozilla.org/zh-CN/docs/Glossary/Null)
  - [Undefined](https://developer.mozilla.org/zh-CN/docs/Glossary/undefined)
  - [Number](https://developer.mozilla.org/zh-CN/docs/Glossary/Number)
  - [BigInt](https://developer.mozilla.org/zh-CN/docs/Glossary/BigInt)
  - [String](https://developer.mozilla.org/zh-CN/docs/Glossary/字符串)
  - [Symbol](https://developer.mozilla.org/zh-CN/docs/Glossary/Symbol) 
- 和一个引用类型 [Object](https://developer.mozilla.org/zh-CN/docs/Glossary/Object)



### let和var,const的区别

- let只在let所在的代码块有效（相当于只在当前花括号内有用）（适合用在循环变量上）-------- 而var出现在当前作用域的顶层
- let有暂时性死区，导致在声明前无法用，有变量提升会变量提升
- let声明变量时,变量需要在声明后使用,不然会ReferenceError
- 暂时性死区的本质就是，只要一进入当前作用域，所要使用的变量就已经存在了，但是不可获取，只有等到声明变量的那一行代码出现，才可以获取和使用该变量。let有暂时性死区
- let不允许在相同作用域内，重复声明同一个变量。
- let 在循环中每次遍历都有一个新的值
  - const
  - const的作用域与let命令相同:只在声明所在的块级作用域内有效。同样不可重复，需要声明后使用
- let 的「创建」过程被提升了，但是初始化没有提升。
- var 的「创建」和「初始化」都被提升了。
- function 的「创建」「初始化」和「赋值」都被提升了。
- const实际上保证的是变量指向的那个内存地址所保存的数据不得改动。



### typeof null == object

- 这是因为在设计第一版的js的时候，设计了一个标志位，如果二进制前3位都为0的话，系统会 认为是object，而null存储的二进制就是000，所以会判定null为object类型



- instanceof 测试一个对象在其原型链上是否存在一个构造函数的prototype属性



### 构造函数继承

```js
function Parent(name){
    this.name = name;
    this.hobby = [];
    this.speak = function(){
        console.log("parent speak");
    }
}
Parent.proyotype.say = function(){
    console.log("parent say");
}
function Child(name,type){
    Parent.call(this,name);
    this.type = type;
}
```





### 原型继承

```js
function Parent(name){
    this.name = name;
    this.hobby = [];
}
Parent.prototype.say = function(){
    console.log("Parent say");
}
function Child(type){
    this.type = type;
}
Child.proptotype = new Parent();
```



### 组合继承

```js
function Parent(name){
    this.name = name;
    this.hobby = [];
}
Parent.prototype.say = function(){
    console.log("Parent say");
}
function Child(name,type){
    Parent.call(this,name);
    this.type = type;
}
Child.prototype = Object.create(Parent.prototype);
Child.prototype.speak = function(){
    console.log("Child speak");
}
Child.prototype.constructor = Child;
```



### eventloop





### 原型链及原型

- 每个函数都有原型，都有prototype属性
- 每个对象都有`__proto__`属性，它指向了创建它的构造函数的prototype
  - `instance.__proto__ = instance.constructor.prototype`



### new

```

```



#### 网站优化

1. 懒加载



### for循环说一下

- forEach：对于每个item来说，都是在另一个地方复制创建的新元素，和原数组无关，不能break和return
- for-in：遍历的是对象的属性，会遍历原型链上的属性，遍历顺序随机
- for-of：遍历数组最好的方法，但是不支持普通对象
- 当 forEach 接受的函数是 async 没法 await 的，也就是说每次执行的 async 函数之间是并发的，而 for 循环可以使用 await 让每次执行的 async 函数之间是同步的



### Object.defineProperty()

- configurable 为true才能改变
- enumerable 为true才能被枚举，定义了是否可以在for...in...循环和Object.keys()中被枚举
- 数据描述符
  - value 属性对应的值
    - writable 可写，为true才能被赋值运算符改变
- 存取描述符
  - get 属性的getter函数
  - set 属性的setter函数

