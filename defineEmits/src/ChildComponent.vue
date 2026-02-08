<script setup>
import { defineEmits } from 'vue';
const emit = defineEmits(['customEvent'])
const handleClick = () => {
    emit('customEvent', 'Button Clicked')
}
</script>

<template>
    <button @click = "handleClick">Click me</button>
</template>