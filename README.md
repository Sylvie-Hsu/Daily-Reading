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

### 2019-08-07

#### JavaScript垃圾回收

:link:[简单了解JavaScript垃圾回收机制](https://juejin.im/post/5a6b3fcaf265da3e2c385375)

* 引用计数法：记录下多少程序在引用自己，可能导致循环引用无法回收
* 标记清除法
  * 标记阶段：从全局作用域逐层往里遍历（深度遍历），遍历到的对象则是被引用的，打上标记
  * 清除阶段：遍历整个堆，回收没有打上标记的对象

### 2019-08-08

#### JavaScript选择题

:link:[送你43道JavaScript面试题](https://mp.weixin.qq.com/s/E4HgxyagrU1pn0lp-ba6vg)

* map & parseInt

  ```js
  [1,2,3,4,5,6,7,8].map(parseInt)
  [1,2,3,4,5,6,7,8,9,10,11].map(parseInt)
  /*
  [1, NaN, NaN, NaN, NaN, NaN, NaN, NaN]
  [1, NaN, NaN, NaN, NaN, NaN, NaN, NaN, NaN, 9, 11]
  [].map(function(item,index){...})
  parseInt(arg1:number,arg2:number) arg2代表进制
  */
  ```

### 2019-08-09

#### Nginx反向代理与负载均衡

:link:[谁说前端不需要懂-Nginx反向代理与负载均衡](https://juejin.im/post/5b01336af265da0b8a67e5c9)

### 2019-08-10

#### 前端面试

:link:[Javascript 面试中经常被问到的三个问题!](https://segmentfault.com/a/1190000018257074)

### 2019-08-11

#### 前端面试

:link:[破解前端面试（80% 应聘者不及格系列）：从 DOM 说起](https://juejin.im/post/58f558efac502e006c3e5c97)

### 2019-08-12

#### 前端面试

:link:[面试的信心来源于过硬的基础](https://segmentfault.com/a/1190000013331105)

### 2019-08-13

:link:[破解前端面试（80% 应聘者不及格系列）：从闭包说起](https://juejin.im/post/58f1fa6a44d904006cf25d22#heading-0)

###2019-08-14

:link:[正则表达式不要背](https://juejin.im/post/5cdcd42551882568651554e6)

:link:https://regexper.com

:link:[前端必知必会—操作URL的黑科技](https://juejin.im/post/5d038c9051882548ac439933)

* 专门用来处理URL的query接口：`URLSearchParams` 

:link: [前端路由原理解析和实现](https://juejin.im/post/5cd8d609e51d456e7b372155)

* **基于Hash实现**

  通过`html`中的`<a href="#/...">...</a>`改变URL，`script`中通过监听路由变化切换视图。

  ```html
  <!DOCTYPE html>
  <html>
    <head>    
    </head>
    <body>
      <ul>
        <!-- 定义路由 -->
        <li><a href="#/home">home</a></li>
        <li><a href="#/about">about</a></li>
        <!-- 渲染路由对应的 UI -->
        <div id="routeView"></div>
      </ul>
    </body>
    <script>
      // 页面加载完不会触发 hashchange，这里主动触发一次 hashchange 事件
      window.addEventListener('DOMContentLoaded', onLoad)
      // 监听路由变化
      window.addEventListener('hashchange', onHashChange)
  
      // 路由视图
      var routerView = null
  
      function onLoad () {
        routerView = document.querySelector('#routeView')
        onHashChange()
      }
  
      // 路由变化时，根据路由渲染对应 UI
      function onHashChange () {
        switch (location.hash) {
          case '#/home':
            routerView.innerHTML = 'Home'
            return
          case '#/about':
            routerView.innerHTML = 'About'
            return
          default:
            return
        }
      }
    </script>
  </html>
  ```

* **基于History实现**

  利用了 HTML5 History Interface 中新增的`pushState()`和`replaceState()`方法。

  > 在Hash模式下，前端路由修改的是 # 中的信息，而浏览器请求时不会将 # 后面的数据发送到后台，所以没有问题。但是在History下，你可以自由的修改path，当刷新时，如果服务器中没有相应的响应或者资源，则会刷新出来404页面。

  ```html
  <!DOCTYPE html>
  <html>
    <head>    
    </head>
    <body>
        <ul>
          <li><a href='/home'>home</a></li>
          <li><a href='/about'>about</a></li>
          <div id="routeView"></div>
        </ul>
      </body>
    <script>
      // 页面加载完不会触发 hashchange，这里主动触发一次 hashchange 事件
      window.addEventListener('DOMContentLoaded', onLoad)
      // 监听路由变化
      window.addEventListener('replaceState', onPopState)
  
      // 路由视图
      var routerView = null
  
      function onLoad () {
        routerView = document.querySelector('#routeView')
        onPopState()
  
        // 拦截 <a> 标签点击事件默认行为，点击时使用 pushState 修改 URL并更新手动 UI，从而实现点击链接更新 URL 和 UI 的效果。
        var linkList = document.querySelectorAll('a[href]')
        linkList.forEach(el => el.addEventListener('click', function (e) {
          e.preventDefault()
          history.pushState(null, '', el.getAttribute('href'))
          onPopState()
        }))
      }
  
      // 路由变化时，根据路由渲染对应 UI
      function onPopState () {
        switch (location.pathname) {
          case '/home':
            routerView.innerHTML = 'Home'
            return
          case '/about':
            routerView.innerHTML = 'About'
            return
          default:
            return
        }
      }
    </script>
  </html>
  ```

### 2019-08-15

:link: [不好意思！耽误你的十分钟，让MVVM原理还给你](https://juejin.im/post/5abdd6f6f265da23793c4458)

