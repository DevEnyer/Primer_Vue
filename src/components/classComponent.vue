<script setup>
import { ref } from 'vue'

const myCondition = ref(true)

const toggleCondition = () => {
    myCondition.value = !myCondition.value
    console.log(myCondition.value)
}

</script>

<template>
    <h1 :class="myCondition ? 'highlight' : 'red'">Condición para una clase dinámica</h1>
    <button @click="toggleCondition"> Cambiar condición </button>
</template>

<style scoped>
.highlight {
    color: red;
    background-color: yellow;
}
.red {
    color: red;
}
</style>
