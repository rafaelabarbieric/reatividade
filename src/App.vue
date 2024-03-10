<script setup>
import { reactive, computed } from 'vue';


const contador = reactive({
  contador1: 0,
  contador2: 0,
})

function decrementar() {
  if(contador.contador1 > 0){
    contador.contador1--
  }
}
function diminuir() {
  if(contador.contador2 > 0){
    contador.contador2--
  }
}
  
  const soma = computed (() => {
   return contador.contador1 + contador.contador2;
  })
</script>

<template>
  
  <div>
  <h1>{{contador.contador1}}</h1>
  <button @click="contador.contador1++">+</button>
  <button @click="decrementar()">-</button>
</div>

<div>
  <h1>{{contador.contador2}}</h1>
  <button @click="contador.contador2++">+</button>
  <button @click="diminuir()">-</button>
</div>
<div>
    <h1 v-if="soma > 10">Soma = {{ soma }} (SOMA MAIOR QUE 10!)</h1>
    <h1 v-else="soma < 10">Soma = {{ soma }} (SOMA MENOR QUE 10!)</h1>
  </div>
  
</template>