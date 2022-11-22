<template>
    <div>
        <h1> {{ title}}</h1>
        <h2> {{ Subtitle }}</h2>
    </div>
</template>

<script setup>
import { ref } from 'vue';
    
    const props = defineProps({
        title: String
    })

    const Subtitle = ref('This is static Data Subtitle using ref')

</script>

<style lang="scss" scoped>

</style>