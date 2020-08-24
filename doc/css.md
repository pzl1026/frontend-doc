## 介绍下 BFC 及其应用。
[答案](https://github.com/Advanced-Frontend/Daily-Interview-Question/issues/59)
<pre>
块级格式上下文
特征：
1.容器里面的元素不会影响到容器外面的元素，容器外的元素也不会影响到里面；
2.容器会一个挨着一个排列
3.计算BFC高度时，浮动元素也会参与计算
4.BFC区域不会与float box重叠

什么时候触发：
1.html跟元素
2.float
3.absolute
4.overflow不为visible，
5.table布局，flex布局

解决了什么问题：
1.解决了浮动，高度塌陷的问题
2.防止了同一BFC容器中相邻元素间的外边距重叠问题
3.实现自适应多栏布局
测试：https://github.com/pzl1026/frontend-test/blob/master/css/bfc.css
</pre>


## 垂直剧中几种实现方式
https://github.com/pzl1026/frontend-test/blob/master/css/center.css

## flex 有哪几种属性及其各种作用

## css选择器有哪些