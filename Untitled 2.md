### Spring Security

相比于Shiro，Spring Security更繁杂，





通过vue-cli搭建了vue工程，封装了axios，增加拦截器等等，引入了ElementUI的一些组件来进行组件开发，完成了计算机资源库的前端登录页面，能根据登录角色跳转不同页面，分配不同的路由，引入VueX来存储登录状态,管理员端完成侧边栏的动态渲染，用户管理，完成根据表格用户数据导出excel，完成导入excel数据生成表格，还未和后端api联调，后端集成了Spring Security来进行用户认证，并返回JWT，完成接口用户认证，完成后台用户相关的api，数据库表设计已完成，后端集成了Druid用作数据库的连接池，集成了Mybatis-plus来操作数据库。



1. 在开发用户认证的时候，技术选型在Shiro和Spring Security之中徘徊，最后选择了Spring Security来进行用户认证，在配置Spring Security中遇到了问题就是Spring Security 有一个默认登陆页面，并且前端只能提交表单类型的请求体，后未找到在后端的解决方案，最后就是让前端提交表单类型的请求体来解决的

2. 在前端用户管理的表格的实现的时候，使用ElementUI的日期区间el-date-picker控件的时候，绑定值改变后未回显，需要其它表单项改变才回显，暂不知道是什么原因造成的，查询资料后未果，暂未解决
3. 在前端用户导出的时候，使用ElementUI的el-upload组件的时候，
4. 