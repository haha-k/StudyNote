### js(es6)
1. let和var,const的区别
   - let只在let所在的代码块有效（适合用在循环变量上）,出现在当前作用域的顶层
   - 不存在变量提升()
   - let声明变量时,变量需要在声明后使用,不然会ReferenceError
   - 暂时性死区的本质就是，只要一进入当前作用域，所要使用的变量就已经存在了，但是不可获取，只有等到声明变量的那一行代码出现，才可以获取和使用该变量。
   - let不允许在相同作用域内，重复声明同一个变量。

   - const
   - const的作用域与let命令相同:只在声明所在的块级作用域内有效。同样不可重复，需要声明后使用

2. this问题


3. 模块化
   - 导入默认，不需要加大括号，导入命名的需要