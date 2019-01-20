- DOM结构(加上" "会在形成1.1,1.2的结构
1. React项目结构解析
2. 组件
3. props
4. state
5. 虚拟dom diff算法

---
####什么时候创建虚拟DOM(老的)
- 浏览器刚刚加载页面的时候
- js对内容进行操作的时候，会生成另外一个虚拟DOM（新的）,最终拿着数据去进行比较，实现类似局部刷新的效果。多次虚拟dom操作，但是在真实的dom中它只会执行一次dom操作.

>比如color的多次赋值,取得是最终的值并且去进行渲染的操作,diff算法简介.

>组件生命周期
componentwillupdate/unmont/update/receivePros


- react性能为什么比Js高。
react摒弃了js原先的部分设计，采用了一些新的具有优化的设计.  

> tips:无论你的组件声明为函数还是类，他都不能修改props.(最好都不要去修改属性props)

```
#箭头函数# 不会绑定作用域，this会绑定当前的作用域.

比如一个function(){
  this 访问不到外界，因为有作用域的存在，但是+了=>函数之后，就可以忽略掉作用域，这样就能访问到外界的数据了.
}

```

关于关键字state，和props是一样的，就是组件中拥有的属性。
不变props,可变state.



---
关于React-Native的环境目录：


```
React刷新的时候只会对局部的区域进行刷新，但是js的话就会进行全局的刷新.
react在dom产生的初期就会预制一个dom树，如果对其进行多次赋值的话，最终进行渲染的就是最终的一个diff之后的结果。


*关于变量
var 太过于灵活，可以定义相同的名称的变量。
let 不可以定义相同名称的变量，比如 let a,leta,这样是不允许的。
const 定义的是只读属性的变量，注意，是变量。但是他是只读属性的。


>虚拟Dom
what's virtual dom?
VirtualDOM是一个能够直接描述一段ＨＴＭＬ　ＤＯＭ结构的Ｊａｖａｓｃｒｉｐｔ对象，浏览器可以根据其结构按照一定规则创建出确定唯一的ＨＴＭＬ　ＤＯＭ结构

1. 浏览器就在页面的时候，react会根据内容先生成一个虚拟的DOM(老的）,js在堆内容进行操作的时候，又会生成另外一个虚拟的DOM(新的），但是只是进行比较，最终渲染的还是新旧dom进行差分算法得到的结果。
2. 在用标准的DOM创建的时候，会自动继承大量的属性和方法，但是虚拟dom则会少很多很多。

例如：
---
另外举个例子：
var A=document.getElementById('test');
 A.style.backgroundColor = "black";
 A.style.backgroundColor = "red";
 A.style.backgroundColor = "black";

```

## ---  以上是diff算法


比如比较123和12，这样好比较。
但是一旦顺序乱了就不行了。

所以可以定义<div key="0">，用key值去进行节点的唯一性的标记。



es6 的方式来定义一个组件。
这样的话就能将控件封装起来。

class Person extends React.Component{
      render(){
         return <h1>Hello,{props.name}</h1>
     }
}


##渲染 ReactDom.render()，渲染。

标签可以用元素的方式进行定义.
let   

---

React 遇到标签中的大写的元素的时候就会去调用组件中元素的方法.


>组件可以是元素，也可以是类。但是要注意的是不能修改props.
那我要修改props怎么办？通过state去进行修改。



为什么不能去掉().
箭头函数的特性：指向的是一个函数。

加入了箭头函数之后可以忽略作用域，直接调用到外面的方法。
()=>  箭头函数，不会指定作用域，this会绑定当前的作用域.

react 生命周期
获取外部数据并且挂在到组件上，只能在组件已经挂在到**真实的网页**上才能去进行渲染.

1. componentWillMount() 是在组件完全挂载到网页上的时候才会调用被执行，所以可以保证数据的加载。
此外，在这方法里面的调用setState()方法，会
2. render() 进行正式的渲染
3. componentDisMount() 组件被完全挂载到网页上的时候才会调用被执行，可以保证数据的加载。
而且在这个方法调用setState()，会触发重新渲染，所以被设计用来处理加载外部的数据或者处理其他副作用的代码.
4. construtor 组件准备挂载的开始，但是尚未挂载到网页上
5. componentWillMount()是在constructor之后render之前，但是在这个方法里面的setState（）不会触发重新渲染，所以一般不用用来加载数据，也很少被用到。

特别注意！！！
//遇到标签以及大写字母开头，则表示要去请求组件(函数），所以定义组件的时候，一定一定要记得用大写字母开头.
html的dom标签： let ele = <Person name = "this is River"/>