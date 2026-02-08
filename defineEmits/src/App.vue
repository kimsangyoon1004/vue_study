<script setup>
import ChildComponent from './ChildComponent.vue';

const handleCustomEvent = (message) => {
  console.log(message)
}
</script>

<template>
  <ChildComponent @customEvents="handleCustomEvent" />
</template>

<style scoped></style>
