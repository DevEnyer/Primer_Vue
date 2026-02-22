<script setup>
import { ref } from 'vue';

const userName = ref('Adrian');
const emit = defineEmits(['login']); //Definitmos el evento

// Creamos la funcion que se ejecutará desde el hijo al padre
const login = () => {
    emit('login', userName.value); // Emitimos el evento con el valor del username
}

</script>

<template>

    <div class="child">
        <h2>Este es un componente hijo</h2>
        <p>Nombre de usuario: {{ userName }}</p>

        <button @click="login">login</button>
    </div>

</template>

<style scoped>
.child{
    border: 5px solid black;
}
</style>