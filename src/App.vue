<script setup>
import HeaderComponent from './components/HeaderComponent.vue';
import VariableComponent from './components/VariableComponent.vue';
import EventComponent from './components/EventComponent.vue';
import classComponent from './components/classComponent.vue';
import VifComponent from './components/VifComponent.vue';
import VforComponent from './components/VforComponent.vue';
import ChildComponent from './components/ChildComponent.vue';


</script>

<template>
  <HeaderComponent />
  <h1 class="title">Curso de Vue</h1>
  <p>En este curso aprenderemos los conceptos basicos de Vue</p>
  <br>
  <p>Ahora mismo me encuentro en el archivo central</p>  

  <VariableComponent />
  <EventComponent />
  <classComponent />
  <VifComponent />
  <VforComponent />

  <p>Acá debajo se encuentra el componenete hijo</p>
  <ChildComponent msg="Hola desde el padre" />
</template>

<style>
* {
  margin: 0;
  padding: 0;
}

.title {
  color: red;
  background-color: yellow;
}
</style>