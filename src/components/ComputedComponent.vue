<script setup>
import { computed, ref } from 'vue';

const userName = ref('Juan');
const numberName = computed(() => {
  return userName.value.length;
})
</script>

<template>

    <input type="text" v-model="userName">
    <p>Nombre: {{ userName }}</p>
    <p>Longitud del nombre: {{ numberName }}</p>

</template>

<style scoped>
</style>