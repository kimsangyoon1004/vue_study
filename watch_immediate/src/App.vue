<script setup>
/**
 * watch 옵션: immediate, deep
 * - immediate: true → 마운트 직후에 한 번 바로 실행
 * - deep: true → 객체 안의 속성이 바뀌어도 감지 (ref로 감싼 객체일 때)
 */
import { ref, watch } from 'vue'

const count = ref(0)
const counter = () => count.value++
const obj = ref({ name: '홍길동', age: 20 })
const updateName = () => (obj.value.name = '김길동')

// immediate: true → 처음에도 한 번 실행 (0 => 0 같은 초기값으로)
watch(
  count,
  (newV, oldV) => {
    console.log(`${oldV} => ${newV}`)
  },
  { immediate: true }
)

// deep: true → obj.value.name 같은 내부 속성 변경도 감지
watch(
  obj,
  (newobj) => {
    console.log(newobj.name)
  },
  { deep: true }
)
</script>

<template>
  <p>count: {{ count }}</p>
  <button @click="counter">클릭</button>

  <h1>Profile</h1>
  <p>name: {{ obj.name }}</p>
  <p>age: {{ obj.age }}</p>
  <button @click="updateName">이름 변경</button>
</template>

<style scoped></style>
