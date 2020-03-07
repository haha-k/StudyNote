# flex布局

- 当父盒子设置flex布局后，子元素的`float`，`clear`，`vertical-align`都失效
- 采用flex布局的元素，称为flex容器，里面的元素是容器中的每一个item
- flex布局就是给父盒子设置flex，来控制子元素的位置和排列方式
---
#### 父项属性

- `align-content` 设置次轴上的子元素排列方式（多行）--- 需要换行

#### 子项属性

- `flex` 从剩余空间中分配几份
- `align-self`控制子项自己在次轴的排列方式

---
## flex相关文章
> [阮一峰的flex布局blog](http://www.ruanyifeng.com/blog/2015/07/flex-grammar.html)

E C F D A |B