<script setup>  
defineProps({
    msg: String
})
</script>

<template>

    <p>Dentro del hijo</p>
    <p>{{ msg }}</p>

</template>

<style scoped>
</style>