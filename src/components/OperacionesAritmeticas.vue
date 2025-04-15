<!-- ✅ ¿Qué se está usando aquí?
v-model.number → convierte automáticamente la entrada a número.
Botones con @click → ejecutan funciones específicas.
ref() → para que Vue reactive y muestre los cambios.
Validación en la división para evitar dividir entre 0. -->

<template>
  <div>
    <h2>Calculadora básica</h2>

    <!-- Inputs para los dos números -->
    <input type="number" v-model.number="num1" placeholder="Número 1">
    <input type="number" v-model.number="num2" placeholder="Número 2">

    <!-- Botones para cada operación -->
    <div style="margin: 10px 0;">
      <button @click="sumar">Sumar</button>
      <button @click="restar">Restar</button>
      <button @click="multiplicar">Multiplicar</button>
      <button @click="dividir">Dividir</button>
    </div>

    <!-- Resultado mostrado dinámicamente -->
    <h3>Resultado: {{ resultado }}</h3>
  </div>
</template>

<script setup>
import { ref } from 'vue';

// Declaramos los dos números y el resultado como variables reactivas
const num1 = ref(0);
const num2 = ref(0);
const resultado = ref(0);

// Funciones para cada operación
const sumar = () => {
  resultado.value = num1.value + num2.value;
}

const restar = () => {
  resultado.value = num1.value - num2.value;
}

const multiplicar = () => {
  resultado.value = num1.value * num2.value;
}

const dividir = () => {
  // Validamos que no se divida entre cero
  if (num2.value === 0) {
    resultado.value = 'Error: División entre cero';
  } else {
    resultado.value = num1.value / num2.value;
  }
}
</script>

<style>
input {
  margin: 5px;
  padding: 5px;
  width: 120px;
}

button {
  margin-right: 10px;
  padding: 5px 10px;
}
</style>
