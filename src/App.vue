<script setup>
import { reactive, ref } from 'vue';


const contador = reactive({
  contador1: 0,
  contador2: 0,
})

const incrementarContador = (item) => {
  contador[item]++
}

const decrementarContador = (item) => {
  if (contador(item)>0) {
    contador[item]--
  }
}


  
</script>

<template>
  
  <h1>{{contador.contador1}}</h1>
  <button @click="incrementarContador('contador1')">+</button>
  <button @click="decrementarContador('contador1')">-</button>
  
  
</template>
