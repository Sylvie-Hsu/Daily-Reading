# Daily Reading

### 2019-08-01

#### 前端性能监测工具

:link:[5 分钟撸一个前端性能监控工具](https://juejin.im/post/5b7a50c0e51d4538af60d995)![Navigation Timing attributes](https://user-gold-cdn.xitu.io/2018/8/20/16555cb56942d42b?imageView2/0/w/1280/h/960/format/webp/ignore-error/1)大致思路是根据浏览器`Performance`API检测关注资源加载的耗时情况，获取超时资源后进行上报。

### 2019-08-02

#### 发布订阅模式

:link:[发布订阅模式，在工作中它的能量超乎你的想象](https://juejin.im/post/5b125ad3e51d450688133f22)

![Related image](https://realtimeapi.io/wp-content/uploads/2017/09/pubsub-1.png)

所以本质就是先用数组把所有函数存起来，需要调用的时候再拿着参数和对应key去找？所谓“监听”也只是直接调用了对应key下面的函数emmmm……