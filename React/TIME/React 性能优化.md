# React 性能优化

### 一. 性能永远是第一需求: 时刻考虑性能问题

1. 如何避免应用出现性能问题
   + 了解常见的性能问题场景
   + 时刻注意代码的潜在性能问题
   + 注意可重构的代码
   + 了解如何使用工具定位性能问题
2. DEMO

------

### 二. 网络性能优化: 自动按需加载

1. 如何在React 中实现按需加载
   + 什么是按需加载
   + 使用Webpack 的import API
   + 使用react-loadable 库 实现React 异步加载
2. demo

------

### 三. 使用Reselect 避免重复计算

1. Reselect : 创建自动缓存的数据处理流程![1563374020617](C:\Users\sunsea\AppData\Roaming\Typora\typora-user-images\1563374020617.png)
2. DEMO

------

### 四. 下一代React :异步渲染

1. 异步渲染的俩部分![1563374063738](C:\Users\sunsea\AppData\Roaming\Typora\typora-user-images\1563374063738.png)
2. 时间分片
   + 虚拟DOM的diff操作可以分片进行
   + React 新的API : unstable_deferredUpdates
   + Chrome 新的API: requestIdCallback
3. 渲染挂起
   + 新内置组件: Timeout
   + unstable_deferUpdate
4. DEMO

------

### 五. 使用Chrome DevTool 进行性能调优

1. 借助工具发现性能问题
   + 使用React DevTool 找到多余渲染
   + 使用 Chrome DevTool定位性能瓶颈
2. DEMO