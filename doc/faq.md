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

## react15与16的区别
>16新特性： render 支持返回数组和字符串 演示 <br>
>Error Boundary<br>
>createPortal<br>
>支持自定义 DOM 属性<br>
>Fiber<br>
>提升SSR渲染速度<br>
>减小文件体积<br>

## parseInt 与 Number区别
parseInt（string,radix）:将字符串解析转化为数字类型,返回的是整数；<br>
Number（object）:将对象的值转换为数字；

## proxy, reflect 与 object区别
>proxy,reflect为object提供了新的api，<br>
>proxy可以进行更多的拦截处理，高达13种，<br>
>reflect修改某些Object方法的返回结果，让其变得更合理；让Object操作都变成函数行为

## vue与react区别
> Vue 通过 getter/setter 以及一些函数的劫持，能精确知道数据变化，不需要特别的优化就能达到很好的性能<br>
> React 默认是通过比较引用的方式进行的，如果不优化（PureComponent/shouldComponentUpdate）可能导致大量不必要的VDOM的重新渲染<br>
> 数据流不同，vue1.0曾使用双向数据绑定<br>
> hoc与mixins，react曾使用mixins，现在转为高阶组件hoc<br>
> 模版渲染方式不同，vue使用的是html语法进行渲染，react使用的jsx<br>
> redux与vuex, Redux 使用的是不可变数据，而Vuex的数据是可变的。Redux每次都是用新的state替换旧的state，而Vuex是直接修改; Redux 在检测数据变化的时候，是通过 diff 的方式比较差异的，而Vuex其实和Vue的原理一样，是通过 getter/setter来比较的（如果看Vuex源码会知道，其实他内部直接创建一个Vue实例用来跟踪数据变化）

## array 与 set 区别
> 唯一性<br>
> 不可通过索引方式获取某个元素，比如let sets = new Set([5, 8, 10])； sets[0]<br>
> 还有一些操作方法不同，比如，has，add, size, clear, delete等<br>

## 观察者与发布订阅的区别
> 在观察者模式中，观察者是知道Subject的，Subject一直保持对观察者进行记录。然而，在发布订阅模式中，发布者和订阅者不知道对方的存在。它们只有通过消息代理进行通信。<br>
> 观察者模式大多数时候是同步的，比如当事件触发，Subject就会去调用观察者的方法。而发布-订阅模式大多数时候是异步的（使用消息队列）。

## 前端性能优化
> 减少http请求<br>
> 减少静态资源体积，比如使用构建工具使生产环境对静态资源进行压缩，<br>
> 使用缓存<br>
> 渲染层面，减少重排回流操作<br>
> 代码方面进行一定的性能优化<br>

## webpack优化
> alias对文件路径优化，加快webpack查找速度<br>
> publicpath如果可以使用cdn可以使用cdn,<br>
> 抽取css文件， MiniCssExtractPlugin<br>
> 代码分割按需加载、提取公共代码<br>
> 文件压缩<br>
> 暴露全局变量，比如使用的jq或者lodash、<br>
> css Tree Shaking, 清除无用的css<br>
> js Tree Shaking, 清除无用的js<br>
> DllPlugin插件打包第三方类库
> 使用happypack并发执行任务,多线程处理
> 生产环境pwa处理

## 深克隆
```js
/**
* deep clone
* @param  {[type]} parent object 需要进行克隆的对象
* @return {[type]}        深克隆后的对象
*/
const clone = parent => {
  // 维护两个储存循环引用的数组
  const parents = [];
  const children = [];

  const _clone = parent => {
    if (parent === null) return null;
    if (typeof parent !== 'object') return parent;

    let child, proto;

    if (isType(parent, 'Array')) {
      // 对数组做特殊处理
      child = [];
    } else if (isType(parent, 'RegExp')) {
      // 对正则对象做特殊处理
      child = new RegExp(parent.source, getRegExp(parent));
      if (parent.lastIndex) child.lastIndex = parent.lastIndex;
    } else if (isType(parent, 'Date')) {
      // 对Date对象做特殊处理
      child = new Date(parent.getTime());
    } else {
      // 处理对象原型
      proto = Object.getPrototypeOf(parent);
      // 利用Object.create切断原型链
      child = Object.create(proto);
    }

    // 处理循环引用
    const index = parents.indexOf(parent);

    if (index != -1) {
      // 如果父数组存在本对象,说明之前已经被引用过,直接返回此对象
      return children[index];
    }
    parents.push(parent);
    children.push(child);

    for (let i in parent) {
      // 递归
      child[i] = _clone(parent[i]);
    }

    return child;
  };
  return _clone(parent);
};
```



