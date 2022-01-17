<template>
  <Nav />

  <div class="container mt-4">
    <h5>React 개발자의 블로그입니다</h5>
    <p>- Vue로 만들었음 -</p>
  </div>

  <List :item="item"/>
</template>

<script>
import Nav from '@/components/Nav';
import List from '@/components/List';
import item from './assets/blog.js';

export default {
  name: 'App',
  data() {
    return {
      item : item,
    }
  },
  components: {
    Nav,
    List,
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  /*margin-top: 60px;*/
}
</style>
