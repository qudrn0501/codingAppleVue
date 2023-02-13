<template>
  <!-- Component : 긴 html을 한 단어로 줄일 수 있는 문법 -->
  <Modal />
  <!-- 컴포넌트 만들면 데이터바인딩할 때 귀찮은 일이 생길 수 있음 -->

  <div class="menu">
    <a v-for="a in 메뉴들" :key="a">{{ a }}</a> 
  </div>

  <!-- 축약해둔 컴포넌트 쓰는법
  1. vue파일 import
  2. 등록하고
  3. 쓰셈 -->
  <Discount />
  <!-- 3. 쓰셈 -->
  <!-- 컴포넌트 쓰는 이유
  1. 아름다워
  2. 재사용쉬움 
  (반복적으로 출현할 부분만 컴포넌트화 권장, 코드가 필연적으로 복잡해짐) -->

  <div v-for="(원룸, i) in 원룸들" :key="i">
    <img :src="원룸들[i].image" class="room-img">
    <h4 @click="모달창열렸니 = true; 누른거 = i">{{ 원룸들[i].title }}</h4>
    <P>{{ 원룸들[i].price }}원</P>
  </div>
</template>

<script>
import data from './assets/oneroom'
import Discount from './Discount.vue' // 1. vue파일 import
import Modal from './Modal.vue' 

export default {
  name: 'App',
  data(){ 
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
    // 2. 등록하고
    Discount : Discount, // 왼쪽은 자유작명 : 오른쪽은 import한 이름
    //  Discount, es6 신문법, 하나만 해도 된다
    Modal,
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
