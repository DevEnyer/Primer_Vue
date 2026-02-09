<script setup>
import { ref } from 'vue'

// Definimos los eventos que este componente puede disparar
const emit = defineEmits(['add-tarea'])

const nuevaTarea = ref('')

const enviarTarea = () => {
  if (nuevaTarea.value.trim()) {
    // Disparamos el evento y enviamos el dato como payload
    emit('add-tarea', nuevaTarea.value)
    nuevaTarea.value = ''
  }
}
</script>

<template>
  <div class="form-container">
    <input v-model="nuevaTarea" @keyup.enter="enviarTarea" placeholder="Nueva tarea..." />
    <button @click="enviarTarea">Agregar</button>
  </div>
</template>

<style scoped>
.form-container {
  display: flex;
  gap: 8px;
  margin-bottom: 20px;
}
input {
  flex-grow: 1;
  padding: 8px;
}
button {
  background: #42b883;
  color: white;
  border: none;
  padding: 8px 15px;
  cursor: pointer;
}
</style>
