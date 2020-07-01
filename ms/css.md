### 两种盒模型分别说一下

- 为什么这种比这种更好

- 两种盒模型分别是border-box和content-box

- `border-box`是指设置一个宽度，比如200px,在这200px内也包括了padding和border的值,而`content-box`则表明只有内容有200px。

  总结就是

  `border-box`：标准盒模型，css定义的宽高只包含content

  `content-box`：IE盒模型，css定义的宽高包括了content,padding,border

### 如何 垂直居中

1. flex
2. 

### 圣杯布局实现



### 双飞翼布局实现









### flex怎么用，常用属性有哪些



### BFC是什么？

BFC 块级格式化上下文

给一个div设置overflow：hidden   div里面的浮动元素就会被包裹起来



### css选择器优先级

- 越具体优先级越高 
- 写在后面的覆盖前面的
- !important  最高，少用



### 清除浮动说一下

清除浮动就是指给元素加浮动后会脱离标准文档流，使得浮动元素撑不起父元素的高度，导致父元素塌陷

- 为浮动元素后的元素添加clear属性

- 给要清除浮动的元素

  ```scss
  .clearfix:after {
  	content: '';
  	display:block;
      clean:both;
      
  }
  ```

- 给浮动元素的父元素设置高度

- 给浮动元素的父元素设置overflow:hidden






### 回流和重绘

回流就是渲染的时候将根据样式来计算dom节点的大小或位置的改变并把它放在它该出现的位置

回流就是渲染树中的一部分或者全部因为元素的尺寸，布局，隐藏等改变而需要重新构建

触发回流：（主要是dom节点大小或位置的改变才会触发）

- 调整窗口大小
- 改变字体
- 设置style属性的值
- 伪类激活

优化：

- 避免使用table布局
- 动画放在fixed和absolute的元素上
- 使用class来统一改样式

重绘就是在计算好各自的位置的时候再将其进行绘制一遍并显示出来



