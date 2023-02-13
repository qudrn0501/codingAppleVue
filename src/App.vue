<template>

  <!-- 이벤트 핸들러 -->
  <div class="menu">
    <a v-for="a in 메뉴들" :key="a">{{ a }}</a> 
  </div>

  <div>
    <h4>{{ products[0] }}</h4>
    <P>40 만원</P>
    <button @click="increase(0)">허위매물신고</button> 
    <span>신고수 : {{ 신고수[0] }}</span>
    <!-- v-on:click == @click -->
  </div>
  <div>
    <h4>{{ products[1] }}</h4>
    <P>50 만원</P>
    <button @click="increase(1)">허위매물신고</button> 
    <span>신고수 : {{ 신고수[1] }}</span>
  </div>
  <div>
    <h4>{{ products[2] }}</h4>
    <P>60 만원</P>
    <button @click="increase(2)">허위매물신고</button> 
    <span>신고수 : {{ 신고수[2] }}</span>
  </div>
</template>

<script>
export default {
  name: 'App',
  data(){ 
    return {
      메뉴들 : ['Home', 'Shop', 'About'],
      products : ['역삼동원룸', '천호동원룸', '마포구원룸'],
      신고수 : [0, 0, 0],
      // (숙제) 모든 상품에 신고수 버튼 만들어오기
    }
  },
  methods: {
    // 함수를 만드는 공간
    increase(i) {
      this.신고수[i] += 1;
      // methods에서 직접 data를 가져올 수 없으므로
      // this.data명 방식으로 입력해야한다.
    }
  },
  components: {
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
</style>
