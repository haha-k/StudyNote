## js要点

1. var

   ```JS
   var x="aaa";
   x="aaa";
   //不用var声明的变量是隐式全局变量，尽量所有变量都用var来声明
   ```

2. const

   ```JS
   const FOO="ss";
   FOO="sss";
   //再赋值不变
   ```

3. 函数(是一个对象)

   ```JS
   function f(a,b,c)
   {
       //函数体
   }
   function s(a,b,c)
   {
       //返回值是Function对象的引用
   }
   var s=function(a,b){
       return Number(a)+Number(b);
   }
   s(1,2);
   s1=s;
   s1(1,2);
   //函数是一个对象
   function a(num,num2){
       arguments[1]=10;
       //num2=10    不同内存空间 但值会同步
   }
   //arguments-----包含传入函数的所有参数
   //arguments.callee---指向拥有这个arguments对象的函数的指针(解耦和)
   //this-----引用的是函数据以执行的环境对象
   //caller---保存着调用当前函数的函数的引用
   //arg6uments.callee.caller
   
   //函数的属性
   //length----表示函数希望接受的命名参数的个数
   //prototype---
   
   //函数得方法(在特定的作用域中调用函数)
   //apply(this,arguments/[])---参数数组
   //call(this，a,b)---参数直接传递给函数
   
   ```

4. 对象

   ```js
   //是一个属性(名值对)的集合
   //1.对象的属性值可以用函数来指定
   //2.具备原型链的构造
   //{(标识符，字符串值，数值):(任何值和对象)}
   var obj={x:2,y:"hah",pos:{x:1,y:2}};
   obj.pos.z=1;
   var n="x";
   //obj["x"]==obj[n]
   var obj=new Object();
   
   
   
   ```

5. 数组

   ```js
   var arr=[1,2,3];
   //不是内建类型
   var a=new Aarry();
   //栈方法
   a.pop();
   a.push();
   //队列方法
   a.shift();
   a.push();
   //----
   a.unshift();
   a.pop();
   
   //操作方法
   //concat()
   var aa=arr.concat("haha",["f","h"]);//基于当前数组所有项创建一个新数组
   //aa=[1,2,3,"haha","f","h"]
   //slice()
   var aaa=aa.slice(1,4);//基于当前数组中一个或多个项创建一个新数组
   //aa=[2,3,"haha","f"]
   //splice()---始终返回一个包含被删项的数组
   var a1=aa.splice(0,2);//起始位置，删除项数
   var a2=aa.splice(2,0,"a","b");//起始位置，删除项数，插入项
   
   //位置方法
   indexOf()//从前找，找到返回找到的位置，未找到返回-1
   lastIndexOf()//从后找  要查找的项 开始查找的位置（可选）
   
   //迭代方法（函数，作用域（可选））
   var aaaa=aa.every(function(item,index,array){
       return xxx;
   });//数组项的值 该项在数组中的位置 数组对象本身
   //every()---每一项都返回true，则true
   //filter()---返回该函数会返回true的项组成的数组
   //forEach()
   //map()---返回函数调用的结果组成的数组
   //some()---任意一项返回true，则true
   
   //归并方法(函数，初始值（可选）)
   var aa=a.reduce(function(prev,cur,index,array){
       return prev+cur;//作为下一项的第一个参数
   });//前一个值 当前值 项的索引 数组对象
   //reduceright()
   
   
   
   ```

6. NaN

   - 0除0会返回NaN，正数除0返回Infinity，负数除0返回-infinity

7. 数值转换

   1. Number()
   2. parseInt("string",基数)
   3. parseFloat("string")

8. 垃圾回收

   1. 标记清除(给当前不使用的值加上标记)
   2. 引用计数(基本不使用)

9. 内存管理

   1. 解除引用---将全局变量的值设为null(让值脱离执行环境，以便垃圾收集器下次运行时将其回收)

10. 基本包装类型

    1. 不建议显示创建包装类型

       * Boolean类型

         ```js
         var booleanObjext=new Boolean(true);
         //对象转换为true 所以在布尔表达式中使用Boolean对象可能会得不到想要的结果
         ```

       * Number类型

         ```js
         var numberObject=new Number(10);
         //toFixed(2)----显示几位小数
         //toExponential()----返回e表示法
         //toPrecision()---以合适的格式返回
         ```

       * String类型

         ```js
         var s="abcdefg";
         //string.length
         //字符方法
         s.charAt(1);//b
         s.charCodeAt(1);//b的字符编码
         //操作方法
         s.concat("hahaha","lalala");//"abcdefghahahalalala"
         s.slice(a,b);//a--开始位置 b--结束位置（未写默认长度）
         s.substring(a,b);//
         s.substr(a,b)；//b--长度
         //负值参数下
         //substr(-a,-b)-->-a+len,0
         //substring(-a,-b)-->0,0
         //slice(-a)-->-a+len,-a+len
         //位置方法
         s.indexOf("g",b*)；//从位置b往后找g
         s.lastIndexOf("g",b*)；
         //trim()
         s.trim();
         //删除前缀后缀空格 返回字符串副本
         //toLowerCase()---toUpperCase()
         //模式匹配方法
         //a=正则表达式/RegExp对象
         s.match(a);//返回一个数组
         s.search(a);//返回第一个匹配项的索引，-1
         s.replace(a,b);
         //a==字符串/RegExp对象
         //b==字符串/函数（模式匹配项，模式匹配项在字符串中的位置，原始字符串）
         s.split(a,b*);
         //a=字符串/RegExp对象
         //b=指定返回数组的大小
         //localeCompare()
         s.localeCompare(string);
         string在s之前===负数  相等===0   之后====正数
         //fromCharCode()
         s.fromCharCode(104,101);//字符编码转成字符串
         ```

11. Global对象

    1. URI编码方法

       ```js
       encodeURI();//替换空格字符
       encodeURIComponent();//替换所有特殊字符
       decodeURI();
       decodeURIComponent();
       ```

    2. eval()方法

       ```js
       eval("consloe.log("fd")");//执行语句
       ```

12. Math对象

    ```js
    Math.ceil();//向上取整
    Math.floor();//向下取整
    Math.round();//四舍五入
    ```

    ### 定时器

    ```js
    setTimeout(()=>{},100);
    //一段时间后执行函数 （仅一次）
setInterval(()=>{},100);
    //每隔一段时间执行函数（N次）
    ```
    
### 如何反转字符串


​    
​    1. ```js
​       '1234'.split('').reverse().join('');
​       ```
​    
​    2. ```js
   [...'1234'].reduce((prev,next)=>next+prev);
​       ```

    3. ```js
       function rev(str){
           if(str.length === 1){
               return str;
           }
           return str.slice(-1)+rev(str.slice(0,-1));
       } 
       ```


### js高度

```js

```



### 数组去重方法

1. ```js
   [...new Set(arr))]
   //转化成集合再转回数组
   Array.from(new Set(arr));
   ```

2. ```js
   arr.filter((item,index,arr)=>arr.indexOf(item) === index)
   //过滤掉后面出现的索引不等于indexOf的索引
   ```

3. ```js
   arr.reduce(a,b=>a.includes(b)?a:[...a,b],[])
   //返回如果下一个item存在当前reduce后的数组里返回这一个当前数组，否则加进去该数
   ```




1. 盒模型
2. css三角形
3. flex布局 （一行10个 一行5个）
4. 作用域 作用域链
5. eventloop
6. promise
7. 闭包
8. bfs
9. 设计模式  发布订阅模式
10. 项目状态管理
11. vue-router的几种





