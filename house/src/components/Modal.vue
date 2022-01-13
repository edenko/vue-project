<template>
  <div class="black-bg" v-if="modalFlag == true">
    <div class="white-bg">
      <img :src=rooms[roomNum].image class="room-img">
      <h4>{{ rooms[roomNum].title }}</h4>
      <p> {{ rooms[roomNum].content }}</p>
      <div>
<!--        <input @input="month = $event.target.value" />-->
        <input v-model.number="month"/>
<!--        <textarea v-model="month"></textarea>-->
      </div>
      <p>{{ month }}개월 : {{ (rooms[roomNum].price) * month }} 원</p>
      <button @click="close">닫기</button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Modal',
  data() {
    return {
      month: 1,
    }
  },
  // watch: {
  //   month(data) {
  //     if(data > 12) {
  //       alert('13일 이상은 안됨');
  //       this.month = 1;
  //     }else if(isNaN(data)) {
  //       alert('숫자만 입력하셈');
  //       this.month = 1;
  //     }
  //   },
  // },
  beforeUpdate() {
    if(this.month > 12) {
      alert('13일 이상은 안됨!');
      this.month = 1;
    }
  },
  props: {
    modalFlag : Boolean,
    rooms : Array,
    roomNum : Number,
  },
  methods: {
    close(){
      this.$emit('closeModal')
    }
  },
}
</script>

<style>

</style>