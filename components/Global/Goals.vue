<template>
    <div>
        <h1>{{ title }}</h1>
        <h2>{{ subTitle }}</h2>
    </div>
</template>

<script setup>
    const props = defineProps( {
        title: String,
        subTitle: String,
    })

</script>

<style lang="scss" scoped>

</style>