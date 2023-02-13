<template>

  <!-- import export 쓰기 -->
  <div class="black-bg" v-if="모달창열렸니 == true">
    <div class="white-bg">
      <h4>상세페이지임</h4>
      <p>상세페이지 내용임</p>
      <button @click="모달창열렸니 = false">닫기</button>
    </div>
  </div>

  <div class="menu">
    <a v-for="a in 메뉴들" :key="a">{{ a }}</a> 
  </div>

  <!-- (숙제) 6개 상품 전부 알아서 진열해보셈 -->
  <div v-for="(원룸, i) in 원룸들" :key="i">
    <img :src="원룸들[i].image" class="room-img">
    <h4>{{ 원룸들[i].title }}</h4>
    <P>{{ 원룸들[i].price }}원</P>
  </div>
</template>

<script>
// import / export 문법 쓰는 법
// 1. export default 변수명
// 2. import 변수명 from 파일경로
import data from './assets/oneroom'
// import {apple, apple2} from './~~' 변수 두개 이상 받을때

export default {
  name: 'App',
  data(){ 
    return {
      원룸들 : data, // 받아온 데이터
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
