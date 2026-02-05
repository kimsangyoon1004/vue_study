<script setup>
import {ref, computed, reactive} from "vue";
const cnt = ref(0);
const oddEven = computed(() => (cnt.value % 2) ? '홀수' : '짝수');
const counter = () => cnt.value++;

const obj1 = reactive({
  name: "kim", age: 33
});

const good = () => {
  cnt.value++
  obj1.name = "lee"
}
</script>

<template>
  <p> {{ cnt }}</p>
  <p>홀짝 판별 : {{ oddEven }}</p>
  <button @click="counter">버튼 클릭</button>
  <p>obj1 : {{  obj1.name }} / {{ obj1.age }}</p>
  <button @click="good"> 카운터 클릭</button>
</template>

<style scoped></style>
