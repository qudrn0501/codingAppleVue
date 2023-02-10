<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <div>
    <!-- {{ 데이터 바인딩 }} : JS 데이터를 HTML에 꽂아넣는 문법 -->
    원룸샵 <!-- 로고 같은 것은 바뀔 일이 거의 없으므로 데이터 바인딩 ㄴㄴ -->
    <h4 :style="스타일">XX 원룸</h4> <!-- 태그 안의 데이터 바인딩은 :속성="데이터" -->
    <P>{{ price1 }} 만원</P>
  </div>
  <div>
    <h4>XX 원룸</h4>
    <P>{{ price2 }} 만원</P>
  </div>
</template>

<!-- 숙제 : 원룸 이름만 데이터 바인딩해서 오기 -->
<script>
// 데이터 바인딩 이유 1 : html에 하드코딩하면 나중에 변경이 어려움
// 데이터 바인딩 이유 2 : vue의 실시간 자동 렌더링 쓰기 위함
export default {
  name: 'App',
  data(){ // 데이터 보관함
    return {
      // 여기에 모든 데이터를 보관함, object 자료로 저장
      // 자주 변경될 데이터들은 여기 저장해놨다가 {{}} 사용해서 넣기
      price1 : 60,
      price2 : 70,
      스타일 : 'color : blue',
      products : ['역삼동원룸', '천호동원룸', '마포구원룸'],
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
  margin-top: 60px;
}
</style>
