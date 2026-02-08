<script setup>
/**
 * 자식 컴포넌트: defineProps로 부모가 넘긴 값 받기
 * - defineProps(['title', 'mainCont']) → props.title, props.mainCont 사용
 */
import { onMounted, ref } from 'vue'

const props = defineProps(['title', 'mainCont'])
const title = ref('')
const cont = ref('')

// onMounted: 컴포넌트가 DOM에 붙은 뒤 한 번 실행. 여기서 props를 로컬 state에 복사
onMounted(() => {
  title.value = props.title
  cont.value = props.mainCont
})
</script>

<template>
  <h1>title : {{ title }}</h1>
  <p>cont: {{ cont }}</p>
</template>
