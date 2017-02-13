---
title: Vue - api入门
date: 2017-02-13 00:06:34
tags:
---


### 全局API

Vue.extend()
========
基础Vue构造器

```
<div id="element">{{ message }}</div>
```

```
var profile = Vue.extend({
	el: '#element'
	data: function(){
		return {
			message: 'hello world'
		}
	}
})
```

Vue.component()
========
注册或获取全局组件

```
<!-- 注册组件 -->
Vue.component{'my-component',Vue.extend({...})}
<!-- 获取组件 -->
var Component = Vue.component{'my-component'}
```

Vue.use()
========
安装Vue.js插件

```
<!-- 安装router插件 -->
Vue.use('router')
```

### 选项/数据

data
========
数据对象

```
<!-- 在Vue.extend实例中 data必须是函数 -->
var Component = Vue.extend({
	data: function(){
		return {
			a: 1,
		}
	}
})
```
props
========
传递父组件的数据，单项绑定

```
var Component = Vue.component('my-component',{
	props: {
		message: 'hello world'
	}
})
```
```
<my-component>{{ message }}</my-component>
```
methods
========
方法与事件处理
```
var vm = new Vue({
	data: {a: 1},
	methods: {
		add: function(){
			this.a++
		}
	}
})
vm.add();
vm.a // 2
```
el
========
挂载页面DOM元素

实例生命周期
========
| Vue2.0        | Description| 
| ------------- | ------------- | 
| beforeCreate  | 组件实例刚被创建，组件属性计算之前，如el属性等|
| created       | 组件实例创建完成，属性已绑定，DOM未生成|
| beforeMount   | 模板编译/挂载之前| 
| mounted       | 模板编译/挂载之后|
| beforeUpdate  | 组件更新之前| 
| updated       | 组件更新之后| 
| beforeDestory | 组件销毁前| 
| destoryed     | 组件销毁后| 

### 指令

v-show
========
根据表达式真假，切换元素的` display `
v-if
========
根据表达式的值的真假，决定是否渲染元素
v-for
========
根据数据渲染元素，语法` alias in expression `
v-on
========
绑定事件，缩写` @ `

``` html
<!-- 方法处理器 -->
<button v-on:click="doThis"></button>
<!-- 内联语句 -->
<button v-on:click="doThat('hello', $event)"></button>
<!-- 缩写 -->
<button @click="doThis"></button>
<!-- 停止冒泡 -->
<button @click.stop="doThis"></button>
<!-- 阻止默认行为 -->
<button @click.prevent="doThis"></button>
<!-- 阻止默认行为，没有表达式 -->
<form @submit.prevent></form>
<!--  串联修饰符 -->
<button @click.stop.prevent="doThis"></button>
<!-- 键修饰符，键别名 -->
<input @keyup.enter="onEnter">
<!-- 键修饰符，键代码 -->
<input @keyup.13="onEnter">
```

v-bind
========
绑定DOM属性，缩写` : `

v-model
========
表单数据绑定

* .lazy - 取代 input 监听 change 事件
* .number - 输入字符串转为数字
* .trim - 输入首尾空格过滤






