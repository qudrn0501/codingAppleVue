<template>
  <div class="black-bg" v-if="모달창열렸니 == true">
    <div class="white-bg">
      <img :src="원룸들[누른거].image" class="room-img">
      <h4>{{ 원룸들[누른거].title }}</h4>
      <p>{{ 원룸들[누른거].content }}</p>
      <p>{{ 원룸들[누른거].price }}</p>
      <button @click="close">닫기</button>
    </div>
  </div>
</template>
<!-- (숙제) 모달창 닫기 버튼 다시 만들어오기 -->
<script>
export default {
  name: 'Modal',
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