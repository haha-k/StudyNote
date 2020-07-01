## 隐式声明

- 当前有a就用这个a 如果都没有声明 就会隐式声明a

```js
function fn(){
    var a = 1;//如果未声明该变量，则为全局变量
    function fn2() {
        a = 3;
    }
    fn2();
    console.log(a); 
}
fn();
console.log(a)  //当前有a,为3


```

- 
- 