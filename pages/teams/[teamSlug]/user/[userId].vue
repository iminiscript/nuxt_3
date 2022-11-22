<template>
    <div>
        <h1>
            I'm on team - {{ $route.params.teamSlug }}
        </h1>
        <h1>
            My user ID is {{ $route.params.userId }}
        </h1>
        <h2>{{ msz }}</h2>
    </div>
</template>

<script setup>
const route = useRoute();

const msz = computed(() => {
    return `I am on Team ${route.params.teamSlug} and my user ID is 
    ${route.params.userId}` 
})

</script>

<style lang="scss" scoped>

</style>