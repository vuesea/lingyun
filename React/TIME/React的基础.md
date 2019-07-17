# React的基础

------

### 一. React 的历史背景和主要特性

+ 历史背景 ===> "简单"的功能一再出现Bug

  1. 传统Web UI 开发的问题
     + 传统的UI操作关注太多的细节
     + 应用程序的状态分散在各处,难以追踪和维护

  2. React: 始终整体"刷新" 页面==>**无需关心细节**

     + 局部刷新 ===> React 整体刷新

     + React 很简单

       1. 一个概念

       2. 4个必须的API

       3. 单向数据流

       4. 完善的错误提示

  3. Flux:单项数据流

     问题:传统的MVC难以扩展和维护

     方案: Flux架构:单向数据流.

     ![1563342833938](C:\Users\sunsea\AppData\Roaming\Typora\typora-user-images\1563342833938.png)

     + 衍生项目
       1. **Redux**
       2. MobX

     ------

     ### 二. 以组件方式考虑UI的构建

     1. 以组件的方式考虑UI的构建

        + 将UI组织成组件树的形式

          ![1563343152910](C:\Users\sunsea\AppData\Roaming\Typora\typora-user-images\1563343152910.png)

        + 理解React组件![1563343247575](C:\Users\sunsea\AppData\Roaming\Typora\typora-user-images\1563343247575.png)

          1.React组件一般不提供方法,而是某种状态机

          2.React组件可以理解为一个纯函数

          3.单向数据绑定

        + ![1563343410943](C:\Users\sunsea\AppData\Roaming\Typora\typora-user-images\1563343410943.png)
        + 何时创建组件:单一职责原则
          1. 每一个组件只做一件事
          2. 如果组件变得复杂,那么应该拆分成小组件

        + 数据状态管理: DRY原则
          1. 能计算得到的状态就不要单独存储
          2. 组件尽量无状态,所需数据通过props获取

     2. dome001

        + 第一个dome:创建一个简单的组件==>TabSelect![1563343773835](C:\Users\sunsea\AppData\Roaming\Typora\typora-user-images\1563343773835.png)
          1. 创建静态的UI
          2. 考虑组件的状态组成
          3. 考虑组件的交互方式

------

### 三. 理解JSX: 不是模板语法, 只是一种语法糖

1. JSX:  在JavaScript 代码中直接写HTML标记![1563344938746](C:\Users\sunsea\AppData\Roaming\Typora\typora-user-images\1563344938746.png)

1. JSX的本质: 动态创建组件的语法糖
   + 实例1:![1563345005095](C:\Users\sunsea\AppData\Roaming\Typora\typora-user-images\1563345005095.png)
   + 实例2![1563345055324](C:\Users\sunsea\AppData\Roaming\Typora\typora-user-images\1563345055324.png)

3. 在JSX中使用表达式
   1. JSX 本身也是表达式![1563345207629](C:\Users\sunsea\AppData\Roaming\Typora\typora-user-images\1563345207629.png)
   2. 在属性中使用表达式![1563345244575](C:\Users\sunsea\AppData\Roaming\Typora\typora-user-images\1563345244575.png)
   3. 延展属性![1563345268337](C:\Users\sunsea\AppData\Roaming\Typora\typora-user-images\1563345268337.png)
   4. 表达式作为子元素![1563345291676](C:\Users\sunsea\AppData\Roaming\Typora\typora-user-images\1563345291676.png)

4. 对比其他的模板语法
   1. ng模板语法
   2. vue模板语法
   3. JSX
   4. **JSX 的优点**
      + 声明式创建界面的直观
      + 代码动态创建界面的灵活
      + 无需学习新的模板语言

5. 约定: 自定义组件以大写字母开头
   1. React 以为小写的tag是原生DOM节点,如 div
   2. 大写字母开头的为自定义组件
   3. JSX标记可以直接使用属性语法,例如<menu.Item />

------

### 四: React 组件的生命周期及其使用场景

1. constructor
   + 用于初始化内部状态,很少使用
   + 唯一可以直接修改state的地方
2. getDerivedStateFromProps
   + 当state需要从props初始化时使用
   + 尽量不要使用: 维护两者状态一致性会增加复杂度
   + 每次render都会调用
   + 典型场景: **表单控件获取默认值**
3. componentDidMount
   + UI渲染完成后调用
   + 只执行一次
   + 典型场景: **获取外部资源**
4. componentWillUnmount
   + 组件移除时被调用
   + 典型场景: **资源释放**
5. getSnapshotBeforeUpdate
   + 在页面render之前调用, state已更新
   + 典型场景: **获取render之前的DOM状态**
6. componentDidUpdate
   + 每次UI更新时被调用
   + 典型场景: **页面需要根据Props 变化重新获取数据**
7. shouldComponentUpdate
   + 决定 Virtual DOM 是否重绘
   + 一般可以由PureComponent自动实现
   + 典型场景:**性能优化**

8. dome002
   + dome练习

------

### 五: 理解Virtual DOM的工作原理, 理解key属性的作用

1. JSX的运行基础: Virtual DOM
   + 虚拟 DOM 是如何工作的![1563346998172](C:\Users\sunsea\AppData\Roaming\Typora\typora-user-images\1563346998172.png)
   + 广度优先分层计较![1563347040864](C:\Users\sunsea\AppData\Roaming\Typora\typora-user-images\1563347040864.png)
   + 根节点开始比较![1563347067393](C:\Users\sunsea\AppData\Roaming\Typora\typora-user-images\1563347067393.png)
   + 属性变化及属性![1563347102538](C:\Users\sunsea\AppData\Roaming\Typora\typora-user-images\1563347102538.png)
   + 节点类型发生变化![1563347137008](C:\Users\sunsea\AppData\Roaming\Typora\typora-user-images\1563347137008.png)
   + 节点跨层移动![1563347173313](C:\Users\sunsea\AppData\Roaming\Typora\typora-user-images\1563347173313.png)
2. 虚拟DOM 的俩个假设
   + 组件的DOM 结构是相对稳定的
   + 类型相同的兄弟节点可以被唯一标识
3. DEMO003
4. 总结:
   + 算法复杂度为O(n)
   + 虚拟DOM如何计算diff
   + key属性的作用

------

### 六. 组件复用的另外两种形式: 高阶组件和函数作为子组件

1. 高阶组件(HOC)![1563347457918](C:\Users\sunsea\AppData\Roaming\Typora\typora-user-images\1563347457918.png)
2. 函数作为子组件![1563347496405](C:\Users\sunsea\AppData\Roaming\Typora\typora-user-images\1563347496405.png)
3. DOME演练
4. 总结: 
   + 高阶组件和函数子组件都是设计模式
   + 可以实现更多场景的组件复用

------

### 七: 理解Context API 的使用场景

1. React16.3 新特性: Context API![1563347782112](C:\Users\sunsea\AppData\Roaming\Typora\typora-user-images\1563347782112.png)
2. React16.3 新特性: Context API![1563347816262](C:\Users\sunsea\AppData\Roaming\Typora\typora-user-images\1563347816262.png)
3. DOME练习
4. 总结: 
   + Conext API的使用方法
   + 适用场景

------

### 八.使用脚手架工具创建React应用: Create React App, Codesandbox, Rekit

1. 为什么需要脚手架工具
2. 三种脚手架
   + creact-react-app
   + Rekit
   + Online:Codesandbox.io
3. DOME

------

### 九. 打包和部署

1. 为什么需要打包?
   + 编译ES6语法特征, 编译JSX
   + 整合资源, 例如图片, Less/Sass
   + 优化代码体积

2. 使用webpack进行打包![1563348321911](C:\Users\sunsea\AppData\Roaming\Typora\typora-user-images\1563348321911.png)
3. 打包注意事项
   + 设置nodejs 环境为production
   + 禁用开发时专用代码 ,比如logger
   + 设置应用根路径

4. DOME

------



