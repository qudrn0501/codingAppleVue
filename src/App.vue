<template>
  <!-- 1. 밑에 데이터를 골라서 보내셈
  <자식 :작명="데이터" 
  :는 class처럼 기존 html에서 데이터 바인딩에도 쓰지만
  props를 전송할 때도 쓰인다. (정식 명칭은 v-bind:)-->
  <Modal :원룸들="원룸들" :누른거="누른거" :모달창열렸니="모달창열렸니" /> 

  <div class="menu">
    <a v-for="a in 메뉴들" :key="a">{{ a }}</a> 
  </div>

  <Discount />

  <Card v-for="(원룸, i) in 원룸들" :key="i" :원룸들="원룸들" :누른거="누른거" :모달창열렸니="모달창열렸니" />

</template>

<script>
import data from './assets/oneroom'
import Discount from './Discount.vue'
import Modal from './Modal.vue' 
import Card from './Card.vue' 

export default {
  name: 'App',
  data(){ 
    // 데이터는 App.vue 한 곳에 보관하고
    // 필요하면 가져다 씀(props)
    // 자식이 부모의 데이터를 가져가 쓰고 싶으면 props로 전송해야함
    return {
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
    // 용어정리 : 부모/자식 컴포넌트
    // App.vue는 부모, Modal.vue는 자식 컴포넌트
    // (숙제) 상품목록도 <Card/> 컴포넌트로 바꿔보셈 (props 직접 변경되는 것들은 지우든 하셈)
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
