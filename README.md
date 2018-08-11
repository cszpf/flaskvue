# 如何采用flask+vue.js构建一个全栈demo系统
参考网址https://juejin.im/post/5ab0a21df265da23a228efd3
1. npm install -g vue-cli
2. cd flaskvue
3. vue init webpack frontend
4. cd frontend
5. npm install
6. npm run dev
7. cd frontend /src/components
	- vi Home.vue:
	<template>
	<div>
	<p>Home page</p>
	</div>
	</template>
	- vi about.vue:
	<template>
	<div>
	<p>About</p>
	</div>
	</template>
8. cd frontend /src/router
	- vi index.js:
	import Vue from 'vue'
	import Router from 'vue-router'
	const routerOptions = [
	{ path: '/', component: 'Home' },
	{ path: '/about', component: 'About' }
	]

	const routes = routerOptions.map(route => {
	return {
	...route,
	component: () => import(`@/components/${route.component}.vue`)
	}

	})

	Vue.use(Router)
	export default new Router({
	routes,
	mode: 'history'
	})

# 其实最重要的是对过程的总结，而不是一个具体的做法。示例是无穷尽的，最主要的是从无到有的思维过程