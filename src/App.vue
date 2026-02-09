<script setup>
import { ref } from 'vue'

// --- LÓGICA (JavaScript) ---

// Creamos una variable reactiva para el texto del input
const nuevaTarea = ref('')

// Creamos una lista reactiva de tareas
const tareas = ref([
  { texto: 'Aprender Vue 3', completada: false },
  { texto: 'Crear mi primer componente', completada: false },
])

// Función para añadir tareas
const agregarTarea = () => {
  if (nuevaTarea.value.trim() !== '') {
    tareas.value.push({
      texto: nuevaTarea.value,
      completada: false,
    })
    nuevaTarea.value = '' // Limpiamos el input
  }
}

// Función para eliminar una tarea
const eliminarTarea = (index) => {
  tareas.value.splice(index, 1)
}
</script>

<template>
  <div id="app-container">
    <h1>Mi Lista de Tareas</h1>

    <div class="input-group">
      <input v-model="nuevaTarea" @keyup.enter="agregarTarea" placeholder="¿Qué hay que hacer?" />
      <button @click="agregarTarea">Agregar</button>
    </div>

    <ul>
      <li v-for="(tarea, index) in tareas" :key="index">
        <span
          :class="{ completada: tarea.completada }"
          @click="tarea.completada = !tarea.completada"
        >
          {{ tarea.texto }}
        </span>
        <button @click="eliminarTarea(index)">x</button>
      </li>
    </ul>
  </div>
</template>

<style scoped>
/* --- ESTILOS (CSS) --- */
#app-container {
  font-family: Arial, sans-serif;
  max-width: 400px;
  margin: 50px auto;
  text-align: center;
}

.input-group {
  margin-bottom: 20px;
}

.completada {
  text-decoration: line-through;
  color: gray;
}

li {
  list-style: none;
  display: flex;
  justify-content: space-between;
  padding: 10px;
  border-bottom: 1px solid #eee;
  cursor: pointer;
}

button {
  margin-left: 10px;
  background-color: #ff4d4d;
  color: white;
  border: none;
  cursor: pointer;
  border-radius: 4px;
}
</style>
