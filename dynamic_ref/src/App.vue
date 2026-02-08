<script setup>
/**
 * v-bind (: ) 로 class 동적 바인딩
 * - :class="변수" → 변수 값이 그대로 class 이름이 됨
 * - data가 바뀌면 적용되는 class도 바뀜 (동적 스타일)
 */
import { ref } from 'vue'

const titleClass = ref('')

const good = () => {
  titleClass.value = 'title'
}
</script>

<template>
  <!-- :class="titleClass" : titleClass 값이 '' 이면 class 없음, 'title'이면 .title 스타일 적용 -->
  <h1 :class="titleClass">빨갛게 만들기</h1>
  <button @click="good">클릭</button>
</template>

<style scoped>
.title {
  color: red;
}
</style>
