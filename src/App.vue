<template>

  <!-- 모달창 만들기 -->
  <!-- 동적인 UI 만드는 법
  1. UI의 현재 상태를 데이터로 저장해둠
  2. 데이터에 따라 UI가 어떻게 보일지 작성 -->
  <!-- v-if="조건식" : 조건식이 참일때만 html 보여줌 -->
  <!-- (숙제) 모달창 닫기버튼과 기능 만들어오셈 -->
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

  <div>
    <img src="./assets/room0.jpg" alt="room0" class="room-img">
    <h4 @click="모달창열렸니 = true">{{ products[0] }}</h4>
    <P>40 만원</P>
    <button @click="increase(0)">허위매물신고</button> 
    <span>신고수 : {{ 신고수[0] }}</span>
  </div>
  <div>
    <img src="./assets/room1.jpg" alt="room1" class="room-img">
    <h4 @click="모달창열렸니 = true">{{ products[1] }}</h4>
    <P>50 만원</P>
    <button @click="increase(1)">허위매물신고</button> 
    <span>신고수 : {{ 신고수[1] }}</span>
  </div>
  <div>
    <img src="./assets/room2.jpg" alt="room2" class="room-img">
    <h4 @click="모달창열렸니 = true">{{ products[2] }}</h4>
    <P>60 만원</P>
    <button @click="increase(2)">허위매물신고</button> 
    <span>신고수 : {{ 신고수[2] }}</span>
  </div>
</template>

<script>
export default {
  name: 'App',
  data(){ // react에서는 state라고 함 (ui의 상태를 저장하는 곳)
    return {
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
