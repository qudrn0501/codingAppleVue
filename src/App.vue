<template>

  <!-- 반복문 -->
  <div class="menu">
    <!-- <v-for="작명" in 횟수" :key="작명">{{ 작명 }} , 키 안쓰면 에러남, 작명은 아무렇게나 가능 -->
    <a v-for="a in 메뉴들" :key="a">{{ a }}</a> 
    <!--    <a v-for="(a, i) in 메뉴들" :key="i">{{ a }}</a>    
            (a,i) a는 array 데이터, i는 0부터 1씩 증가하는 정수  -->
    <!-- array/object 넣으면 그 자료 안의 데이터 갯수만큼 반복 -->
  </div>

  <!-- (숙제) 상품 목록도 반복문으로 축약해보셈 -->
  <!-- 가격은 대충 신경쓰지 맙시다 제목만 잘뜨면 됨 -->
  <div>
    <h4>{{ products[0] }}</h4>
    <P>40 만원</P>
  </div>
  <div>
    <h4>{{ products[1] }}</h4>
    <P>50 만원</P>
  </div>
  <div>
    <h4>{{ products[2] }}</h4>
    <P>60 만원</P>
  </div>
</template>

<script>
export default {
  name: 'App',
  data(){ 
    return {
      메뉴들 : ['Home', 'Shop', 'About'],
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
