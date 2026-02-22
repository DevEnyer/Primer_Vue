<script setup>  

</script>

<template>

    <!-- Vamos con los slots personalizados -->
    <slot name="header">
        <h1>Este es el header del slot</h1>
    </slot>

    <!-- Slot general -->
    <h2>Componente con slots (bloques html desde el padre al hijo)</h2>
    <slot>
        <p>Este es el contenido por defecto del slot</p>
    </slot>

    <!-- Slot personalizado -->
    <slot name="footer">
        <p>Este es el footer del slot</p>
    </slot>


</template>

<style scoped>
</style>