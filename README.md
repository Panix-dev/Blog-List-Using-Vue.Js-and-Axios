# Blog List Using Vue.js and Axios

> A simple example of combining Vue.js and Axios to retrieve and post blog data. 

A simple example of combining Vue.js and Axios to retrieve and post blog data from and to a 3rd party service provider. For the purposes of this experiment a fake online REST API for Testing and Prototyping has been used called "JSONPlaceholder" at jsonplaceholder.typicode.com


## Table of Contents


> Try `clicking` on each of the `anchor links` below so you can get redirected to the appropriate section.


- [JSONPlaceholder](#jsonplaceholder)
- [Created](#created)
- [Post](#post)
- [Contact Details](#contact-details)
- [Inspiration](#inspiration)


## JSONPlaceholder


Fake Online REST API for Testing and Prototyping 

- :link: [JSONPlaceholder](http://jsonplaceholder.typicode.com/)


## Created


> Show list of blog items on component's created() lifecycle hook


```javascript
created() {
	this.$http.get('http://jsonplaceholder.typicode.com/posts')
	.then(function(data) {
		this.blogs = data.body.slice(0,10);
	});
}
```


## Post


```javascript
methods: {
	post() {
		this.$http.post('http://jsonplaceholder.typicode.com/posts', {
			title: this.blog.title,
			body: this.blog.content,
			userId: 1
		}).then(function(data){
			console.log(data);
			this.submitted = true;
		});
	}
}
```


## Contact Details


> :computer: [https://pagapiou.com](https://pagapiou.com)

> :email: [hello@pagapiou.com](mailto:hello@pagapiou.com)

> :iphone: [LinkedIn](https://www.linkedin.com/in/agapiou/)

> :iphone: [Instagram](https://www.instagram.com/panos_agapiou/)

> :iphone: [Facebook](https://www.facebook.com/panagiotis.agapiou)


## Inspiration


- **[The Net Ninja](https://www.youtube.com/channel/UCW5YeuERMmlnqo4oq8vwUpg)**
