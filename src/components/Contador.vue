

<template>
 <h1>hola mundo</h1>
 <p>{{ contador }}</p>
 <button @click="incrementar">Incrementar</button>
 <button @click="decrementar">Decrementar</button>
</template>


<script setup>
import {ref} from 'vue';  //importacion de variavles reactivas de vue
const contador = ref(0);  //creamos una variable con la conexion a la variable reactica
//creamos una funcion para incrementar el valor de la variable
const incrementar = () => {
  contador.value++;
}
//creamos otra funcion para decrementar el valor de la variable
const decrementar = () => {
  contador.value--;
}
</script>

<style scoped>
p{
  color: red;
}

</style>
