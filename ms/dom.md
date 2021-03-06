### 简单介绍一下事件传播机制

- 事件传播机制只要分为三个阶段
  - 首先是`捕获阶段`，事件从最外层元素一直传播到目标元素
  - 然后是`目标阶段`，经过目标阶段，来响应事件
  - 最后是`冒泡阶段`, 从目标往外层层层触发相同的事件方法直到最外层
- 触发当前元素的某一个事件行为，不仅当前元素事件行为被触发，而且其祖先元素的相关事件行为也会依次被触发
- 可以通过`addEventListener()`方法的最后一个参数选择是在捕获阶段**true**还是冒泡阶段**false**绑定事件处理函数
- `stopPropagation()`阻止冒泡
- `preventDefault()`阻止事件的默认行为



### 什么是事件委托

- `事件委托`就是把原来需要绑定的事件委托给父元素，让父元素担当事件监听的职务，原理就是通过事件冒泡来处理的，这样做的好处有
  - 可以提高性能，减少内存占用（减少了事件的注册）
  - 举个例子：在表格table上代理所有td的click事件
  - 还可以在新增子对象的时候不用再次进行绑定
- 不适合用在**mousemove**，**mouseout**这样的会不断通过位置去计算定位的事件上，也不适合用在**focus**，**blur**这样本身没有事件冒泡机制的事件上



### `mouseover`和`mouseenter`的区别

- over属于划过事件，enter属于进入事件
- 从父元素到子元素，over离开了父元素，会触发父元素的out，而enter不算，会直接触发子元素的enter
- enter和leave阻止了事件冒泡，而over和out还存在事件冒泡
- 用enter更多于over



### 实现一下事件委托

```js

```





