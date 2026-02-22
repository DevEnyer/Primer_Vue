<script setup>  
defineProps({
    msg: String,
    person : Object // Tambien se pueden pasar objectos
})
</script>

<template>

    <p >Dentro del hijo</p>
    <p>{{ msg }}</p>
    
    <div>
        <p>Esto viene de un objeto iterado con u v-for</p>
        <p v-for="(value, key) in person" :key="key">{{ key }}: {{ value }}</p>
    </div>

</template>

<style scoped>
</style>