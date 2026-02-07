<script setup>
import ButtonCounter from './ButtonCounter.vue';

//const post = {
//  id: 1,
//  title: 'Hello World',
//  mainCont: 'This is a test post',
//} 

const props = defineProps({
  title: {
    type: String,
    required: true,
  },
  mainCont: {
    type: String,
    required: true,
  }
})
</script>

<template>
  <h1> 아래 있는 컴포넌트는 자식 컴포넌트</h1>
  <ButtonCounter :title="post.title" :mainCont="post.mainCont" />
</template>

