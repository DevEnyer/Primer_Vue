<script setup> 

const condition = true

</script>

<template>

    <h1>Directiva v-if en Vue</h1>
    <!-- De esta manera se usar la directiva V-if-->
    <h2 v-if="condition">Se cumple la condicion</h2>
    <h2 v-else>No se cumple la condicion</h2>

</template>

<style scoped></style>