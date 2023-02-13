<template>
  <!-- 꺽쇠 하나 열고 엔터치면 vue 파일 자동완성 -->
  <div class="discount">
    <h4>지금 결제하면 20% 할인</h4>
  </div>
</template>

<script>
export default {
  name: 'Discount',
  // (업데이트사항) 컴포넌트.vue 이름은 귀찮게 2단어 이상으로 작명해야합니다.
  // 안그러면 에러로 잡아줌. DiscountBanner.vue 이런 식으로 2단어로 작명 잘하면 됩니다.
  // 싫으면 package.json 파일 열어서 "rules"라는 항목에
  /*
  "rules": {
   "vue/multi-word-component-names": "off"
  } 
  */
  // 한줄 추가하고 미리보기 껐다가 다시 띄우면 됩니다.
}
</script>

<style>
  .discount {
    background: #eee;
    padding: 10px;
    margin: 10px;
    border-radius: 5px;
  }
</style>