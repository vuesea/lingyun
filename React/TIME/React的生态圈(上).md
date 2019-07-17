# React 生态圈(上)

### 一. Redux: JS 状态管理框架

1. 一张图带你读懂Redux![1563354034476](C:\Users\sunsea\AppData\Roaming\Typora\typora-user-images\1563354034476.png)
2. Redux让组件通信更加容易![1563354088815](C:\Users\sunsea\AppData\Roaming\Typora\typora-user-images\1563354088815.png)
3. Redux特征:Single Source of Truth![1563354234261](C:\Users\sunsea\AppData\Roaming\Typora\typora-user-images\1563354234261.png)告别了传统的MVC框架,直接错综复杂的逻辑,直接简洁.
4. Redux特性:可预测性![1563354365587](C:\Users\sunsea\AppData\Roaming\Typora\typora-user-images\1563354365587.png)
5. Redux特性:纯函数更新Store![1563354414834](C:\Users\sunsea\AppData\Roaming\Typora\typora-user-images\1563354414834.png)
6. 总结: 
   + 为什么使用Redux
   + Redux 的三个特性

------

### 二. Redux: 深入理解Store , Action , Reducer

1. 理解Store![1563354642184](C:\Users\sunsea\AppData\Roaming\Typora\typora-user-images\1563354642184.png)

2. 理解action![1563354667274](C:\Users\sunsea\AppData\Roaming\Typora\typora-user-images\1563354667274.png)
3. 理解reducer![1563354691470](C:\Users\sunsea\AppData\Roaming\Typora\typora-user-images\1563354691470.png)
4. Redux
5. ![1563355006730](C:\Users\sunsea\AppData\Roaming\Typora\typora-user-images\1563355006730.png)
6. 理解combineReducers![1563355054831](C:\Users\sunsea\AppData\Roaming\Typora\typora-user-images\1563355054831.png)
7. 理解bindActionCreators![1563355099018](C:\Users\sunsea\AppData\Roaming\Typora\typora-user-images\1563355099018.png)
8. 理解bindActionCreators![1563355144736](C:\Users\sunsea\AppData\Roaming\Typora\typora-user-images\1563355144736.png)
9. DEMO练习

------

### 三. Redux: 在React中使用Redux

1. 事例![1563355671240](C:\Users\sunsea\AppData\Roaming\Typora\typora-user-images\1563355671240.png)
2. connect的工作原理: 高阶组件![1563355705880](C:\Users\sunsea\AppData\Roaming\Typora\typora-user-images\1563355705880.png)
3. DEMO

------

### 四. Redux: 理解异步Action , Redux 中间件

1. 事例![1563355936196](C:\Users\sunsea\AppData\Roaming\Typora\typora-user-images\1563355936196.png)
2. Redux 中间件(Middleware)
   1. 截获 action
   2. 发出 action
3. DEMO
4. 总结:
   + 异步 action 不是特殊的action , 而是多个同步 action 的组合使用
   + 中间件在 dispatcher 中获取 action 做特殊处理

------

### 五. Redux: 如何组织Action 和 Reducer

1. '标准' 形式Redux Action 的问题
   + 所有的Action放一个文件 ,会无限扩展
   + Action, Reducer 分开 ,实现业务逻辑时需要来回切换
   + 系统中有哪些Action不够直观
2. 新的方式: 单个action 和 reducer 放在同一个文件![1563356812510](C:\Users\sunsea\AppData\Roaming\Typora\typora-user-images\1563356812510.png)
3. 新的方式 :每个文件一个Action![1563356875034](C:\Users\sunsea\AppData\Roaming\Typora\typora-user-images\1563356875034.png)
4. DEMO

------

### 六. Redux: 理解Redux的运行基础,不可变数据(Immutability)

1. 不可变数据(Immutability)![1563357217656](C:\Users\sunsea\AppData\Roaming\Typora\typora-user-images\1563357217656.png)
2. 为啥需要不可变数据
   + 性能优化
   + 易于调试和跟踪
   + 易于推测
3. 如何操作不可变数据
   + 原生写法: {...}, Object.assign
   + immutability-helper
   + immer
4. 原生写法: {...}, Object.assign![1563357421722](C:\Users\sunsea\AppData\Roaming\Typora\typora-user-images\1563357421722.png)
5. immutability-helper![1563357472097](C:\Users\sunsea\AppData\Roaming\Typora\typora-user-images\1563357472097.png)
6. immer![1563357487793](C:\Users\sunsea\AppData\Roaming\Typora\typora-user-images\1563357487793.png)
7. 小结:
   + 不可变数据的含义
   + Redux为什么需要使用不可变数据
   + 如何操作不可变数据

------

