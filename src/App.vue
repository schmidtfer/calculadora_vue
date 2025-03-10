<script setup>
import { reactive } from 'vue';

import Operacao from './components/Operacao.vue'
import Resultado from './components/Resultado.vue'

const estado = reactive ({
  operation: '+',
  numero1: '',
  numero2: ''
  
})

const resultado = () => {
  const {operation} = estado
  switch(operation) {
    case '-':
    return parseFloat (estado.numero1) - parseFloat (estado.numero2);
    case '*':
    return parseFloat (estado.numero1) * parseFloat (estado.numero2); 
    case '/':
    return parseFloat (estado.numero1) / parseFloat (estado.numero2);
  default:
    return parseFloat (estado.numero1) + parseFloat (estado.numero2);
  }
}



</script>

<template>
  <div class="container">
    <header>
    <h1 class="title pt-5 mb-5">Calculadora</h1>
  </header>
   
     
      <Operacao :operacao="evento=> estado.operation = evento.target.value" :numero1="evento => estado.numero1 = evento.target.value" :numero2="evento => estado.numero2 = evento.target.value" />
      <Resultado :numero1="estado.numero1"  :numero2="estado.numero2" :resultado="resultado()" />
  
 
    
    
      </div>
</template>

<style scoped>

.container {
  border: solid 2px #000;
  padding: 20px;
  text-align: center;
  width: 50%;
  background-color: #727070c2;
}

.title {
  text-align: center;
}

</style>
