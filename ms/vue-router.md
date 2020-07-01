### vue-router有哪些模式





### hash和history的区别

- `hash`指url后的#号以及后面的字符，`hash`值得变化不会导致浏览器向服务器发送请求，`hash`的改变会触发hashChange事件，`浏览器的前进后退也能对其进行控制`

- `history`



### 说一下vue-router

- vue router是Vue用来进行路由管理的，将组件去和路由进行一个映射，可以通过meta字段来定制路由的元信息，通过<router-link>去进行一个导航，将<router-view>去渲染出来，

### vue-router路由平常怎么用的，比如从一个路由跳转到另一个路由怎么实现

- router-link

- this.$router.push,往history栈添加一条记录
- this.$router.replace替换掉当前的history记录
- this.$router.go在history记录中间前后退多少步



### vue-router底层是怎么实现的



### 你说一下路由守卫

通过router.beforeEach注册一个全局前置守卫

路由守卫有三个参数，第一个是即将要进入的目标路由对象to，第二个是当前导航正要离开的路由，第三个是进入到下一个路由的钩子函数

router.afterEach全局后置钩子，比前置守卫少一个next参数

组件内守卫

