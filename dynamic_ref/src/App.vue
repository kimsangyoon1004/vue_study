<script setup>
import { ref } from 'vue'

const titleClass = ref('');

const good = () => {
  titleClass.value = 'title'
}
</script>

<template>
  <h1 :class ="titleClass"> 빨갛게 만들기 </h1>
  <button @click="good"> 클릭 </button>
</template>

<style scoped>
.title {color:red}
</style>
