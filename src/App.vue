<script setup>
import { ref, watch, onMounted } from 'vue'
import TodoForm from './components/TodoForm.vue'
import TodoList from './components/TodoList.vue'

const tareas = ref([])

// Lógica de Persistencia (Igual que antes)
onMounted(() => {
  const saved = localStorage.getItem('mis_tareas')
  if (saved) tareas.value = JSON.parse(saved)
})

watch(
  tareas,
  (val) => {
    localStorage.setItem('mis_tareas', JSON.stringify(val))
  },
  { deep: true },
)

// --- MÉTODOS QUE MANIPULAN EL ESTADO ---

const agregarTarea = (texto) => {
  tareas.value.push({ texto, completada: false })
}

const borrarTarea = (index) => {
  tareas.value.splice(index, 1)
}

const alternarTarea = (index) => {
  tareas.value[index].completada = !tareas.value[index].completada
}
</script>

<template>
  <div class="main-app">
    <h1>Gestor de Tareas Componentizado</h1>

    <TodoForm @add-tarea="agregarTarea" />

    <TodoList :tareas="tareas" @delete-tarea="borrarTarea" @toggle-tarea="alternarTarea" />
  </div>
</template>

<style>
.main-app {
  max-width: 500px;
  margin: 2rem auto;
  font-family: sans-serif;
}
</style>
