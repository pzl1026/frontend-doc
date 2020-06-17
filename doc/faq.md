## app如何实现与h5通信
 
## 介绍下 npm 模块安装机制，为什么输入 npm install 就可以自动安装对应的模块？
[https://github.com/Advanced-Frontend/Daily-Interview-Question/issues/22](https://github.com/Advanced-Frontend/Daily-Interview-Question/issues/22)

## 有以下 3 个判断数组的方法，请分别介绍它们之间的区别和优劣Object.prototype.toString.call() 、 instanceof 以及 Array.isArray()
[https://github.com/Advanced-Frontend/Daily-Interview-Question/issues/23](https://github.com/Advanced-Frontend/Daily-Interview-Question/issues/23)

## 介绍下观察者模式和订阅-发布模式的区别，各自适用于什么场景
>在观察者模式中，观察者是知道Subject的，Subject一直保持对观察者进行记录。然而，在发布订阅模式中，发布者和订阅者不知道对方的存在。它们只有通过消息代理进行通信。<br/>
>在发布订阅模式中，组件是松散耦合的，正好和观察者模式相反。<br/>
>观察者模式大多数时候是同步的，比如当事件触发，Subject就会去调用观察者的方法。而发布-订阅模式大多数时候是异步的（使用消息队列）。<br/>
>观察者 模式需要在单个应用程序地址空间中实现，而发布-订阅更像交叉应用模式。

## 说说浏览器和 Node 事件循环的区别 
[https://github.com/Advanced-Frontend/Daily-Interview-Question/issues/26](https://github.com/Advanced-Frontend/Daily-Interview-Question/issues/26)
```js
// 例子说明
function test () {
   console.log('start')
    setTimeout(() => {
        console.log('children2')
        Promise.resolve().then(() => {console.log('children2-1')})
    }, 0)
    setTimeout(() => {
        console.log('children3')
        Promise.resolve().then(() => {console.log('children3-1')})
    }, 0)
    Promise.resolve().then(() => {console.log('children1')})
    console.log('end') 
}

test()

// 以上代码在node11以下版本的执行结果(先执行所有的宏任务，再执行微任务)
// start
// end
// children1
// children2
// children3
// children2-1
// children3-1

// 以上代码在node11及浏览器的执行结果(顺序执行宏任务和微任务)
// start
// end
// children1
// children2
// children2-1
// children3
// children3-1
```

## 介绍模块化发展历程
[https://github.com/Advanced-Frontend/Daily-Interview-Question/issues/28](https://github.com/Advanced-Frontend/Daily-Interview-Question/issues/28)

## 浏览器缓存读取规则
[https://www.jianshu.com/p/54cc04190252](https://www.jianshu.com/p/54cc04190252)

