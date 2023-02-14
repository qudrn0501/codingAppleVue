<template>
  <div v-for="(원룸, i) in 원룸들" :key="i">
    <img :src="원룸들[i].image" class="room-img">
    <h4>{{ 원룸들[i].title }}</h4>
    <P>{{ 원룸들[i].price }}원</P>
  </div>
</template>

<script>
export default {
  name: 'Card',
  props: {
    원룸들 : Array,
    누른거 : Number,
    모달창열렸니 : Boolean,
  }
}
</script>

<style>

</style>