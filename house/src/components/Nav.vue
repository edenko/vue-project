<template>
  <div class="menu">
    <a>Home</a>
    <a>Product</a>
    <a>About</a>
  </div>
</template>

<script>
export default {
  name: 'Nav',
}
</script>

<style>
.menu {
  background : darkslateblue;
  padding : 15px;
  border-radius : 5px;
}
.menu a {
  color : white;
  padding : 10px;
}
</style>