# React 核心概念

### 一. Hello World 

------

### 二.JSX 简介

解读:

1. 为什么使用jsx?

2. 在JSX中嵌入表达式

3. JSX也是一个表达式

4. jsx特定属性 

   + JSX 里的 `class` 变成了 [`className`](https://developer.mozilla.org/en-US/docs/Web/API/Element/className)，
   + 而 `tabindex` 则变为 [`tabIndex`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/tabIndex)。

5. 使用jsx指定子属性

6. jsx防止注入攻击

7. jsx表示对象

   ```
   // 注意：这是简化过的结构
   const element = {
     type: 'h1',
     props: {
       className: 'greeting',
       children: 'Hello, world!'
     }
   };
   ```

------

### 三.元素渲染

*元素是构成React 应用的最小砖块.*

```
const element = <h1>Hello, world</h1>
```

1. 讲一个元素渲染为DOM.

2. 更新已渲染的元素.

+ 更新 UI 唯一的方式是创建一个全新的元素，并将其传入 `ReactDOM.render()`

3. React 只更新他需要更新的部分

+ React DOM 会将元素和它的子元素与它们之前的状态进行比较，并只会进行必要的更新来使 DOM 达到预期的状态。

------

### 四.组件&Props

*组件允许你将 UI 拆分为独立可复用的代码片段，并对每个片段进行独立构思。*

1. 函数组件与class组件

2. 渲染组件

+ react元素不只是DOM标签,还可以是用户自定义的组件.
+ 当 React 元素为用户自定义组件时，它会将 JSX 所接收的属性（attributes）转换为单个对象传递给组件，这个对象被称之为 “props”。
+  **注意：**组件名称必须以大写字母开头。

3. 组合组件

4. 提取组件

+ 将组件拆分为更小的组件

5. Props 的只读性

+ 组件无论是使用函数声明还是通过class声明，都决不能修改自身的 props。
+ 所有 React 组件都必须像纯函数一样保护它们的 props 不被更改

------

### 五.State&生命周期

封装真正可复用的 `Clock` 组件

1. 将函数组件转换为class组件
2. 向class组件中添加局部的state
3. 将生命周期方法添加到Class中
   + `componentDidMount()` 方法会在组件已经被渲染到 DOM 中后运行
   +  `componentWillUnmount()` 生命周期方法中清除计时器：

4. 正确的使用State

   + 不要直接修改State 

     + 使用 `setState()`:

     + 构造函数是唯一可以给 `this.state` 赋值的地方：

   + State 的更新可能是异步的

   + State的更新会被合并

5. 数据时向下流动的

------

### 六.事件处理

*React 元素的事件处理和 DOM 元素的很相似，但是有一点语法上的不同:*

- *React 事件的命名采用小驼峰式（camelCase），而不是纯小写。*
- *使用 JSX 语法时你需要传入一个函数作为事件处理函数，而不是一个字符串。*

+ React 中另一个不同点是你不能通过返回 `false` 的方式阻止默认行为。你必须显式的使用 `preventDefault` 

1.向事件处理程序传递参数.

### 七.条件渲染

*React 中的条件渲染和 JavaScript 中的一样，使用 JavaScript 运算符 [`if`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/if...else) 或者[条件运算符](https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Operators/Conditional_Operator)去创建元素来表现当前的状态，然后让 React 根据它们来更新 UI。*

1. 元素变量
2. 与运算符&&
3. 三目运算符
4. 阻止组件渲染
   + 以让 `render` 方法直接返回 `null`，而不进行任何渲染。

------

### 八.列表&Key

使用map() 转化列表

1. 渲染多个组件
2. 基础列表组件
3. key(独一无二)
4. 用key提取组件
   + 经验法则：在 `map()` 方法中的元素需要设置 key 属性。

5. key 只是在兄弟节点之间必须唯一
6. **在jsx中嵌入map()** 灵活根据自己的业务需求.选择

------

### 九. 表单

*HTML 表单元素的工作方式和其他的 DOM 元素有些不同，这是因为表单元素通常会保持一些内部的 state。*

1. 受控组件

2. textarea标签

   + 在 React 中，`<textarea>` 使用 `value` 属性代替。

3. select 标签

   + `<select>` 创建下拉列表标签

   + React 并不会使用 `selected` 属性，而是在根 `select` 标签上使用 `value` 属性。

   + **注意**:

     你可以将数组传递到 `value` 属性中，以支持在 `select` 标签中选择多个选项：

     ```
     <select multiple={true} value={['B', 'C']}>
     ```

4. 文件 input 标签 ==>非受控组件

   + ```
     <input type="file" />
     ```

5. 处理多个输入

   + 当需要处理多个 `input` 元素时，我们可以给每个元素添加 `name` 属性，并让处理函数根据 `event.target.name` 的值选择要执行的操作。

6. 受控输入空值

   + 在[受控组件](https://react.docschina.org/docs/forms.html#controlled-components)上指定 value 的 prop 可以防止用户更改输入。如果指定了 `value`，但输入仍可编辑，则可能是意外地将`value` 设置为 `undefined` 或 `null`。

7. 受控组件的替代品

   + [非受控组件](https://react.docschina.org/docs/uncontrolled-components.html)

8. 成熟的解决方案

   +  [Formik](https://jaredpalmer.com/formik)

------

### 十.状态提升

*通常，多个组件需要反映相同的变化数据，这时我们建议将共享状态提升到最近的共同父组件中去。*

1.添加第二个输入框

