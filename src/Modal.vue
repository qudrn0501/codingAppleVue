<template>
  <div class="black-bg" v-if="모달창열렸니 == true">
    <div class="white-bg">
      <img :src="원룸들[누른거].image" class="room-img">
      <h4>{{ 원룸들[누른거].title }}</h4>
      <p>{{ 원룸들[누른거].content }}</p>
      <!-- watcher : data 감시하는 함수
      input에 문자입력하면 경고문을 띄우고 싶다 -->
      <input type="text" v-model.number="month">
      <!-- 
      <input type="range" min="1" max="12">
      이런 인풋으로 제한을 걸 수도 있긴 함
      -->
      <p> {{ month }}개월 선택함 : {{ 원룸들[누른거].price * month }} 원</p>

      <button @click="close">닫기</button>
    </div>
  </div>
</template>
<script>
export default {
  name: 'Modal',
  data() {
    return {
      month : 1, 
    }
  },
  watch: { // 데이터를 감시 watch: { 감시할데이터(){} } , 감시할데이터 이름은 실제 데이터 대상과 이름이 같음
    month(a){ // a라는 파라미터 (자유작명), 변경 후 month 데이터임, (a,b)이면 b는 변경 전 데이터
      // month라는 데이터가 변할 때마다 여기있는 코드가 실행됨
      // 사용자가 month를 글자로 입력하면 경고문 띄워주셈
      if (a >= 13) {
        alert('1년은 12달임 그 이상은 없음');
        this.month = 1;
        // (숙제) 글자 입력하면 alert띄우기, month값을 1로 되돌리기
      } else if (isNaN(a) == true) {
        alert('문자 입력 금지');
        this.month = 1;
      }
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