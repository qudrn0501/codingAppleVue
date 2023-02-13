<template>
  <!-- v-if 문법 더 알아야할 내용
    v-if가 참이 아니면 v-else, v-else-if 실행
  <div v-if="1 == 2">안녕하세요</div>
  <div v-else-if="1 == 1">안녕하지 않아요</div> -->


  <!-- 모달창 내용 채우기 -->
  <!-- (숙제) 이미지, 상품설명, 가격 이런거 채워오셈 -->
  <div class="black-bg" v-if="모달창열렸니 == true">
    <div class="white-bg">
      <h4>{{ 원룸들[누른거].title }}</h4>
      <img :src="원룸들[누른거].image" class="room-img">
      <p>{{ 원룸들[누른거].content }}</p>
      <p>{{ 원룸들[누른거].price }}</p>
      <button @click="모달창열렸니 = false">닫기</button>
    </div>
  </div>

  <div class="menu">
    <a v-for="a in 메뉴들" :key="a">{{ a }}</a> 
  </div>

  <div v-for="(원룸, i) in 원룸들" :key="i">
    <img :src="원룸들[i].image" class="room-img">
    <h4 @click="모달창열렸니 = true; 누른거 = i">{{ 원룸들[i].title }}</h4>
    <P>{{ 원룸들[i].price }}원</P>
  </div>
</template>

<script>
import data from './assets/oneroom'

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
