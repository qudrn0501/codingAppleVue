<template>
  <div class="black-bg" v-if="모달창열렸니 == true">
    <div class="white-bg">
      <img :src="원룸들[누른거].image" class="room-img">
      <h4>{{ 원룸들[누른거].title }}</h4>
      <p>{{ 원룸들[누른거].content }}</p>
      <!-- 유저가 <input>에 입력한 값을 데이터로 저장하는 법 -->
      <!-- 1. @input : 입력할 때마다 뭐 실행해주셈 
      <input type="text" @input="month = $event.target.value"> -->

      <!-- 2. v-model="입력할데이터" -->
      <input type="text" v-model.number="month"> 
      <!-- $event는 addEventListener에 쓰는 e라는 파라미터랑 같음 -->
      <!-- 사용자가 입력한 값을 month에 저장 
      v-model.number를 해야 숫자로 바꿔주어 제대로 된 숫자 더하기가 된다.-->
      <p> {{ month }}개월 선택함 : {{ 원룸들[누른거].price * month }} 원</p>

      <button @click="close">닫기</button>
    </div>
  </div>
</template>
<!-- (숙제) 모달창 닫기 버튼 다시 만들어오기 -->
<script>
export default {
  name: 'Modal',
  data() {
    return {
      month : 1, // 초기값 자료형이 중요함. 인풋에 한글을 아무리 써봐야 안들어감
      // 그러나 출력되는 것은 전부 문자자료형임. 곱셈이 되는 이유는 js는 문자도 곱셈이 된다.
    }
  },
  props: {
    원룸들 : Array,
    누른거 : Number,
    모달창열렸니 : Boolean,
  },
  methods: {
    close(){
      this.$emit('closeModal', this.모달창열렸니)
    }
  }
}
</script>

<style>

</style>