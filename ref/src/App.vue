<script setup>
/**
 * Composition API - ref, reactive, computed 연습
 * <script setup> 안에서는 반응형을 ref(), reactive()로 만듦
 */
import { ref, computed, reactive } from 'vue'

// ref(0): 숫자·문자열 같은 기본형 반응형. template에서는 .value 없이 씀
const cnt = ref(0)
// computed: 다른 반응형 값으로부터 계산된 값. cnt가 바뀌면 자동으로 다시 계산
const oddEven = computed(() => (cnt.value % 2 ? '홀수' : '짝수'))
const counter = () => cnt.value++

// reactive(): 객체 전체를 반응형으로. 속성은 .value 없이 obj1.name 처럼 접근
const obj1 = reactive({
  name: 'kim',
  age: 33,
})

const good = () => {
  cnt.value++
  obj1.name = 'lee'
}
</script>

<template>
  <p>{{ cnt }}</p>
  <p>홀짝 판별 : {{ oddEven }}</p>
  <button @click="counter">버튼 클릭</button>
  <p>obj1 : {{ obj1.name }} / {{ obj1.age }}</p>
  <button @click="good">카운터 클릭</button>
</template>

<style scoped></style>
