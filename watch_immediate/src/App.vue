<script setup>
import { ref,  watch } from 'vue';

const count = ref(0)
const counter = () => count.value++
const obj = ref({name: "홍길동", age: 20})
const updateName =() => obj.value.name = "김길동"
watch(count, (newV, oldV) => {
  console.log(`${oldV} => ${newV}`)
}, { immediate: true })

watch(obj, (newobj) => {
  console.log(newobj.name)
}, { deep: true })
</script>

<template>
  <p>count: {{ count }}</p>
  <button @click="counter">클릭</button>

  <h1> Profile</h1>
  <p>name: {{ obj.name }}</p>
  <p>age: {{ obj.age }}</p>
  <button @click="updateName">이름 변경</button>
</template>

<style scoped></style>
