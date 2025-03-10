<script setup>
import { reactive } from 'vue';

import Cabecalho from './components/Cabecalho.vue'
import Operacao from './components/Operacao.vue'
import Resultado from './components/Resultado.vue'

const estado = reactive ({
  operation: '+',
  numero1: '',
  numero2: '',
  
})

const resultado = () => {
  switch (estado.operation) {
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
    <Cabecalho />
     
      <Operacao :operacao="evento=> estado.operation = evento.target.value" :numero1="evento =>estado.numero1 = evento.target.value" :numero2="evento =>estado.numero2 = evento.target.value" />
      
      <Resultado :numero1="estado.numero1" :numero2="estado.numero2" :resultado="resultado()"></Resultado>
  
 
    
    
      </div>
</template>

<style scoped>
.container {
  border: solid 2px #000;
  padding: 20px;
}

.title {
  text-align: center;
}

</style>
