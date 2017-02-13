---
title: Vue-router - 前端控制路由、单页面应用
date: 2017-02-13 10:58:47
tags:
---

### 配置环境

前提
========

- node 
- npm
- vue
- webpack

webpack创建项目
========

``` 
$ vue init webpack my-project
$ cd my-project
$ npm install
$ npm run dev
```
vue-router安装
========
``` 
$ npm install vue-router
```

### vue-router

全局引入
============
``` javascript
// main.js
import Vue from 'vue'
import App from './App'
import router from './router'
// 全局引入router
new Vue({
  el: '#app',
  router,
  template: '<App/>',
  components: { App }
})
```
new Router()
========

``` javascript
// router/index.js
import Vue from 'vue'
import Router from 'vue-router'
// 引入页面
import Hello from 'components/Hello'  
import Table from 'components/Table'
import About from 'components/About'

Vue.use(Router)

export default new Router({
  routes: [
    {
      path: '/',
      name: 'Hello',
      component: Hello
    },
    {
      path: '/table',
      name: 'Table',
      component: Table
    },
    {
      path: '/about',
      name: 'About',
      component: About
    },
  ]
})
```

router-view
========
``` html
// app.vue
// router-view路由视图
<router-view></router-view>
```
router-link
========
``` html
// app.vue
// router-link链接路由
<router-link class="nav_li" to="/">Home</router-link>
<router-link class="nav_li" to="/table">Table</router-link>
<router-link class="nav_li" to="/about">About</router-link>
```

