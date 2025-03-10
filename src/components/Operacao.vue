<script setup>
  const props = defineProps(['operacao', 'numero1', 'numero2'])

</script>

<template>
    <div class="operation">
      <input @keyup="props.numero1" type="number" placeholder="Digite um número" class="form-control-md-2 ms-5" />
       <select @change="props.operacao" class="form-select-md-2 ms-5 mb-5">
          <option selected>Escolha uma operação</option>
          <option value="+">+</option>
          <option value="-">-</option>
          <option value="*">*</option>
          <option value="/">/</option>
        </select>
        <input @keyup="props.numero2" type="number" placeholder="Digite outro número" class="form-control-md-2 ms-5" />
      </div>
      <div>
        
      </div>

</template>

<style scoped>
    input {
      background-color: rgb(219, 217, 214);
    }
</style>
