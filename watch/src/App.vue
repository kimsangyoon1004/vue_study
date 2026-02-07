<script setup>
import { ref, reactive, watch } from 'vue';

const cnt = ref(1)
const obj = reactive({oldV: null, newV:null})
const counter = () => cnt.value++

watch(cnt, (newValue, oldValue) => {
  obj.oldV = oldValue;
  obj.newV = newValue;
})
</script>

<template>
  <p>cnt: {{ cnt }}</p>
  <p>old: {{ obj.oldV }} / new: {{ obj.newV }}</p>
  <button @click="counter">클릭</button>
</template>

<style scoped></style>
