<template>
  <Modal @closeModal="모달창열렸니 = false" :원룸들="원룸들" :누른거="누른거" :모달창열렸니="모달창열렸니" /> 

  <div class="menu">
    <a v-for="a in 메뉴들" :key="a">{{ a }}</a> 
  </div>

  <Discount v-bind="오브젝트" /> 

  <Card @openModal="모달창열렸니 = true; 누른거 = $event" v-for="(원룸, i) in 원룸들" :key="i" :원룸="원룸들[i]" />
  <!-- 부모가 메시지 수신할 땐 @작명한거="" 
  자식이 보낸 데이터는 $event 변수에 담겨있음-->

</template>

<script>
import data from './assets/oneroom'
import Discount from './Discount.vue'
import Modal from './Modal.vue' 
import Card from './Card.vue' 

export default {
  name: 'App',
  data(){ 
    return {
      오브젝트 : { name : 'kim', age : 20},
      원룸들 : data,
      누른거 : 0,
      모달창열렸니: false,
      메뉴들 : ['Home', 'Shop', 'About'],
      products : ['역삼동원룸', '천호동원룸', '마포구원룸'],
      신고수 : [0, 0, 0],
    }
  },
  methods: {
    increase(i) {
      this.신고수[i] += 1;
    }
  },
  components: {
    Discount : Discount, 
    Modal,
    Card,
  }
}
</script>

<style>
body {
  margin: 0;
}
div {
  box-sizing: border-box;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.menu {
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}
.menu a {
  color: white;
  padding: 10px;
}
.room-img {
  width: 100%;
  margin-top: 40px;
}
.black-bg {
  width: 100%; height: 100%;
  background: rgba(0, 0, 0, 0.5);
  position: fixed;
  padding: 20px;
}
.white-bg {
  width: 100%;
  background: white;
  border-radius: 8px;
  padding: 20px;
}

</style>
