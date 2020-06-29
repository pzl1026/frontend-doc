## 实现原理

## diff算法

## fibber

## hook

## redux设计思想

## 为什么 Vuex 的 mutation 和 Redux 的 reducer 中不能做异步操作？
[答案Hiker9527]（https://github.com/Advanced-Frontend/Daily-Interview-Question/issues/65）


## React 中 setState 什么时候是同步的，什么时候是异步的？
> 在React中，如果是由React引发的事件处理（比如通过onClick引发的事件处理），调用setState不会同步更新this.state，除此之外的setState调用会同步执行this.state 。所谓“除此之外”，指的是绕过React通过addEventListener直接添加的事件处理函数，还有通过setTimeout/setInterval产生的异步调用。<br/>
> 原因： 在React的setState函数实现中，会根据一个变量isBatchingUpdates判断是直接更新this.state还是放到队列中回头再说，而isBatchingUpdates默认是false，也就表示setState会同步更新this.state，但是，有一个函数batchedUpdates，这个函数会把isBatchingUpdates修改为true，而当React在调用事件处理函数之前就会调用这个batchedUpdates，造成的后果，就是由React控制的事件处理过程setState不会同步更新this.state。<br/>
> 注意： setState的“异步”并不是说内部由异步代码实现，其实本身执行的过程和代码都是同步的，只是合成事件和钩子函数的调用顺序在更新之前，导致在合成事件和钩子函数中没法立马拿到更新后的值，形式了所谓的“异步”，当然可以通过第二个参数 setState(partialState, callback) 中的callback拿到更新后的结果。<br/>
>详细请看 [深入 setState 机制 ](https://github.com/sisterAn/blog/issues/26)

## 面试题汇总
> [35 道咱们必须要清楚的 React 面试题](https://juejin.im/post/5dc20a4ff265da4d4e30040b)<br>
> [关于React面试题汇总](https://juejin.im/post/5b2215f76fb9a00e8f795cd1)<br>
> [2019年17道高频React面试题及详解](https://juejin.im/post/5d5f44dae51d4561df7805b4)<br>