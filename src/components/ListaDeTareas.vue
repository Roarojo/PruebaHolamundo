<template>
  <div>
    <h2>
      Lista de Tareas <!-- Título que se muestra en la página -->
    </h2>

    <!-- Campo de texto para escribir una nueva tarea -->
    <!-- v-model enlaza el input con la variable "nuevaTarea" -->
    <!-- @keyup.enter ejecuta la función "addTarea" cuando se presiona Enter -->
    <input type="text" v-model="nuevaTarea" @keyup.enter="addTarea">

    <!-- Lista desordenada que muestra las tareas -->
    <ul>
      <!-- v-for recorre el array "tareas" -->
      <!-- "tarea" es el valor y "index" es la posición del elemento -->
      <!-- :key ayuda a Vue a identificar cada ítem de manera única -->
      <li v-for="(tarea, index) in tareas" :key="index">
        {{tarea}} <!-- Mostramos el contenido de cada tarea -->
      </li>
    </ul>
  </div>
</template>

<script setup>
// Importamos "ref" desde Vue para crear variables reactivas
import { ref } from 'vue';

// Declaramos una lista vacía de tareas, es reactiva (cambia en tiempo real)
const tareas = ref([]);

// Declaramos una variable para guardar la nueva tarea que el usuario escribe
const nuevaTarea = ref('');

// Creamos una función que agrega la nueva tarea a la lista
const addTarea = () => {
  tareas.value.push(nuevaTarea.value); // Añadimos la tarea a la lista
  nuevaTarea.value = '';               // Limpiamos el campo de texto
}
</script>

<style>
/* Aquí puedes agregar estilos si lo deseas */
</style>

