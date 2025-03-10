<script setup>

const props = defineProps(['numero1', 'numero2', 'resultado'])

</script>

<template>

        <button class="btn btn-success me-5 ms-5 mb-2">Resultado = {{props.resultado}} </button>
        <span v-if="props.numero1 && props.numero2 !=''" type="text" class="form-control-md-2"></span> 
      
</template>