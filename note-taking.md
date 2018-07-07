## display: none;与visibility: hidden;的区别 ##

 - 联系：它们都能让元素不可见
 - 区别：

`display:none`;会让元素完全从渲染树中消失，渲染的时候不占据任何空间；

`visibility: hidden`;不会让元素从渲染树消失，渲染师元素继续占据空间，只是内容不可见

`display: none`;是非继承属性，子孙节点消失由于元素从渲染树消失造成，通过修改子孙节点属性无法显示；

`visibility: hidden`;是继承属性，子孙节点消失由于继承了hidden，通过设置`visibility: visible`;可以让子孙节点显式

修改常规流中元素的display通常会造成文档重排。

修改visibility属性只会造成本元素的重绘。

读屏器不会读取`display: none`;元素内容；会读取`visibility: hidden`;元素内容

link与@import的区别
---------------

 1. `link`是HTML方式， `@import`是CSS方式
 2. `link`最大限度支持并行下载，`@import`过多嵌套导致串行下载，出现FOUC
 3. link可以通过`rel="alternate stylesheet"`指定候选样式
 4. 浏览器对link支持早于`@import`，可以使用`@import`对老浏览器隐藏样式
 5. `@import`必须在样式规则之前，可以在css文件中引用其他文件
 总体来说：`link`优于`@import`
 
 
 ## `apply()`和`call()` ##
 每个函数都包含两个非继承而来的方法：`apply()`和`call()`。；

call与apply都属于Function.prototype的一个方法，所以每个function实例都有call、apply属性；

## 作用 ##

`call（）`方法和`apply（）`方法的作用相同：**改变this指向**。

## 区别 ##

他们的**区别**在于接收参数的方式不同：

`call（）`：第一个参数是this值没有变化，变化的是**其余参数都直接传递给函数**。在使用`call（）`方法时，**传递给函数的参数必须逐个列举出来**。

`apply（）`：传递给函数的是**参数数组**

如下代码做出解释：

```
function add(c, d){ 
	return this.a + this.b + c + d; 
} 
var o = {a:1, b:3}; 
add.call(o, 5, 7); // 1 + 3 + 5 + 7 = 16 
add.apply(o, [10, 20]); // 1 + 3 + 10 + 20 = 34 
```


