# 概念

Vue.js 是一套构建用户界面的渐进式框架

Vue 只关注图层，采用**自底向上**增量开发的设计

Vue 的目标是通过尽可能简单的 API 实现响应的数据绑定和组合的视图组件。



# 使用

## 起步

1.每个Vue应用都需要通过实例化Vue来实现

```javascript
var vm = new Vue({
    
})
```



2.Vue构造器中有一个el参数，它是DOM元素中的id。

这意味着我们接下来的改动全部在以上指定的div内，div外部不受影响。



3.当一个Vue实例被创建时，它向Vue的响应式系统中加入了data对象中能找到的所有属性。

当这些属性的值发生改变时，html视图也会产生相应的变化。

另外 Vue实例提供的实例属性与方法，都有前缀$，以便与用户定义的属性区分开来。

```html
	<div id="vue_det">
		<h1>site : {{site}}</h1>
		<h1>url : {{url}}</h1>
		<h1>Alexa : {{alexa}}</h1>
	</div>
	<script type="text/javascript">
	// 我们的数据对象
	var data = { site: "菜鸟教程", url: "www.runoob.com", alexa: 10000}
	var vm = new Vue({
		el: '#vue_det',
		data: data
	})

	document.write(vm.$data === data) // true
	document.write("<br>") // true
	document.write(vm.$el === document.getElementById('vue_det')) // true
	</script>
```

## 模板语法

Vue.js 使用了基于HTML的模板语法，允许开发者**声明式**（坦白说我还没懂这个声明式是什么意思）地将DOM绑定至底层Vue实例的数据。

Vue.js 的核心是一个允许你采用简洁的模板语法来声明式的将数据渲染进 DOM 的系统。

结合响应系统，在应用状态改变时， Vue 能够智能地计算出重新渲染组件的最小代价并应用到 DOM 操作上。

### 插值

#### 文本

最常见的形式，使用{{...}}方式进行文本插值

#### html

V-html 输出 html代码

```html
<div id = 'app'>
		<div v-html = "message"/>
</div>
<script>
	new Vue({
		el : '#app',
		data : {
			message : '<h1>张致远的小站</h1>'
		}
	})
</script>
```

#### 属性

v-bind 主要用于属性绑定，根据boolean值判断是否使用该类

```html
<style>
.class1{
  background: #444;
  color: #eee;
}
</style>

<div id="app">
  <br><br>
  <div v-bind:class="{'class1': isClass1}">
    v-bind:class 指令
  </div>
</div>
	
<script>
new Vue({
	el: '#app',
  data:{
  	isClass1: true
  }
});
</script>
```



#### 指令

指令是指带有v-前缀的特殊属性

指令用于在表达式的值改变时，将某些行为用到DOM上

```html
<div id="app">
    <p v-if="seen">现在你看到我了</p>
    <p v-if="ok">学的不仅是技术，更是梦想！</p>
</div>
    
<script>
new Vue({
  el: '#app',
  data: {
    seen: true,
    ok: false
  }
})
</script>
```



#### 参数





