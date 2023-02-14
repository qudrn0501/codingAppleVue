<template>
  <!-- custom event : 부모데이터를 수정한다고 메시지를 보냄 -->
  <div>
    <img :src="원룸.image" class="room-img">
    <!-- <h4 @click="$emit('openModal', 원룸.id)">{{ 원룸.title }}</h4> -->
    <h4 @click="send">{{ 원룸.title }}</h4>
    <!-- $어쩌구는 vue만의 특별한 변수
    부모에게 메시지 보낼땐 $emit('작명', 데이터), 데이터는 안써도 됨 
    제목을 누르면 오픈모달이라는 이름으로 원룸.id 담아서 발사해주세요~ -->

    <P>{{ 원룸.price }}원</P>
  </div>
</template>

<script>
export default {
  name: 'Card',
  props: {
    원룸 : Array,
  },
  methods : {
    send(){
      this.$emit('openModal', this.원룸.id)
      // $emit()을 함수 안에서 하고 싶으면 this.$emit()
    }
  }
}
</script>

<style>

</style>