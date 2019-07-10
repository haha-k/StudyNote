#### css编码技巧
1. 保持代码的DRY

1. HSLA
H: 色调 0表示红色,120表示绿色,240表示蓝色 [0,360]
S: 饱和度 [0%,100%]
L: 亮度 [0%,100%]
A: 透明度 [0,1]

* 实现半透明边框
```scss
    div{
        border:10px solid hsla(0,0%,100%,.5);
        background:white;
        background-clip:padding-box;
    }
```

`background-clip`:规定背景的绘制区域
border-box  背景延伸到边框盒(默认)
padding-box  背景延伸到内边距框
content-box  背景延伸到内容框

* 实现多重边框
1. `box-shadow`适用于多重
    ```scss
    div {
        background: yellowgreen;
        /* x偏移量 | y偏移量 | 阴影模糊半径 | 阴影扩散半径 | 阴影颜色 */
        box-shadow: 0 0 0 10px #655,
                    0 0 0 15px red;
    }
    ```
2. `outline`
    ```scss
    div {
        background: yellowgreen;
        border: 10px solid #655;
        /* 宽度 | 样式 | 颜色 */
        outline: 5px solid red
    }
    ```
- 只适用于2层边框
- 使用outline实现的边框不会贴合元素的圆角
- `outline-offset`:控制outline和元素边缘的间距

* 背景定位
1. `background-position`
    ```scss
    div {
        background: url(xxx.svg) no-repeat bottom right #58a;
        background-position:right 20px bottom 10px;
    }
    ```
- 盒模型`background-position`left top 默认以padding-box为准
- `background-origin`可以改变基准
    ```scss
    div {
        padding: 10px;
        background: url(xxx.svg) no-repeat bottom right #58a;
        background-origin: content-box;
    }
    ```
    - 此时背景图片距离边角的偏移量就和内边距保持一致了
- `calc`
    ```scss
    div {
        background: url(xxx.svg) no-repeat #58a;
        background-position: calc(100% - 20px) calc(100% - 10px)
    }
    ```
    - `-`左右两边加个空格



