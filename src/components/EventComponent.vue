<script setup>
import { ref } from 'vue';

let number = ref(0);
let inputNumber = ref(0);

//Creamos una funcion en donde se sume uno a una variable`
const addOne = ()=> {
    number.value++;
}

// Funcion para incrementar segun el numero que diga
const addNumber = (increment) => {
    inputNumber.value += increment;
}
</script>

<template>

    <p>Este es un evento donde al darle click aumenta en un el número {{ number }}</p>
    <button @click="addOne">Sumar 1</button>

    <!-- Cabe destacar que para hacer un evento se usa primero @ y despues el evento que se quiere realizar -->

    <p>Este es un evento donde al darle click aumenta el número con el valor del input {{ inputNumber }}</p>
    <input type="number" v-model.number="inputValue" placeholder="Ingresa un número" />
    <button @click="addNumber(inputValue)">Sumar número</button>

</template>

<style></style>