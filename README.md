# Daily Reading

### 2019-08-01

#### 前端性能监测工具

:link:[5 分钟撸一个前端性能监控工具](https://juejin.im/post/5b7a50c0e51d4538af60d995)

![Navigation Timing attributes](https://user-gold-cdn.xitu.io/2018/8/20/16555cb56942d42b?imageView2/0/w/1280/h/960/format/webp/ignore-error/1)

大致思路是根据浏览器`Performance`API检测关注资源加载的耗时情况，获取超时资源后进行上报。

### 2019-08-02

#### 发布订阅模式

- [ ] Practice

:link:[发布订阅模式，在工作中它的能量超乎你的想象](https://juejin.im/post/5b125ad3e51d450688133f22)

![Related image](https://realtimeapi.io/wp-content/uploads/2017/09/pubsub-1.png)

所以本质就是先用数组把所有函数存起来，需要调用的时候再拿着参数和对应key去找？所谓“监听”也只是直接调用了对应key下面的函数emmmm……

:bookmark_tabs:[Node.js events](https://github.com/nodejs/node/blob/698d479aff2a71267a13ba1f3fda390221ea591e/doc/api/events.md)

### 2019-08-03

#### Babel相关概念

- [ ] Practice

:link:[面试官: 你了解过Babel吗？写过Babel插件吗? 答: 没有。卒](https://juejin.im/post/5a9315e46fb9a0633a711f25) 

:link:[Babel相关概念](https://github.com/jamiebuilds/babel-handbook/blob/master/translations/zh-Hans/plugin-handbook.md)

:link:[AST Explorer](https://astexplorer.net/)

Babel将JavaScript解析成AST，（Babel插件更改AST，最后由Babel输出代码）。

Babel 的三个主要处理步骤分别是： **解析（parse）**，**转换（transform）**，**生成（generate）**。

* **解析**

  解析步骤接收代码并输出 AST。这个步骤分为两个阶段：**词法分析（Lexical Analysis）**和**语法分析（Syntactic Analysis）**。

  * **词法分析**：把字符串形式的代码转换为**令牌（tokens）**流，（可以把令牌看作是一个扁平的语法片段数组）。
  * **语法分析**：语法分析阶段会把一个令牌流转换成 AST 的形式。 这个阶段会使用令牌中的信息把它们转换成一个 AST 的表述结构，这样更易于后续的操作。

* **转换**

  转换步骤接收 AST 并对其进行遍历，在此过程中对节点进行添加、更新及移除等操作。 这是 Babel 或是其他编译器中最复杂的过程，同时也是插件将要介入工作的部分。

* **生成**

  代码生成步骤把最终（经过一系列转换之后）的 AST 转换成字符串形式的代码，同时还会创建源码映射（source maps）。代码生成其实很简单：深度优先遍历整个 AST，然后构建可以表示转换后代码的字符串。

### 2019-08-04

#### Webpack

- [ ] Practice

:link: [手把手教你撸一个简易的 webpack](https://juejin.im/post/5b192afde51d45069c2efe5a) 

![Image result for webpack](https://miro.medium.com/max/1420/1*_AEYv1m43cH8a0yGrOi3mQ.png)

基础打包编译工具的功能：

1. 将ES6语法转换成ES5
   - 通过`babylon`生成AST
   - 通过`babel-core`将AST重新生成源码
2. 处理模块加载依赖
   * 通过`babel-tranverse`遍历`AST`视图，通过`ImportDeclaration`得到根文件依赖属性
   * 通过深度遍历，得到完整的深度依赖关系
3. 生成一个可以再浏览器加载执行的js文件
   * 源码包装：生成`modules`对象，注册`require` `module.exports`
   * 函数内部循环执行每个依赖文件的JS代码

### 2019-08-05

#### How JavaScript works

:link:[How JavaScript works: an overview of the engine, the runtime, and the call stack](https://blog.sessionstack.com/how-does-javascript-actually-work-part-1-b0bacc073cf)

这篇就是个广告好嘛……只讲了一些最基础的东西orz

### 2019-08-06

#### JavaScript 复杂判断的优雅写法

:link:[JavaScript 复杂判断的更优雅写法](https://juejin.im/post/5bdfef86e51d453bf8051bf8)

自从`switch-case`被嘲笑之后就开始关心这种奇淫技巧……十分涨:cheese:，记下来记下来