<script setup>
import HeaderComponent from './components/HeaderComponent.vue';
import VariableComponent from './components/VariableComponent.vue';
import EventComponent from './components/EventComponent.vue';
import classComponent from './components/classComponent.vue';
import VifComponent from './components/VifComponent.vue';
import VforComponent from './components/VforComponent.vue';
import ChildComponent from './components/ChildComponent.vue';
import ComponentEvent from './components/ComponentEvent.vue';
import SlotsComponent from './components/SlotsComponent.vue';
import ComputedComponent from './components/ComputedComponent.vue';
import { ref } from 'vue';

// Definimos una variable de tipo objeto para pasarla al hijo
const person = {
  nombre: 'Juan',
  edad: 30,
  profesion: 'Desarrollador'
}

const displayName = ref('');

const setName = (e) => {
  displayName.value = e;
}

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
  <!-- De esta manera se pasan las props al hijo, con :person se le dice 
   que lo que se le va a pasar es un objeto json, y luego se le asigna 
   la variable person que definimos arriba -->
  <ChildComponent msg="Hola desde el padre" :person="person"/> 

  <h1>Components Events | Comunicación Hijo-Padre</h1>
  <h2>Hola {{ displayName }}</h2>
  <ComponentEvent @login="setName" />

  <SlotsComponent>
    <p>Este es un bloque html que se pasa desde el padre al hijo, y se muestra en el slot del hijo</p>
    <p>Tambien pueden ser componentes, como por ejemplo el componente ChildComponent</p>
  </SlotsComponent>

  <SlotsComponent>
    <ChildComponent msg="Hola desde el padre con slots" :person="person"/> <!-- Tambien podemos pasar otros componentes-->
  </SlotsComponent>

  <SlotsComponent />

  <SlotsComponent>

    <template #footer>
      
    </template>

    <template #header>
      
    </template>

  </SlotsComponent>

  <ComputedComponent />

</template>

<style>
/* * {
  margin: 0;
  padding: 0;
} */

.title {
  color: red;
  background-color: yellow;
}
</style>