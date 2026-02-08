<script setup>
/**
 * watch: 특정 반응형 값이 바뀔 때마다 콜백 실행
 * - watch(감시할대상, (newValue, oldValue) => { ... })
 * - 값이 변경된 "후"에 실행됨
 */
import { ref, reactive, watch } from 'vue'

const cnt = ref(1)
const obj = reactive({ oldV: null, newV: null })
const counter = () => cnt.value++

// cnt가 바뀔 때마다 (newValue, oldValue) 콜백 실행
watch(cnt, (newValue, oldValue) => {
  obj.oldV = oldValue
  obj.newV = newValue
})
</script>

<template>
  <p>cnt: {{ cnt }}</p>
  <p>old: {{ obj.oldV }} / new: {{ obj.newV }}</p>
  <button @click="counter">클릭</button>
</template>

<style scoped></style>
