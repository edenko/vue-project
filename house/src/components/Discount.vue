<template>
  <div class="discount">
    <h4>지금 결제하면 {{ percent }}% 할인</h4>
  </div>
</template>

<script>
export default {
  name: 'Discount',
  data() {
    return {
      percent : 20,
    }
  },
  mounted(){
    setInterval(() => {
      this.percent -= 1;
    }, 1000);
  },
}
</script>

<style>
.discount {
  background: #eee;
  padding: 10px;
  margin: 10px;
  border-radius: 5px;
}
</style>