<template>
  <!-- 모달창이 안뜬 이유 : {{ 데이터바인딩은 밑에 데이터가 있어야 가능함 }} -->
  <div class="black-bg" v-if="모달창열렸니 == true">
    <div class="white-bg">
      <img :src="원룸들[누른거].image" class="room-img">
      <h4>{{ 원룸들[누른거].title }}</h4>
      <p>{{ 원룸들[누른거].content }}</p>
      <p>{{ 원룸들[누른거].price }}</p>
      <!-- <button @click="모달창열렸니 = false">닫기</button> -->
      <!-- (주의) props는 read-only이므로 받아온거 수정하면 큰일남 -->
    </div>
  </div>
</template>

<script>
export default {
  name: 'Modal',
  // 2. 자식은 props로 받은거 등록
  // props: {데이터이름:자료형이름}
  // 자료형이름은 받아온 데이터의 자료형을 대문자로 쓴다
  props: {
    원룸들 : Array,
    누른거 : Number,
    모달창열렸니 : Boolean,
  },
  // 애초에 자식한테 데이터 만들면 되잖?
  // -> 되긴하는데 부모도 쓰는 데이터라면 부모한테 만들어두셈(자식이 부모한테 주는건 어렵)
}
</script>

<style>

</style>