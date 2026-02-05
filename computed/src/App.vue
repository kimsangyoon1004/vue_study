<script setup>
import {ref, computed} from 'vue';
const cnt = ref(10);
const oddEven = computed( () => cnt.value % 2 ? '홀수' : '짝수');

const counter = () =>{
  cnt.value++;
}
</script>

<template>
  <p> cnt: {{ cnt }}</p>
  <p>홀짝 판별 : {{ oddEven }}</p>
  <button @click="counter"> 클릭 </button>
</template>

<style scoped></style>
