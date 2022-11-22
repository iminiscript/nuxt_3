<template>
    <div>
        <h1> {{ title}}</h1>
        <h2> {{ Subtitle }}</h2>
    </div>
</template>

<script setup>
    
    const props = defineProps({
        title: String
    })

    const Subtitle = ref('Please enter the Movie Title below in Input field')
    
</script>

<style scoped>

div {
    text-align: center;
}

</style>