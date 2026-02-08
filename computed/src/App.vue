<script setup>
/**
 * computed: 다른 반응형 값으로부터 "계산된 값"을 만듦
 * - 의존하는 값(cnt)이 바뀔 때만 다시 계산되고, 결과는 캐시됨
 * - methods와 달리 의존성이 없으면 재계산 안 함 (성능 유리)
 */
import { ref, computed } from 'vue'

const cnt = ref(10)
// computed(함수): 함수 안에서 쓰인 반응형(cnt.value)이 바뀌면 자동으로 다시 계산
const oddEven = computed(() => (cnt.value % 2 ? '홀수' : '짝수'))

const counter = () => {
  cnt.value++
}
</script>

<template>
  <p>cnt: {{ cnt }}</p>
  <p>홀짝 판별 : {{ oddEven }}</p>
  <button @click="counter">클릭</button>
</template>

<style scoped></style>
