<script setup>
/**
 * defineEmits: 이 컴포넌트가 부모에게 "이벤트"를 보낼 수 있게 선언
 * - emit('이벤트이름', 인자1, 인자2...) → 부모의 @이벤트이름="핸들러" 가 호출됨
 */
import { defineEmits } from 'vue'

const emit = defineEmits(['customEvent'])
const handleClick = () => {
  emit('customEvent', 'Button Clicked')
}
</script>

<template>
  <button @click="handleClick">Click me</button>
</template>