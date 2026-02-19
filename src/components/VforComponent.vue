<script setup>
const items = ['Manzana', 'Banana', 'Naranja', 'Pera']
const things = { 
    name: 'Juan', 
    age: 30, 
    city: 'Madrid' 
    }
const personas = [
    { name: 'Juan', age: 30 },
    { name: 'María', age: 25 },
    { name: 'Pedro', age: 35 }
]
    
</script>

<template>
    <h1>Directiva v-for en Vue | v-for </h1>
    <div>
        <p v-for="item in items" :key="item">{{ item }}</p>
    </div>

    <h1>Directiva v-for con índice | v-for index</h1>
    <div>
        <p v-for="(item, index) in items" :key="item">
            {{ index + 1 }} - {{ item }}
        </p>
    </div>

    <h1>Directiva v-for con objeto | v-for object</h1> 
    <div>
        <p v-for="(value, key) in things" :key="key"> <!-- De esta manera se hace con un objeto json-->
            {{ key }}: {{ value }}
        </p>

        <br>

        <p v-for="persona in personas" :key="persona.name"> <!-- De esta manera se hace con un array de objetos json-->
            {{ persona.name }} tiene {{ persona.age }} años.
        </p>


    </div>
</template>

<style scoped>
h1 {
    font-size: 2em;
}
</style>