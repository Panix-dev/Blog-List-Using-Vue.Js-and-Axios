<template>
  <div>
    <app-header></app-header>
    <router-view></router-view>
  </div>
</template>

<script>
import header from './components/header.vue';

export default {
  name: 'App',
  components: {
    'app-header': header
  },
  methods: {

  }
}
</script>

<style>
body {
  margin:0;
  font-family: 'Nunito SemiBold';
}
</style>
