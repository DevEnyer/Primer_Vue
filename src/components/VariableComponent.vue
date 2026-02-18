<script setup>
import {ref} from 'vue';

let number = ref(0);

//Ahora toca mostrar como se usa el v-bind
const myID = "adkfjhaldskfjakjd";

const newID = ref("Algo nuevo");

setInterval(() => {
    number.value++;
}, 10000);
</script>

<template>

    <p>Este es un componente con variable creciente y reactiva</p>
    <br>
    <p>El número es el siguiente: {{ number }}</p>
    <br>
    <p v-bind:id="myID">Esto es solo una prueba</p> <!-- Esto se puede usar de esta manera -->
    <br>
    <p :id="myID">Este es otra prueba</p> <!-- Esto es otra manera de usar el v-bind, con los : -->
    <br>
    <input type="text" v-model="newID" /> <!-- Esto es para mostrar como se puede usar el v-model, el cual es una forma de hacer que el input sea reactivo -->
    <p>{{ newID }}</p>

</template>

<style scoped>
</style>