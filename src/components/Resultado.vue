<script setup>
const props = defineProps(['calculaResultado'])
</script>

<template>
    <h2 class="text-center">Resultado: {{ props.calculaResultado }}</h2>
</template>
