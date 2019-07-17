# React 生态圈(上)

### 一.  React Router: 路由不只是页面切换, 更是代码的组织方式

1. 为什么需要路由![1563358001483](C:\Users\sunsea\AppData\Roaming\Typora\typora-user-images\1563358001483.png)
2. 路由实现的基本架构![1563358040830](C:\Users\sunsea\AppData\Roaming\Typora\typora-user-images\1563358040830.png)
3. React Router 的实现![1563358096316](C:\Users\sunsea\AppData\Roaming\Typora\typora-user-images\1563358096316.png)
4. React Router 的特征![1563358142235](C:\Users\sunsea\AppData\Roaming\Typora\typora-user-images\1563358142235.png)
5. 三种路由的实现方式
   + URL路径
   + hash路由
   + 内存路由

6. 基于路由配置进行资源组织
   + 实现业务逻辑的松耦合
   + 易于扩展 , 重构和维护
   + 路由层面实现 Lazy Load

7. React Router API![1563358370537](C:\Users\sunsea\AppData\Roaming\Typora\typora-user-images\1563358370537.png)
8. <link>![1563358398012](C:\Users\sunsea\AppData\Roaming\Typora\typora-user-images\1563358398012.png)
9. <NavLink>![1563358429341](C:\Users\sunsea\AppData\Roaming\Typora\typora-user-images\1563358429341.png)
10. <Prompt>![1563358450975](C:\Users\sunsea\AppData\Roaming\Typora\typora-user-images\1563358450975.png)
11. <Redirect>![1563358485756](C:\Users\sunsea\AppData\Roaming\Typora\typora-user-images\1563358485756.png)
12. <Route>![1563358509610](C:\Users\sunsea\AppData\Roaming\Typora\typora-user-images\1563358509610.png)
13. <Switch>![1563358529230](C:\Users\sunsea\AppData\Roaming\Typora\typora-user-images\1563358529230.png)
14. 总结:
    + 前端路由是什么
    + React Router 如何实现路由
    + 基于路由思考资源的组织
    + React Router 核心API

------

### 二. React Router: 参数定义 ,嵌套路由的使用场景

1. 通过URL传递参数![1563358806026](C:\Users\sunsea\AppData\Roaming\Typora\typora-user-images\1563358806026.png)
2. 何时需要URL参数==> 页面状态尽量通过URL参数定义![1563358899966](C:\Users\sunsea\AppData\Roaming\Typora\typora-user-images\1563358899966.png)
3. 嵌套路由![1563358922773](C:\Users\sunsea\AppData\Roaming\Typora\typora-user-images\1563358922773.png)
4. 总结:
   + 路由参数的传递
   + 嵌套路由的实现

------

### 三. UI组件库的对比和介绍

1. Ant.Design
2. Material UI
3. Semantic UI
4. 选择UI库的考虑因素
   + 组件库是否齐全
   + 样式风格是否符合业务需求
   + API设计是否便捷和灵活
   + 技术支持是否完善
   + 开发是否活跃
5. DMEO

------

### 四. 使用Next.js创建React同构应用

1. 什么是同构应用![1563359259859](C:\Users\sunsea\AppData\Roaming\Typora\typora-user-images\1563359259859.png)
2. 创建页面![1563359286147](C:\Users\sunsea\AppData\Roaming\Typora\typora-user-images\1563359286147.png)
3. 在页面中使用其他的React组件
   + 页面也是标准的node 模块 , 可使用其他React 组件
   + 页面会针对性打包, 仅包含其引入的组件

4. 使用Link 实现同构路由![1563359510635](C:\Users\sunsea\AppData\Roaming\Typora\typora-user-images\1563359510635.png)
5. 动态加载页面![1563359537468](C:\Users\sunsea\AppData\Roaming\Typora\typora-user-images\1563359537468.png)
6. DEMO

------

### 五. 使用Jest, Enzyme等工具进行单元测试

1. React 应用让前端单元测试变得容易
   + React 应用很少需要访问浏览器API
   + 虚拟DOM可以在NodeJS环境运行和测试
   + Redux  隔离了状态管理 ,纯数据层单元测试
2. 单元测试涉及的工具
   + Jest:Facebook 开源的JS 单元测试框架
   + JS DOM:浏览器环境的NodeJS模拟
   + Enzyme : React 组件渲染和测试
   + nock: 模拟HTTP请求
   + sinon:函数模拟和调用跟踪
   + intanbul:单元测试覆盖率

3. Jest![1563361460728](C:\Users\sunsea\AppData\Roaming\Typora\typora-user-images\1563361460728.png)
4. jsdom![1563361481965](C:\Users\sunsea\AppData\Roaming\Typora\typora-user-images\1563361481965.png)
5. Enzyme![1563361505914](C:\Users\sunsea\AppData\Roaming\Typora\typora-user-images\1563361505914.png)
6. Nock![1563361520217](C:\Users\sunsea\AppData\Roaming\Typora\typora-user-images\1563361520217.png)
7. Sinon![1563361553939](C:\Users\sunsea\AppData\Roaming\Typora\typora-user-images\1563361553939.png)
8. Istanbul![1563361586646](C:\Users\sunsea\AppData\Roaming\Typora\typora-user-images\1563361586646.png)
9. DEMO

------

### 六. 常用的开发调试工具:ESLint, Prettier, React DevTool....

1. ESLint![1563361673040](C:\Users\sunsea\AppData\Roaming\Typora\typora-user-images\1563361673040.png)
2. prettier![1563361694098](C:\Users\sunsea\AppData\Roaming\Typora\typora-user-images\1563361694098.png)
3. React Dev Tools 
4. Redux Dev Tools
5. DEMO