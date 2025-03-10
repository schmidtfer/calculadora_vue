<script setup>
const props = defineProps (['operacao', 'numero1', 'numero2']);

</script>

<template>
    <div class="operation">
        <input @keyup="props.numero1" type="text" placeholder="Digite um número" class="form-control-md-2 ms-5" />
       <select @change="props.operacao" class="form-select-md-2 ms-5 mb-5">
          <option selected>Escolha uma operação</option>
          <option value="adicao">+</option>
          <option value="subtracao">-</option>
          <option value="multiplicacao">*</option>
          <option value="divisao">/</option>
        </select>
        <input @keyup="props.numero2" type="text" placeholder="Digite outro número" class="form-control-md-2 ms-5" />
      </div>
      <div>
        
      </div>

</template>