<script setup>
/**
 * defineProps: 부모 → 자식으로 데이터 전달 (props)
 * - 부모에서 :title="post.title" 처럼 넘기면, 자식에서 props.title 로 받음
 */
import ButtonCounter from './ButtonCounter.vue'

// 부모가 가진 데이터. 자식(ButtonCounter)에 :title, :mainCont 로 전달
const post = {
  id: 1,
  title: 'Hello World',
  mainCont: 'This is a test post',
}
</script>

<template>
  <h1>아래 있는 컴포넌트는 자식 컴포넌트</h1>
  <!-- :title, :mainCont : props 이름. 오른쪽은 부모 data -->
  <ButtonCounter :title="post.title" :mainCont="post.mainCont" />
</template>

