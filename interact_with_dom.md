## start

```javascript
new Vue({ // Vue instance
	el: '#app', // Html element, connect with Vie instance (root element)
  data: {
  	title: 'Hello World!',
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

´´´html
<pre>
<div id="app">
  <h1 v-once>{{ title }}</h1>
  <p>{{ sayHello() }} - <a v-bind:href="link">Google</a></p>
  <hr>
  <p v-html="finishedLink"></p>
</div>
</pre>
´´´
