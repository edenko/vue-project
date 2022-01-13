<template>
  <Nav/>

<!--  <div class="start" :class="{ end : modalFlag }">-->
<!--    <Modal :modalFlag="modalFlag" :roomNum="roomNum" :rooms="rooms" @closeModal="modalFlag = false"/>-->
<!--  </div>-->
  <transition name="fade">
    <Modal :modalFlag="modalFlag" :roomNum="roomNum" :rooms="rooms" @closeModal="modalFlag = false"/>
  </transition>

  <Discount v-if="showDiscount == true" />

  <button @click="priceSort">가격순정렬</button>
  <button @click="titleSort">가나다정렬</button>
  <button @click="sortBack">되돌리기</button>

  <Card @click="modalFlag = true; roomNum = i;" :rooms="rooms[i]" v-for="(item, i) in rooms" :key="item"/>
</template>

<script>
import {rooms} from './assets/dto/rooms.js';
import Nav from "@/components/Nav";
import Modal from "@/components/Modal";
import Discount from "@/components/Discount";
import Card from "@/components/Card";

export default {
  name: 'App',
  data() {
    return {
      showDiscount : true,
      modalFlag : false,
      originRooms : [...rooms],
      rooms : rooms,
      roomNum : 0,
      products : [
        { local : '역삼동원룸', price: 60 },
        { local : '천호동원룸', price: 50 },
        { local : '마포구원룸', price: 70 },
      ],
      count : [0, 0, 0],
      colorBlue : 'color: blue',
    }
  },
  methods : {
    // increase(i) {
    //   this.count[i]++;
    // }
    priceSort(){
      this.rooms.sort(function(a, b){
        return a.price - b.price;
      })
    },
    titleSort(){
      this.rooms.sort(function(a, b){
        return a.title < b.title ? -1 : a.title > b.title ? 1 : 0;
      })
    },
    sortBack(){
      this.rooms = [...this.originRooms];
    }
  },
  // mounted(){
  //   setTimeout(() => {
  //     this.showDiscount = false;
  //   }, 2000);
  // },
  components: {
    Nav,
    Modal,
    Discount,
    Card,
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
  margin-top: 60px;
}
body {
  margin : 0;
}
div {
  box-sizing: border-box;
}
.black-bg {
  width: 100%; height:100%;
  background: rgba(0,0,0,0.5);
  position: fixed;
  padding: 20px 200px;
}
.white-bg {
  width: 100%; background: white;
  border-radius: 8px;
  padding: 20px;
}
.start {
  opacity: 0;
  transition: all 0.5s;
}
.end {
  opacity: 1;
}
.fade-enter-from {
  transform: translateY(-1000px);
}
.fade-enter-active {
  transition: all 0.5s;
}
.fade-enter-to {
  transform: translateY(0px);
}
.fade-leave-from {
  opacity: 1;
}
.fade-leave-active {
  transition: all 0.5s;
}
.fade-leave-to {
  opacity: 0;
}
</style>
