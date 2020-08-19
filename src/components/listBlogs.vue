<template>
  <div id="show-blogs" v-theme:column="'narrow'">
    <h1>List Blog Titles</h1>
    <input type="text" v-model="search" placeholder="Search box" />
    <div class="single-blog" v-for="blog in filteredBlogs" v-bind:key="blog.id">
      <h2 v-rainbow>{{ blog.title | to-uppercase }}</h2>
    </div>
  </div>
</template>

<script>

import searchMixin from '../mixins/searchMixin';

export default {
  name: 'listBlogs',
  data() {
    return {
      blogs:[],
      search: '',
    }
  },
  methods: {

  },
  computed: {

  },
  created() {
    this.$http.get('http://jsonplaceholder.typicode.com/posts')
      .then(function(data) {
        this.blogs = data.body.slice(0,10);
      });
  },
  filters: {
    toUppercase(value) {
      return value.toUpperCase();
    }
  },
  directives: {
    'rainbow': {
      bind(el){
        el.style.color = "#" + Math.random().toString().slice(2,8);
      }
    }
  },
  mixins: [searchMixin]
}
</script>

<style>
#show-blogs{
    max-width: 800px;
    margin: 0px auto;
}
.single-blog{
    padding: 20px;
    margin: 20px 0;
    box-sizing: border-box;
    background: #eee;
}
</style>
