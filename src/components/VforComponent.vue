<script setup>
const items = ['Manzana', 'Banana', 'Naranja', 'Pera']
</script>

<template>
    <h1>Directiva v-for en Vue | v-for </h1>
    <div>
        <p v-for="item in items" :key="item">{{ item }}</p>
    </div>
</template>

<style scoped>
h1 {
    font-size: 2em;
}
</style>