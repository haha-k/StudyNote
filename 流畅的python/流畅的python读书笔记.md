## 第一章

### Python数据模型

1. collections.namedtuple()-----用于构建只有少数属性没有方法的对象
2. 魔术方法(双下方法)
   - 一般用于python解释器调用，一般不去直接调用，而是通过内置的函数来使用
   - `__repr__`---能把一个对象用字符串的形式表现出来
     - 区别于`__str__`（`str()` 或`print()`中使用)
     - 无`__str__`时，用`__repr__`代替



## 第二章

### 内置序列

- 可分为
  - 容器序列（list，tuple，collections.deque）
    - 能存放不同类型的数据，存放的是它们所包含的任意类型对象的引用
  - 扁平序列（str，bytes，bytearray，memoryview，array.array）
    - 只能容纳一种类型，存放的是值，是一段连续的内存空间
- 按是否可修改可以分为
  - 可变序列（list，collections.deque，bytearray，memoryview，array.array）
  - 不可变序列（str，bytes，tuple）



----

####

- #### 列表推导

  - 只用列表推导来创建新的列表，并且尽量保持简短
  - 只能生成列表，生成其他类型的序列需要生成器表达式

  ---

- #### 生成器表达式
  - 遵守了迭代器协议，可以逐个产出元素
  - 语法上由方括号变为了圆括号

- #### 元组
  * 不可变的列表
  * 对数据的记录



