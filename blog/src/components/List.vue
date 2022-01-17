<template>
  <div v-for="(item, i) in item" :key="i">
    <h5>{{ item.title }}</h5>
    <p>{{ item.date }}</p>
  </div>
</template>

<script>
// import item from '../assets/blog';

export default {
  name: 'List',
  data() {
    return {
      // item : item,
    }
  },
  props: {
    item : Array,
  }
}
</script>

<style>

</style>