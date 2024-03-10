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
    <h1 v-else>Soma = {{ soma }} (SOMA MENOR QUE 10!)</h1>
</div>
<div>
    <h1 v-if="soma == 0">(ESSA SOMA É ...!)</h1>
    <h1 v-else-if="soma%2 == 0">(ESSA SOMA É PAR!)</h1>
    <h1 v-else>(ESSA SOMA É ÍMPAR!)</h1>
</div>
<div>
</div>
  
</template>