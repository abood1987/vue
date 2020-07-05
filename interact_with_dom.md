## start

```javascript
new Vue({ // Vue instance
	el: '#app', // Html element, connect with Vie instance (root element)
  data: {
  	title: 'Hello World!',
	name: '',
    link: 'http://google.com',
    finishedLink: '<a href="http://google.com">Google</a>'
  },
  methods: {
  	sayHello: function() {
    	this.title = 'Hello!';
    	return this.title;
    }
  }
});
```

```html
<div id="app">
  <h1 v-once>{{ title }}</h1>
  <p>{{ sayHello() }} - <a v-bind:href="link">Google</a></p>
  <hr>
  <p v-html="finishedLink"></p>
  <input type="text" v-model="name">
  <button v-on:click="increase(2, $event)">Click me</button>

</div>
```
* v-one: عند إضافتها يأخذ العنصر القيمةالمبدأية ولايقوم بتحديثها
* v-bind: ربط خاصية html مع متغير (data, method, computed)
* v-html: لإضافة عنصر html
* v-on: للربط مع حدث
* model: ربط مع متغير بحيث يقوم بالتحديث وإظهار القيمة

```javascript
new Vue({
	el: '#app',
  data: {counter: 0},
  computed: {
  	output: function() {
	return this.counter >;
	}
  },
  watch: {
  	counter: function(value) {}
  },
  methods: {}
  }
```

* computed: تتغير عند تغيير المتغير ضمنها فقط على عكس الدوال التي تنفذ عند تغيير اي قيمة
* watch: تتغير عند تغيير المتغير فقط ولكن يمكن إضافة عمليات غير متزامنة على عكس المحسوبة


## style

```htm
:class="{red: attachRed}" // red = class & attachRed = boolian prop & color = class
:class="[color, {red: attachRed}]"
```

عند ربط الصنف مع متغير منطقي يتم تفعيل الصنف عند تفعيل المتغير

```html
:style="[myStyle, {height: width + 'px'}]"
```

```javascript
data: {
  	color: 'gray',
    width: 100
  },
  computed: {
  	myStyle: function() {
    	return {
      	backgroundColor: this.color,
        width: this.width + 'px'
      };
    }
  }
```

##  Conditionals and Rendering Lists 
```html
<template v-if="isTrue"></template>
<template v-else></template>

<template v-show></template>

<template v-for="(item, index) in object" :key="index"></template>
```

* v-if: تحذف العنصر من الدوم
* v-show: إخفاء العنصر

