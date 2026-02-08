<script setup>
/**
 * defineEmits: 자식 → 부모로 이벤트 알리기
 * - 자식이 emit('customEvent', '메시지') 하면
 * - 부모의 @customEvent="handleCustomEvent" 가 실행되고, 인자로 메시지를 받음
 */
import ChildComponent from './ChildComponent.vue'

const handleCustomEvent = (message) => {
  console.log(message)
}
</script>

<template>
  <!-- @customEvent: 자식이 emit('customEvent', 인자) 할 때 부모에서 받는 이벤트 이름 -->
  <ChildComponent @customEvent="handleCustomEvent" />
</template>

<style scoped></style>
