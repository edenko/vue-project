<template>
  <div>
    <img :src=rooms.image class="room-img">
    <h4 class="title">{{ rooms.title }}</h4>
    <p>{{ rooms.price }} 원</p>
  </div>
</template>

<script>
export default {
  name: 'Modal',
  props: {
    rooms : Object,
  },
}
</script>

<style>
.room-img {
  width: 50%;
  margin-top: 40px;
}
.title {
  cursor: pointer;
}
</style>