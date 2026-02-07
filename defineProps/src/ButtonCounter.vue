<script setup>
import { onMounted,ref } from 'vue';
const props = defineProps(['title', 'mainCont'])
const title = ref('')
const cont = ref('')

onMounted(() => {
    title.value = props.title
    cont.value = props.mainCont
})
</script>

<template>
    <h1> title : {{ title }} </h1>
    <p>  cont: {{ cont }}</p>
</template>
