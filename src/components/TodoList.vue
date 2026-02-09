<script setup>
// Recibimos la lista como Prop
defineProps(['tareas'])

// Definimos eventos para borrar o marcar como completada
const emit = defineEmits(['delete-tarea', 'toggle-tarea'])
</script>

<template>
  <ul>
    <li v-for="(tarea, index) in tareas" :key="index">
      <span :class="{ completada: tarea.completada }" @click="emit('toggle-tarea', index)">
        {{ tarea.texto }}
      </span>
      <button @click="emit('delete-tarea', index)">Eliminar</button>
    </li>
  </ul>
</template>

<style scoped>
.completada {
  text-decoration: line-through;
  color: #888;
}
li {
  display: flex;
  justify-content: space-between;
  padding: 10px;
  border-bottom: 1px solid #eee;
}
button {
  background: #ff4d4d;
  color: white;
  border: none;
  cursor: pointer;
  border-radius: 3px;
}
</style>
